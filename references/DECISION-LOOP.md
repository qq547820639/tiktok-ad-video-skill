# 核心决策循环 · Bayesian Decision Loop (v4.0-Adaptive)

> **文件定位**: v4.0 系统的“心脏”。本文档不是知识库，而是**可执行的算法流程图**。
>   - 当系统需要在 16 个失败案例、8 类 Hook、动态权重之间做决策时，本文档是唯一的导航图。
>   - 阅读顺序：Loop 1 (初始化) → Loop 2 (选择) → Loop 3 (更新) → 收敛判定。
> 
> **数学依赖**:
>   - 先验: `failure-case-library.md` → Beta(α₀, β₀)
>   - 权重: `core-knowledge.md` §4 动态权重引擎
>   - 采样: `ab-testing-matrix.md` → Thompson Sampling
>   - 文化过滤: `cultural-tensor.md` → Hook 适配矩阵
>   - 回传: `product-tracker-template.md` → CTR_actual

---

## 〇、系统状态定义

在进入循环之前，系统维护以下全局状态：

```
STATE = {
    // --- 贝叶斯先验 (来自 failure-case-library.md 附录) ---
    prior: {
        fatal:   { α: 13, β: 3  },   // 致命层失败概率 Beta
        core:    { α: 9,  β: 7  },   // 核心层失败概率 Beta
        hygiene: { α: 12, β: 4  },   // 卫生层失败概率 Beta
        culture: { α: 15, β: 1  },   // 文化层失败概率 Beta
    },

    // --- Hook 类型权重 (每个品类×市场独立维护) ---
    hook_weights: {
        // key = "{category}_{market}_{hook_type}"
        "cookware_US_CON": { w: 1.32, α: 8, β: 2, last_update: "2026-04-20" },
        "cookware_US_CUR": { w: 1.00, α: 1, β: 1, last_update: "2026-04-01" },
        // ... 其余 6 类同理
    },

    // --- 全局超参数 (锁定) ---
    LAMBDA: 0.0462,                    // 遗忘因子 (半衰期15天)
    THRESHOLD_INTERVAL: [0.55, 0.75],  // 决策阈值区间
    BOOTSTRAP_N: 1000,                 // Bootstrap 重采样次数
    CONVERGENCE_WINDOW: 5,             // 收敛判定窗口 (连续轮次)
    MIN_SAMPLES_FOR_UPDATE: 10,        // 触发权重更新的最小样本量
    CULTURE_SIMILARITY_THRESHOLD: 0.3, // 先验借用的文化向量最大欧氏距离
}
```

---

## 一、Loop 1: 先验初始化回路 (Prior Initialization Loop)

**触发条件**: 用户首次为某品类×市场组合请求生成

**目标**: 确定 Hook 类型的先验 Beta(α, β) 从何而来

### 伪代码

```python
def initialize_prior(category: str, market: str, hook_type: str) -> tuple:
    """
    返回 (α, β) 作为该 Hook 类型的先验参数
    """
    key = f"{category}_{market}_{hook_type}"
    
    # Step 1: 检查是否有本地数据
    if key in STATE.hook_weights:
        return (STATE.hook_weights[key].α, STATE.hook_weights[key].β)
    
    # Step 2: 检查是否有相似市场可借用
    market_vector = get_culture_vector(market)
    best_market = None
    best_similarity = float('inf')
    
    for other_market in MARKETS:
        if other_market == market:
            continue
        other_vector = get_culture_vector(other_market)
        distance = euclidean(market_vector, other_vector)
        
        other_key = f"{category}_{other_market}_{hook_type}"
        if distance < STATE.CULTURE_SIMILARITY_THRESHOLD and other_key in STATE.hook_weights:
            if distance < best_similarity:
                best_similarity = distance
                best_market = other_market
    
    if best_market:
        # 借用先验，但增加不确定性 (β 加一个惩罚项)
        borrowed = STATE.hook_weights[f"{category}_{best_market}_{hook_type}"]
        penalty = 2  # 借用惩罚：β 增加，表示更低置信度
        return (borrowed.α, borrowed.β + penalty)
    
    # Step 3: 使用无信息先验
    return (1, 1)  # Beta(1, 1) = Uniform(0, 1)
```

