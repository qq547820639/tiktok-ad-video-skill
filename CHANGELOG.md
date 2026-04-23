# 版本变更日志 (CHANGELOG)

> 本文档记录 TikTok Ad Video Skill 从初始版本至今的所有重要变更。
> 版本号遵循 [语义化版本](https://semver.org/lang/zh-CN/) 规范：主版本号.次版本号.修订号。


## [v2.10] - 2026-05-23

### 🚀 新增
- **内容形态决策节点（阶段 0.5）**：在 `SKILL.md` 工作流中新增内容形态分流逻辑，根据产品特性、目标市场、历史数据智能切换**直给型（15秒）**与**叙事型（45-60秒）**工作流。
- **叙事型软广剧本指南**：新建 `references/narrative-ad-playbook.md`，包含 5 种叙事模板（Mystery Object 悬念驱动型、Before You Judge 反转型、Adulting Win 成长叙事型、Secret Ingredient 秘密武器型、Routine Reveal 日常揭秘型）、美国市场“零提及”植入原则、评论区运营 Playbook、分段生成策略、叙事型专用数据迭代决策树。
- **故事型钩子（第 7 类钩子）**：在 `references/viral-hook-patterns.md` 中新增 5 种故事型钩子（Relatable Struggle、Mystery Object、Plot Twist、Unsolicited Win、Social Proof），覆盖叙事型软广的心理触发点与适用场景。
- **叙事型内容专项评估**：在 `references/evaluation-rubric.md` 中新增叙事型专项评分（悬念维持度 10 分、情绪弧线完整度 10 分、产品植入自然度 10 分、评论区引导力 10 分、零提及纪律 5 分，共 45 分），叙事型最终得分 = 五维分 + 专项分，满分 145 分。
- **美国 TikTok 评论区运营规则**：在 `references/platform-specs.md` 中新增 §四，包含评论区运营时间线、小号评论模板库（好奇心型/效果惊叹型/社交分享型/购买意向型）、主号回复话术库、铁律。
- **叙事型视频自查清单**：在 `references/self-check-checklist.md` 中新增 §三，覆盖钩子与悬念检查、产品植入检查（零提及纪律）、评论区准备、分段生成检查、叙事型专用数据反馈迭代动作。
- **叙事型案例**：在 `references/case-studies.md` 中新增铸铁元宝锅（美国市场）叙事型软广实战案例，含背景、策略、执行细节、提示词设计、评论区运营、预期数据。

### 🔄 变更
- **SKILL.md 工作流升级**：阶段 0.5 新增内容形态决策矩阵（账号粉丝量、产品使用效果、目标市场、历史数据、产品外观）；阶段 1-4 增加叙事型分支处理逻辑；阶段 6 增加叙事型专用决策树。
- **评分体系扩展**：`evaluation-rubric.md` 从单一 100 分制扩展为直给型 100 分制 + 叙事型 145 分制。
- **平台规格补充**：`platform-specs.md` 时长限制更新为“推荐 9-15s，叙事型 45-60s”；跨平台通投策略增加叙事型分段拼接说明。
- **自查清单重构**：`self-check-checklist.md` 拆分为通用检查项、直给型自查、叙事型自查三部分，叙事型增加零提及纪律、分段生成、评论区运营等专属检查项。
- **版本号统一**：`README.md`、`SKILL.md`、`viral-hook-patterns.md`、`evaluation-rubric.md`、`platform-specs.md`、`self-check-checklist.md` 统一至 v2.10。

### 📚 文档更新
- `SKILL.md` → v2.10
- `README.md` → v2.10
- `references/narrative-ad-playbook.md` → v1.0 (新增)
- `references/viral-hook-patterns.md` → v2.10
- `references/evaluation-rubric.md` → v2.10
- `references/platform-specs.md` → v2.10
- `references/self-check-checklist.md` → v2.10
- `references/case-studies.md` → v1.2 (新增叙事型案例)
- `CHANGELOG.md` → v2.10


## [v2.9] - 2026-05-22

### 🚀 新增
- **30秒极简加载指南**：在 `README.md` 开头新增极简版加载步骤。
- **引流强度选择模式**：在 `SKILL.md` 阶段4新增「软植入型」与「强引流型」两种引流策略。
- **实战案例集**：新增独立文档 `references/case-studies.md` (v1.1)，收录铸铁锅、鞋架、不锈钢盆、香水、小白鞋等 7 个品类的完整实战案例。
- **出海场景前置**：在 `README.md` 常见问题中新增“想生成英文/其他语言视频”入口。
- **批量生成模式说明**：在 `SKILL.md` 阶段0后增加批量生成提示。
- **提示词字数自检**：在 `SKILL.md` 阶段3增加即梦 AI 2000字符限制自动检查。
- **阶段 -1：竞品爆款拆解**：在 `SKILL.md` 阶段0之前新增可选阶段。
- **数据回传对话模板**：在 `references/data-driven-iteration.md` 中新增 §八。
- **产品图上传建议**：在 `SKILL.md` 阶段0增加引导用户上传产品实拍图的建议。

### 🔄 变更
- `SKILL.md` 工作流增强，`README.md` 结构优化，案例集版本迭代至 v1.1。

### 📚 文档更新
- `README.md` → v2.9
- `SKILL.md` → v2.9
- `references/case-studies.md` → v1.1
- `CHANGELOG.md` → v2.9


## [v2.8] - 2026-05-20

### 🚀 新增
- **声音钩子优先原则**：在 `SKILL.md` 核心铁律中新增“前 3 秒优先使用声音钩子（ASMR/音效/环境音），口播第 3 秒后才进入”。
- **品类钩子选型对照表（实战版）**：在 `viral-hook-patterns.md` 中新增 §二。
- **数据驱动迭代指南**：新增独立文档 `references/data-driven-iteration.md`。
- **发布前自查清单**：新增独立文档 `references/self-check-checklist.md`。
- **声音钩子执行度评分项**：在 `evaluation-rubric.md` 导演执行维度中新增“声音钩子执行度”子项（3 分）。

### 🔄 变更
- 多镜头模板融入声音策略，SKILL.md 工作流升级，评分表权重微调。

### 📚 文档更新
- `SKILL.md` → v2.8
- `README.md` → v2.8
- `evaluation-rubric.md` → v2.8
- `references/viral-hook-patterns.md` → v2.8
- `references/data-driven-iteration.md` → v1.0 (新增)
- `references/self-check-checklist.md` → v1.0 (新增)


## [v2.7] - 2026-05-19

### 🚀 新增
- **快速诊断决策树**：在 `SKILL.md` 开头新增决策树。
- **TikTok 垂直领域强化信号**：新增核心铁律，要求前5秒口述+字幕双重强化核心主题词。
- **AIGC 合规强制提醒**：阶段4新增独立合规区块。
- **YouTube Shorts 多平台分享加权**、**Meta Reels 当日发布优先深度策略**。
- **平台特性快速对照卡**、**垂直领域信号 A/B 测试模块**。
- **失败案例扩充至 16 个**：新增 FC-014/015/016。
- **多模态参考素材输入规范完善**、**TikTok Shop ACE 方法论落地操作指南**、**AIGC 标签地区差异说明**。

### 🔄 变更
- 评分维度微调，产品追踪模板字段增加。

### 📚 文档更新
- 全部核心文档 → v2.7


## [v2.6] - 2026-05-19

### 🚀 新增
- 版本号全面统一，TikTok 测试池精确化（200-500人），原生感升级为核心创作原则，社交货币 A/B 测试模块，Fast 模式全面集成，多模态参考数量明确，YouTube Shorts 划走率指标，Pinterest 多格式加权，失败案例扩充至 13 个，本土化指南升级。

### 🔄 变更
- 导演执行维度微调，产品追踪模板字段增加。

### 📚 文档更新
- 全部核心文档 → v2.6


## [v2.5] - 2026-04-16

### 🚀 新增
- 社交货币分享体系、原生感默认策略、中英文混写提示词示例、多模态参考素材指南、Instagram 当日发布优先说明。

### 🔄 变更
- 修正 TikTok 分发逻辑、强化 TikTok SEO 策略、分享引导话术全面升级。

### 📚 文档更新
- `SKILL.md`、`viral-hook-patterns.md`、`cinematic-vocabulary.md`、`platform-specs.md`、`prompt-examples.md`、`README.md` → v2.5


## [v2.4] - 2026-04-16

### 🚀 新增
- 平台算法深度更新：纳入 TikTok 粉丝优先测试、收藏/分享最高权重、Meta UTIS、YouTube Shorts 搜索过滤器等。

### 🔄 变更
- 运镜质感纳入技术质量评估，评分维度重构：“进阶叙事”升级为“导演执行”。

### 📚 文档更新
- `platform-specs.md` → v2.4，`evaluation-rubric.md` → v2.3


## [v2.3] - 2026-04-16

### 🚀 新增
- 品类场景化多镜头模板、五维提示词架构、标准化运镜词库、原生感词汇包。

### 🔄 变更
- 工作流升级，互动引导优先级调整。

### 📚 文档更新
- `SKILL.md`、`viral-hook-patterns.md`、`cinematic-vocabulary.md`、`prompt-examples.md` → v2.3


## [v2.2] - 2026-04-15

### 🚀 新增
- 复播引导体系、深度互动策略、五维度评分体系、出海本土化完全指南、广告创意测试完全指南。

### 🔄 变更
- 评分维度重组，核心铁律升级。

### 📚 文档更新
- `SKILL.md`、`viral-hook-patterns.md`、`evaluation-rubric.md` → v2.2
- `localization-guide.md`、`ad-campaign-testing.md` → v1.0 (新增)


## [v2.1] - 2026-04-14

### 🚀 新增
- 双镜头叙事语法、音频同步指令、失败案例知识库、A/B测试矩阵模板。

### 🔄 变更
- 默认脚本结构升级，评分体系重构。

### 📚 文档更新
- 全部核心文档 → v2.1
- `failure-case-library.md`、`ab-testing-matrix.md` → v1.0 (新增)


## [v2.0] - 2026-04-13

### 🚀 新增
- 2026 平台算法全面适配，Meta Advantage+ Creative 集成策略，爆款钩子特征库。

### 🔄 变更
- 评分体系重构，词汇表重构。

### 📚 文档结构建立


## [v1.0] - 2025-10-15

### 🎉 初始版本发布
- 核心工作流、基础钩子体系、基础评分表、实战验证。


## 版本号说明

| 版本类型 | 说明 | 示例 |
| :--- | :--- | :--- |
| **主版本号** | 重大架构变更，不兼容旧版 | v1.0 → v2.0（评分体系重构、新增钩子库） |
| **次版本号** | 功能新增，向下兼容 | v2.9 → v2.10（内容形态分流、叙事型软广、故事型钩子） |
| **修订号** | 问题修复、文档优化 | — |

---

**当前版本：v2.10**  
**最后更新：2026-05-23**
