# 核心决策循环 · Bayesian Decision Loop (v4.2-Adaptive)

> **文件定位**: v4.2 系统的“心脏”。本文档不是知识库，而是**可执行的算法流程图**。
>   - 阅读顺序：Loop 0 (内部自评) → Loop 1 (先验初始化) → Loop 2 (Thompson Sampling) → Loop 3 (权重更新) → 收敛判定。
> 
> **v4.2 新增**: Loop 0 内部自评循环——系统不依赖用户反馈的自我收敛机制。
> 
> **数学依赖**:
>   - 先验: `failure-case-library.md` → Beta(α₀, β₀)
>   - 权重: `core-knowledge.md` §4 动态权重引擎
>   - 采样: `ab-testing-matrix.md` → Thompson Sampling
>   - 文化过滤: `cultural-tensor.md` → Hook 适配矩阵
>   - 多模态: `multimodal-reference-guide.md` → 光照/主体/动态锚定

---

## 〇、系统状态定义

在进入循环之前，系统维护以下全局状态：

```
STATE = {
    // --- 贝叶斯先验 (来自 failure-case-library.md 附录) ---
    prior: {
        fatal:   { α: 13, β: 3  },
        core:    { α: 9,  β: 7  },
        hygiene: { α: 12, β: 4  },
        culture: { α: 15, β: 1  },
    },

    // --- Hook 类型权重 (每个品类×市场独立维护) ---
    hook_weights: {
        // key = "{category}_{market}_{hook_type}"
        "cookware_US_CON": { w: 1.32, α: 8, β: 2, last_update: "2026-04-20" },
    },

    // --- 全局超参数 (锁定) ---
    LAMBDA: 0.0462,
    THRESHOLD_INTERVAL: [0.55, 0.75],
    BOOTSTRAP_N: 1000,
    CONVERGENCE_WINDOW: 5,
    MIN_SAMPLES_FOR_UPDATE: 10,
    CULTURE_SIMILARITY_THRESHOLD: 0.3,
    
    // 🆕 v4.2 内部自评超参数
    MAX_SELF_EVAL_ROUNDS: 3,          // 最多迭代3轮
    SELF_EVAL_CONVERGENCE: 2,         // 连续2轮无新问题即收敛
    P_VIRAL_CONVERGENCE_DELTA: 0.05,  // P(Viral)变化<0.05即收敛
}
```

---

## 🆕 Loop 0: 内部自评循环 (Internal Self-Evaluation Loop)

**触发条件**: 
- 阶段 6 输出 Seedance 2.0 原子化提示词后**自动触发**
- **不依赖用户反馈**，系统基于内置规则自主评估生成质量

**目标**: 
- 在交付给用户之前，系统自行发现并修正 Prompt 中的缺陷
- 通过最多 3 轮自评迭代，将 P(Viral) 收敛到稳定区间
- 确保每次输出都附带了自我诊断和改进记录

### 自评维度（与三层诊断完全对齐）

```python
SELF_EVAL_DIMENSIONS = {
    "fatal": {
        "checks": [
            "visual_conflict_first_3s",    # 视觉冲突前3秒是否出现？
            "sound_hook_exists",           # 声音Hook存在？
            "aigc_compliance",             # AIGC合规三大禁区无触碰？
        ],
        "on_fail": "ABORT_AND_RETURN_TO_STAGE_3"  # 致命=返回阶段3
    },
    "core": {
        "checks": [
            "vertical_signal_dual_5s",     # 垂直信号前5秒口述+字幕双出现？
            "realism_ratio_60pct",         # 原生感：60%+真实材质占比？
            "scene_logic_coherent",        # 场景逻辑自洽？
            "replay_easter_egg_exists",    # 复播彩蛋存在？
            "single_subject_per_shot",     # 单镜头单主体？
        ],
        "on_fail": "WARN_AND_OUTPUT_FIXED_VERSION"  # 警告+输出修正版
    },
    "hygiene": {
        "checks": [
            "no_negative_anchors",         # 无"不/别/没"负向锚点词？
            "word_count_per_segment_100",  # 单段≤100词？
            "no_cultural_sensitive",       # 无文化敏感元素？
            "pause_markers_every_12chars", # 口播标注/停顿标记？
            "verifiable_details_replace_abstract",  # 可验证细节替代抽象词？
        ],
        "on_fail": "AUTO_FIX_AND_OUTPUT_CORRECTED"  # 自动修正+输出
    }
}
```