### 决策流图
```
新品类×市场请求
    │
    ├─ 本地有先验？ ──→ 是 ──→ 返回 (α_local, β_local)
    │                          │
    │                          └─→ 进入 Loop 2
    │
    ├─ 文化相似市场有先验？ ──→ 是 ──→ 借用 + 惩罚 (α, β+2)
    │                                    │
    │                                    └─→ 进入 Loop 2
    │
    └─ 无任何先验 ──→ Beta(1, 1) ──→ 进入 Loop 2 (全探索模式)
```

---

## 二、Loop 2: 采样选择回路 (Thompson Sampling Loop)

**触发条件**: 每次 Hook 盲测（用户请求生成）

**目标**: 从 N 个候选臂中选择最优臂呈现给用户

### 步骤

#### Step 1: 文化过滤
根据 `cultural-tensor.md` 的适配矩阵，移除目标市场禁用的 Hook 类型（标记为 ❌ 的条目）。

```python
def filter_arms_by_culture(arms: list, market: str) -> list:
    """
    从候选臂中移除文化不适用的 Hook 类型
    """
    culture_matrix = load_culture_matrix()  # 来自 cultural-tensor.md
    filtered = []
    for arm in arms:
        status = culture_matrix[market][arm.hook_type]  # ✅ ⚠️ ❌
        if status != "❌":
            arm.cultural_flag = status  # 标记是否需调整语气
            filtered.append(arm)
    return filtered
```

#### Step 2: Thompson Sampling
```python
def thompson_select(arms: list) -> tuple:
    """
    从每个臂的 Beta(α, β) 中采样，返回 θ 最大的臂
    返回: (selected_arm, theta_values_dict)
    """
    theta_values = {}
    for arm in arms:
        # 从 Beta 分布中采样
        theta = random_beta(arm.α, arm.β)
        theta_values[arm.id] = theta
    
    # 选择 θ 最大的臂
    selected = argmax(theta_values)
    return (selected, theta_values)
```

#### Step 3: 呈现与用户反馈
```python
def present_and_collect(selected_arm, arms):
    """
    给用户展示选中的 Hook 文案，收集 Y/N 反馈
    """
    # 展示文案
    display(selected_arm.hook_text)
    display(selected_arm.script_preview)
    
    # 收集用户选择
    user_choice = wait_for_user_input()  # Y/N
    
    # 更新该臂的 Beta 分布
    if user_choice == "Y":
        selected_arm.α += 1
    else:
        selected_arm.β += 1
    
    # 记录本轮采样值，用于收敛判定
    return {
        "round": current_round,
        "selected": selected_arm.id,
        "theta_values": theta_values,
        "user_choice": user_choice,
        "updated_alpha": selected_arm.α,
        "updated_beta": selected_arm.β,
    }
```

#### Step 4: 收敛判定
```python
def check_convergence(history: list, arms: list) -> dict:
    """
    三条收敛标准，同时满足则停止盲测
    """
    if len(history) < STATE.CONVERGENCE_WINDOW:
        return {"converged": False, "reason": "轮次不足"}
    
    # 条件 1: 最佳臂在最近 N 轮中被选中 ≥ N-1 次
    recent_rounds = history[-STATE.CONVERGENCE_WINDOW:]
    top_arm_id = mode([r["selected"] for r in recent_rounds])
    top_arm_count = sum(1 for r in recent_rounds if r["selected"] == top_arm_id)
    
    condition_1 = top_arm_count >= STATE.CONVERGENCE_WINDOW - 1
    
    # 条件 2: 最佳臂的 95% CI 宽度 < 0.30
    top_arm = find_arm_by_id(arms, top_arm_id)
    ci_lower, ci_upper = beta_posterior_ci(top_arm.α, top_arm.β, n_bootstrap=STATE.BOOTSTRAP_N)
    condition_2 = (ci_upper - ci_lower) < 0.30
    
    # 条件 3: 最佳臂的样本量 (α + β) ≥ 5
    condition_3 = (top_arm.α + top_arm.β) >= 5
    
    if condition_1 and condition_2 and condition_3:
        return {
            "converged": True,
            "best_arm": top_arm_id,
            "p_viral": top_arm.α / (top_arm.α + top_arm.β),
            "ci": [ci_lower, ci_upper],
        }
    else:
        return {
            "converged": False,
            "reason": f"C1:{condition_1} C2:{condition_2} C3:{condition_3}",
        }
```

