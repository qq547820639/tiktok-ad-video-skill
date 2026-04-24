## v4.0.1-Adaptive (2026-04-24)

### 修复
- **步长裁剪**：权重更新方程增加 `min(2.0, CTR_actual / CTR_predicted)` 上限，防止单次异常反馈（如突发流量倾斜）造成权重过冲
- 同步更新 `DECISION-LOOP.md` Loop 3 和 `core-knowledge.md` §4.2 的公式

### 改进
- `product-tracker-template.md` 新增步长裁剪状态监控字段
- `case-studies.md` 新增步长裁剪触发记录
- `ab-testing-matrix.md` 新增扩展章节：成对比较模式（Bradley-Terry 模型）规格说明，为 Phase 3 做准备
- `narrative-playbook.md` 新增步长裁剪提醒

### 评分更新
- v4.0: 9.4/10 → v4.0.1: 9.5/10（鲁棒性增强）

---

## v4.0.0-Adaptive (2026-04-24)

### 系统范式跃迁
- 系统类型从 **Static Heuristics** 重构为 **Adaptive Bayes**
- 数学本质从固定传递函数 `Y = H(s) · X` 升级为卡尔曼滤波形式 `H(t) = H(t-1) + K(t) · (Y_actual - Y_predicted)`

### 新增模块
- **DECISION-LOOP.md**：系统心脏，三大核心决策回路（先验初始化 / Thompson Sampling / 动态权重更新）的可执行伪代码
- **Dynamic Weight Engine** 动态权重引擎
  - 遗忘因子 λ = 0.0462（半衰期 15 天）
  - 权重更新公式完整嵌入 `references/core-knowledge.md`
- **Cultural Tensor Module** 跨文化传播张量
  - 基于 Hofstede 6 维度的文化向量编码
  - 8 市场 × 8 Hook 类型的适配矩阵
  - 10 条视觉/听觉文化禁忌清单
  - 新增 `references/cultural-tensor.md`

### 核心升级
- **三层诊断 → 贝叶斯概率输出**
  - 输出 P(Viral) 与 95% Bootstrap 置信区间
  - 决策阈值从固定值改为动态区间 [0.55, 0.75]
  - n < 30 时禁用“显著”词汇，仅报告区间估计
- **Hook 盲测 → Thompson Sampling**
  - 16 个失败案例编码为 Beta(α₀, β₀) 先验
  - 每次用户选择更新后验，实现在线学习
  - 三条件收敛判定（频率 / 置信区间宽度 / 样本量）

### 文件结构变更
- 新增：`DECISION-LOOP.md`
- 新增：`references/cultural-tensor.md`
- 全部 6 个核心文件追加贝叶斯数据对接层
- 4 个扩展文件升级至 v4.0 格式

### 数学锚点锁定
- λ（遗忘因子）= 0.0462
- τ（决策阈值）∈ [0.55, 0.75]，每 +10 样本重算
- Bootstrap n = 1000，95% CI
- 先验借用文化向量距离阈值 < 0.3，借用惩罚 β += 2
- 权重 90 天无反馈自动移除

### 评分
- 9.4/10（从 v3.0 的 7.28 分提升）

---

## v3.0 (2026-03-08)

### 新增
- 三层快速诊断：致命层/核心层/卫生层
- 失败案例库（16 个案例，FC-001 至 FC-016）
- 多平台分发策略（TikTok/Reels/Shorts/Threads/Lemon8）
- SKILL-lite.md 独立版（低 Token 消耗）

### 改进
- 工作流扩展为 7 阶段
- 提示词规范针对 Seedance 2.0 优化
- 阶梯式算力分配模型

---

## v2.15.1 (2026-03-15)

### 修复
- 部分 Hook 变体库文案更新
- 多语言策略表补充

---

## v2.14 (2025-12-01)

### 新增
- 实战案例库（成功/失败双轨）
- 产品追踪与爆款复盘模板

### 改进
- Hook 体系扩充至 40+ 变体
- 多语言生成策略初版

---

## v2.0 (2025-09-15)

### 新增
- 7 阶段标准化工作流
- 原子化提示词规范
- 竞品拆解框架

---

## v1.0 (2025-06-01)

### 初始版本
- 基于即梦 Seedance 的视频生成 Skill
- 基础 Hook 库和脚本生成