### 自评评分函数

```python
def self_evaluate(prompt_segments: list, script: dict) -> dict:
    """
    对已生成的4段Prompt进行内部自评
    返回: {score, issues, p_viral_estimate, convergence_status}
    """
    issues = []
    
    # --- 致命层自评 ---
    fatal_checks = check_fatal_layer(prompt_segments[0], script)
    for check_name, passed in fatal_checks.items():
        if not passed:
            issues.append({
                "layer": "fatal",
                "check": check_name,
                "action": "ABORT"
            })
    
    # 致命层不通过 → 直接返回
    if any(i["layer"] == "fatal" for i in issues):
        return {
            "score": 0,
            "issues": issues,
            "p_viral_estimate": 0.0,
            "convergence_status": "FATAL_FAIL"
        }
    
    # --- 核心层自评 ---
    core_checks = check_core_layer(prompt_segments, script)
    for check_name, result in core_checks.items():
        if not result["passed"]:
            issues.append({
                "layer": "core",
                "check": check_name,
                "detail": result.get("detail", ""),
                "suggestion": result.get("suggestion", ""),
                "action": "WARN_AND_FIX"
            })
    
    # --- 卫生层自评 ---
    hygiene_checks = check_hygiene_layer(prompt_segments, script)
    for check_name, result in hygiene_checks.items():
        if not result["passed"]:
            issues.append({
                "layer": "hygiene",
                "check": check_name,
                "detail": result.get("detail", ""),
                "auto_fix": result.get("auto_fix", ""),
                "action": "AUTO_FIX"
            })
    
    # ---🆕 P(Viral) 重估 ---
    # 基于自评发现的问题数量和层级，重新计算 P(Viral)
    base_p = calculate_base_p_viral(script.hook_type)
    penalty = calculate_penalty(issues)  # 每个核心层问题扣0.05-0.10
    adjusted_p = max(0.0, min(1.0, base_p - penalty))
    
    # Bootstrap CI
    ci_lower, ci_upper = bootstrap_ci(adjusted_p, n=STATE.BOOTSTRAP_N)
    
    return {
        "score": calculate_score(issues),  # 满分5.0
        "issues": issues,
        "p_viral_estimate": adjusted_p,
        "ci": [ci_lower, ci_upper],
        "convergence_status": "NEEDS_FIX" if issues else "CONVERGED"
    }
```

### 迭代控制逻辑