### 决策流图
```
用户请求生成
    │
    ├─ 1. 文化过滤：移除 ❌ Hook 类型
    │
    ├─ 2. 对每臂采样 θⱼ ~ Beta(αⱼ, βⱼ)
    │
    ├─ 3. 选择 argmax(θ) 作为展示臂
    │
    ├─ 4. 用户盲选 Y/N
    │    ├─ Y → α_selected += 1
    │    └─ N → β_selected += 1
    │
    ├─ 5. 收敛判定
    │    ├─ 已收敛 → 最佳臂投放 + 记录最终 P(Viral)
    │    ├─ 所有臂 P(Viral) < 0.40 → 放弃，重新竞品拆解
    │    ├─ 已 10 轮未收敛 → 当前最佳臂投放 (标记未收敛)
    │    └─ 继续 → 回到步骤 2
```

---

## 三、Loop 3: 权重更新回路 (Dynamic Weight Update Loop)

**触发条件**: 视频投放后第 7 天（或达到爆款标准时立即触发）

**目标**: 将真实市场反馈回写至权重系统和贝叶斯先验

### 回传数据格式
```
FEEDBACK = {
    video_id: str,
    category: str,
    market: str,
    hook_type: str,
    ctr_actual: float,        // 前 3 秒留存率 (0-100)
    ctr_predicted: float,     // 生成时的预测留存率
    viral: bool,              // 是否爆款 (>100K播放 且 分享率>3%)
    days_since_publish: int,  // 距发布天数
}
```

### 伪代码

```python
def update_weights(feedback: dict):
    """
    单个视频反馈触发的完整权重更新
    """
    key = f"{feedback.category}_{feedback.market}_{feedback.hook_type}"
    old_weights = STATE.hook_weights.get(key, {"w": 1.0, "α": 1, "β": 1, "last_update": None})
    
    # ──── 更新 1: 贝叶斯先验 (来自 Loop 1/2 的 Beta 分布) ────
    if feedback.viral:
        old_weights.α += 1
    else:
        old_weights.β += 1
    
    # ──── 更新 2: 动态权重 (核心方程) ────
    # w_new = w_old × (CTR_actual / CTR_predicted) × exp(-λ·Δt)
    
    if old_weights.last_update is not None:
        delta_t = (today() - old_weights.last_update).days
    else:
        delta_t = 0
    
    ctr_ratio = feedback.ctr_actual / max(feedback.ctr_predicted, 0.01)  # 防除零
    decay = exp(-STATE.LAMBDA * delta_t)
    
    old_weights.w = old_weights.w * ctr_ratio * decay
    old_weights.last_update = today()
    
    # 存储更新
    STATE.hook_weights[key] = old_weights
    
    # ──── 更新 3: 触发全局先验更新 ────
    # 根据失败类型，更新对应的 Beta 先验
    if not feedback.viral:
        # 分析失败原因，更新对应的 prior 层
        failure_type = classify_failure(feedback)
        STATE.prior[failure_type].β += 1
    else:
        # 成功则略微降低失败概率估计
        STATE.prior["core"].α += 0.5  # 成功 = 核心层缺陷概率的信号
    
    return {
        "new_weight": old_weights.w,
        "updated_alpha": old_weights.α,
        "updated_beta": old_weights.β,
        "p_viral_posterior": old_weights.α / (old_weights.α + old_weights.β),
    }
```

### 决策流图
```
视频投放数据回传
    │
    ├─ 1. 更新 Hook 类型的 (α, β)
    │    ├─ 爆款 → α += 1
    │    └─ 非爆款 → β += 1
    │
    ├─ 2. 权重方程: w *= (CTR_actual/CTR_predicted) × e^(-λ·Δt)
    │
    ├─ 3. 更新全局先验 (fatal/core/hygiene/culture)
    │    ├─ 非爆款 → 对应失败层 β += 1
    │    └─ 爆款 → core.α += 0.5
    │
    ├─ 4. 检查权重衰减
    │    ├─ 连续 30 天无更新 → 权重降至 25%
    │    ├─ 连续 60 天无更新 → 权重降至 6.25% (实质退出)
    │    └─ 连续 90 天无更新 → 从 hook_weights 中移除
    │
    └─ 5. 收敛状态更新
         ├─ 连续 10 条视频 P(Viral) 中位数 σ < 0.05 → 该品类已收敛
         └─ 降低该品类的盲测频率至每 5 条一次
```

