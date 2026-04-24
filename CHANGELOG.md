# Changelog

## v4.0.0-Adaptive (2026-04-24)

### 系统范式跃迁
- 系统类型从 **Static Heuristics** 重构为 **Adaptive Bayes**
- 数学本质从固定传递函数升级为卡尔曼滤波形式  
  `H(t) = H(t-1) + K(t) · (Y_actual - Y_predicted)`

### 新增模块
- **Dynamic Weight Engine** 动态权重引擎  
  - 遗忘因子 λ = 0.0462（半衰期15天）  
  - 权重更新公式完整嵌入 `references/core-knowledge.md`
- **Cultural Tensor Module** 跨文化传播张量  
  - 基于 Hofstede 6 维度的文化向量编码  
  - 8 市场 × 8 Hook 类型的适配矩阵  
  - 新增 `references/cultural-tensor.md`

### 核心升级
- **三层诊断 → 贝叶斯概率输出**  
  - 输出 P(Viral) 与 95% Bootstrap 置信区间  
  - 决策阈值从固定值改为动态区间 [0.55, 0.75]  
  - n < 30 时禁用“显著”词汇，仅报告区间估计
- **Hook 盲测 → Thompson Sampling**  
  - 16 个失败案例编码为 Beta(α₀, β₀) 先验  
  - 每次用户选择更新后验，实现在线学习

### 文件结构变更
- 新增：`references/cultural-tensor.md`
- 全部核心文件追加贝叶斯数据对接层
- `CHANGELOG.md` 条目增加（本文件）

### 数学锚点锁定
- λ（遗忘因子）= 0.0462
- τ（决策阈值）∈ [0.55, 0.75]，每 +10 样本重算
- Bootstrap n = 1000，95% CI

---

## v3.0 (2026-03-08)

### 新增
- 三层快速诊断：致命层/核心层/卫生层
- 失败案例库（16个案例，FC-001至FC-016）
- 多平台分发策略（TikTok/Reels/Shorts/Threads/Lemon8）

### 改进
- 工作流扩展为7阶段
- 提示词规范针对 Seedance 2.0 优化
- 阶梯式算力分配模型

---

## v2.14 (2025-12-01)

### 新增
- 实战案例库（成功/失败双轨）
- 产品追踪与爆款复盘模板

### 改进
- Hook体系扩充至40+变体
- 多语言生成策略初版

---

## v2.0 (2025-09-15)

### 新增
- 7阶段标准化工作流
- 原子化提示词规范
- 竞品拆解框架

---

## v1.0 (2025-06-01)

### 初始版本
- 基于即梦Seedance的视频生成Skill
- 基础Hook库和脚本生成