```python
def internal_iteration_loop(prompt_segments, script, max_rounds=3):
    """
    内部自评迭代主循环
    最多迭代 max_rounds 轮，每轮自评→修正→重估
    """
    current_segments = prompt_segments
    current_script = script
    iteration_history = []
    
    for round_num in range(1, max_rounds + 1):
        # Step 1: 自评
        eval_result = self_evaluate(current_segments, current_script)
        iteration_history.append({
            "round": round_num,
            "p_viral": eval_result["p_viral_estimate"],
            "ci": eval_result["ci"],
            "issues_count": len(eval_result["issues"]),
            "issues": eval_result["issues"]
        })
        
        # Step 2: 判定
        if eval_result["convergence_status"] == "FATAL_FAIL":
            return {
                "status": "FATAL_FAIL",
                "message": "致命层不通过，需返回阶段3重新生成Hook",
                "history": iteration_history
            }
        
        if eval_result["convergence_status"] == "CONVERGED":
            return {
                "status": "CONVERGED",
                "final_segments": current_segments,
                "final_script": current_script,
                "p_viral": eval_result["p_viral_estimate"],
                "ci": eval_result["ci"],
                "rounds": round_num,
                "history": iteration_history
            }
        
        # Step 3: 修正
        if round_num < max_rounds:
            # 应用修正
            current_segments = apply_fixes(current_segments, eval_result["issues"])
            current_script = apply_script_fixes(current_script, eval_result["issues"])
        else:
            # 最后一轮：即使未完全收敛，也输出当前版本+问题清单
            return {
                "status": "MAX_ROUNDS_REACHED",
                "final_segments": current_segments,
                "final_script": current_script,
                "p_viral": eval_result["p_viral_estimate"],
                "ci": eval_result["ci"],
                "remaining_issues": eval_result["issues"],
                "rounds": round_num,
                "history": iteration_history,
                "message": f"已达最大迭代轮次({max_rounds})，以下问题未完全修复：{len(eval_result['issues'])}个"
            }
    
    # 安全检查：不会到这里，但防无限循环
    return {"status": "ERROR", "message": "Unexpected loop exit"}
```

### 收敛判定

```python
def check_self_eval_convergence(history: list) -> dict:
    """
    内部自评收敛判定（不依赖外部数据）
    """
    if len(history) < STATE.SELF_EVAL_CONVERGENCE:
        return {"converged": False, "reason": "自评轮次不足"}
    
    # 条件 1: 连续 N 轮无新增问题
    recent = history[-STATE.SELF_EVAL_CONVERGENCE:]
    no_new_issues = all(r["issues_count"] == 0 for r in recent)
    
    # 条件 2: P(Viral) 变化 < Δ
    if len(history) >= 2:
        p_viral_delta = abs(history[-1]["p_viral"] - history[-2]["p_viral"])
        p_viral_stable = p_viral_delta < STATE.P_VIRAL_CONVERGENCE_DELTA
    else:
        p_viral_stable = False
    
    if no_new_issues and p_viral_stable:
        return {
            "converged": True,
            "final_p_viral": history[-1]["p_viral"],
            "final_ci": history[-1]["ci"],
            "rounds": len(history)
        }
    
    return {
        "converged": False,
        "reason": f"无新问题:{no_new_issues}, P(Viral)稳定:{p_viral_stable}"
    }
```

### 决策流图
```
阶段 6 输出完成
    │
    ▼
[Loop 0: 内部自评]
    │
    ├─ 致命层自评
    │    ├─ 不通过 → 🛑 返回阶段 3（重新Hook）
    │    └─ 通过 → 继续
    │
    ├─ 核心层自评
    │    ├─ 无问题 → 继续
    │    └─ 有问题 → 记录问题 + 生成修复建议
    │
    ├─ 卫生层自评
    │    ├─ 无问题 → 继续
    │    └─ 有问题 → 自动修正
    │
    ├─ P(Viral) 重估
    │    └─ 基于问题数扣分，重新计算 P(Viral) + CI
    │
    ├─ 收敛判定
    │    ├─ 已收敛 → ✅ 输出最终版本
    │    ├─ 未收敛 + 轮次 < 3 → 应用修正 → 回到自评步骤
    │    └─ 未收敛 + 轮次 = 3 → ⚠️ 输出当前版本 + 剩余问题清单
    │
    └─ 输出: 最终Prompt + 自评历史 + P(Viral) + CI
```

### 自评输出格式模板

每次自评完成，输出以下格式：