---

## 四、遗忘因子衰减监控 (Forgetting Factor Monitor)

**独立于三个主循环，作为守护进程运行**

```python
def forgetting_monitor():
    """
    每日执行一次，检查所有权重的衰减状态
    """
    today = today()
    
    for key, weights in STATE.hook_weights.items():
        if weights.last_update is None:
            continue
        
        days_since_update = (today - weights.last_update).days
        
        # 仅当超过 15 天无更新时显式衰减 (正常更新已在 Loop 3 中处理)
        if days_since_update >= 15 and days_since_update % 7 == 0:
            # 每周检查一次，应用纯时间衰减
            decay = exp(-STATE.LAMBDA * 7)  # 一周的衰减
            weights.w *= decay
            
            # 标记为"仅时间衰减，无数据更新"
            log(f"[FORGET] {key}: w={weights.w:.4f}, idle={days_since_update}d")
        
        # 超时移除
        if days_since_update >= 90:
            log(f"[REMOVE] {key}: 90天无反馈，已移除")
            del STATE.hook_weights[key]
```

### 衰减可视化
```
权重保持率曲线:
t=0:    w = 1.000  ████████████████████████
t=15:   w = 0.500  ████████████ (半衰期)
t=30:   w = 0.250  ██████ (1个月)
t=45:   w = 0.125  ███
t=60:   w = 0.062  ██ (2个月)
t=90:   → 移除
```

---

## 五、完整决策循环时序图

```
用户请求 ──→ [Loop 1: 先验初始化] ──→ Beta(α,β) 就绪
                    │
                    ▼
              [Loop 2: Thompson Sampling]
                    │
        ┌───────────┼───────────┐
        ▼           ▼           ▼
     Arm A      Arm B      Arm C
     θ~Beta     θ~Beta     θ~Beta
        │           │           │
        └───────────┼───────────┘
                    ▼
            argmax(θ) = 选中臂
                    │
                    ▼
            用户盲选 Y/N
                    │
        ┌───────────┴───────────┐
        ▼                       ▼
    更新 α/β              继续/收敛判定
        │                       │
        └───────────┬───────────┘
                    ▼
            生成 + 诊断 + 投放
                    │
                    ▼ (7天后或爆款触发)
        [Loop 3: 权重更新回路]
                    │
        ┌───────────┼───────────┐
        ▼           ▼           ▼
    更新 α/β    w *= ratio   更新全局 Prior
                    │
                    ▼
        [Forgetting Monitor · 每日]
                    │
                    ▼
              权重衰减/移除
```

---

## 六、快速调试指南

### Q: 系统冷启动时，没有任何数据，怎么办？
> A: Loop 1 自动退回 Beta(1,1) 无信息先验。Thompson Sampling 此时等价于随机选择，随着用户反馈积累（3-5 次盲测后），优势臂自然浮现。

### Q: 某个品类在某个市场一直跑不出爆款，如何判断是否该放弃？
> A: Loop 2 收敛判定中：若所有臂的 P(Viral) 均 < 0.40，触发“放弃本轮 Hook 方向”建议。不自动放弃的原因：可能只是 Hook 文案设计问题，而非品类-市场不匹配。

### Q: 权重更新后，旧的最佳臂反而被降权了，这是 bug 吗？
> A: 不是。这恰恰是遗忘因子 λ 的工作——说明该臂在过去 15 天内没有产生正向反馈，系统正在自动淡出过时策略。

### Q: 文化向量相似度 < 0.3 的市场可以互借先验，这个阈值是怎么定的？
> A: 基于 Hofstede 六维向量的欧氏距离。经过标准化后，全距约 0-1.5，< 0.3 意味着两个市场在 6 个文化维度上的差异平均不到 5%。例如美国-澳大利亚 (距离 0.15)，韩国-日本 (距离 0.22)。

---
*DECISION-LOOP.md v1.0 · v4.0-Adaptive 心脏 · 三个回路驱动一个贝叶斯生命体*