```
---
【内部自评 · Round {N}/{MAX}】
· 致命层: ✅ / ❌（{问题描述}）
· 核心层: ✅ / ⚠️（{问题数量}个 → {修复建议摘要}）
· 卫生层: ✅ / ⚠️（{问题数量}个 → 已自动修正）
· P(Viral) 重估: {值}（修正前: {值} → 修正后: {值}）
· 95% CI: [{下限}, {上限}]
· 收敛状态: {已收敛 / 继续迭代 / 已达上限}
---
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
        borrowed = STATE.hook_weights[f"{category}_{best_market}_{hook_type}"]
        penalty = 2
        return (borrowed.α, borrowed.β + penalty)
    
    # Step 3: 使用无信息先验
    return (1, 1)
```

---

## 二、Loop 2: 采样选择回路 (Thompson Sampling Loop)

**触发条件**: 每次 Hook 盲测（用户请求生成）

**目标**: 从 N 个候选臂中选择最优臂呈现给用户

### v4.2 修正：默认选择策略

```python
def thompson_select_with_default(arms: list, user_choice: str = None) -> tuple:
    """
    执行 Thompson Sampling，支持用户未选择时的默认策略
    """
    theta_values = {}
    for arm in arms:
        theta = random_beta(arm.α, arm.β)
        theta_values[arm.id] = theta
    
    # 选择 θ 最大的臂
    selected = argmax(theta_values)
    
    if user_choice:
        # 用户做了选择 → 更新对应臂
        chosen_arm = find_arm_by_id(arms, user_choice)
        if chosen_arm:
            chosen_arm.α += 1
            selected = chosen_arm
    else:
        # 🆕 用户未选择 → 默认采用 θ 最高的臂，标记"默认选择"
        selected.default_choice = True
    
    return (selected, theta_values)
```

其余 Loop 2 步骤（文化过滤、收敛判定）维持 v4.0.1 不变。

---

## 三、Loop 3: 权重更新回路 (Dynamic Weight Update Loop)

维持 v4.0.1 不变（含步长裁剪 min(2.0, ratio)）。

---

## 四、完整决策循环时序图（v4.2）

```
用户请求生成
    │
    ▼
[Loop 1: 先验初始化] → Beta(α,β) 就绪
    │
    ▼
[Loop 2: Thompson Sampling]
    │
    ├─ 用户选择 → 更新对应臂
    └─ 用户未选择 → 默认选 θ 最高臂
    │
    ▼
[阶段 4: 脚本生成]
    │
    ▼
[Loop 0: 内部自评] ← 🆕 v4.2 核心
    │
    ├─ 致命层 → 不通过则返回 Loop 2
    ├─ 核心层 → 警告 + 修复
    ├─ 卫生层 → 自动修正
    │
    ├─ 自评收敛？ 
    │    ├─ 是 → 输出最终版
    │    └─ 否 + 轮次 < 3 → 修正后重新自评
    │         └─ 否 + 轮次 = 3 → 输出当前版+问题清单
    │
    ▼
[阶段 6: 输出 Seedance 2.0 Prompt]
    │
    ▼
[投放后 7 天或爆款触发]
    │
    ▼
[Loop 3: 权重更新回路]
    │
    ▼
[Forgetting Monitor · 每日]
```

---

## 五、快速调试指南

### Q: Loop 0 会不会无限循环？
> A: 不会。硬性上限 `MAX_SELF_EVAL_ROUNDS = 3`，第 3 轮后强制输出结果并附带剩余问题清单。

### Q: 如果用户给了反馈，Loop 0 还要跑吗？
> A: 要。Loop 0 是**每次生成后必须执行**的内部质检。用户反馈通过 Loop 3 更新权重，两者互不冲突。

### Q: Loop 0 和 Loop 3 的 P(Viral) 有什么区别？
> A: Loop 0 的 P(Viral) 基于**内部规则自评**（无外部数据），Loop 3 的 P(Viral) 基于**真实投放数据反馈**。两者独立计算，在阶段 5 的诊断摘要中标注校准状态。

---
*DECISION-LOOP.md v2.0 · v4.2-Adaptive 心脏 · Loop 0 赋予系统自省能力*
