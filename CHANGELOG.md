# 版本变更日志 (CHANGELOG)

> 本文档记录 TikTok Ad Video Skill 从初始版本至今的所有重要变更。
> 版本号遵循 [语义化版本](https://semver.org/lang/zh-CN/) 规范：主版本号.次版本号.修订号。


## [v2.13] - 2026-04-23

### 🚀 新增
- **阶段 -2：实时趋势扫描**：在 `SKILL.md` 工作流中新增趋势感知环节，AI 基于知识库及用户输入输出当前品类热门音频、流行格式、热门标签，确保钩子选择踩中趋势红利。
- **三维匹配矩阵（品类×钩子×趋势）**：在 `viral-hook-patterns.md` 的品类选型表中新增「趋势适配建议」列，AI 选择钩子时需同步输出推荐钩子+声音策略+趋势标签。
- **钩子模板变体库**：每个钩子类型提供 5-10 个变体句式（共 40+ 变体），AI 生成时随机选取或轮换，避免连续 3 条视频使用相同句式导致模板化限流。
- **阶段 4.5：TikTok Shop 转化策略**：新增可选阶段，输出商品卡挂载建议、评论区购物引导话术、直播间引流钩子及 Pixel 追踪提醒，打通从视频到转化的全链路。
- **数据校准闭环落地**：新增 `references/calibration-guide.md`，提供结构化数据收集模板、Google Sheets 相关系数计算法、Python 自动化脚本，将“动态权重校准”从概念变为可执行方案。
- **竞品分析结构化模板**：新增 `references/competitor-analysis-template.md`，包含单视频拆解表、多视频共性提取框架、差异化策略生成器。
- **内容日历与生产排期模板**：新增 `references/content-calendar-template.md`，提供单产品测试期日历、多产品月度矩阵、A/B 测试专项排期。
- **SKILL-lite.md 精简版**：新增 `SKILL-lite.md`，仅包含核心工作流、评分表和钩子选型表，Token 消耗减少约 60%，覆盖 80% 常见使用场景。
- **趋势信号反馈机制**：在 `SKILL.md` 阶段 6 新增趋势信号效果追踪，某趋势标签/音频持续带来高完播率则提升为该品类默认推荐。

### 🔄 变更
- **钩子匹配逻辑升级**：从二维（品类×钩子）升级为三维（品类×钩子×趋势），`viral-hook-patterns.md` 品类选型表结构同步更新。
- **变体随机化规则**：`SKILL.md` 阶段 1 明确要求从变体库随机选取或轮换钩子文案，并增加去模板化自检告警（连续 3 条相同句式自动提醒）。
- **模式决策矩阵量化**：在 `SKILL.md` 成本控制章节增加 Fast/Standard 模式选择的具体场景与阈值（冷启动用 Fast，完播率>50%且收藏率>10%后切换 Standard 复制）。
- **校准闭环从概念变可执行**：`SKILL.md` 阶段 6 增加引导用户记录数据至追踪表、数据量达标后主动提醒校准、AI 辅助计算相关系数等具体动作。
- **评论运营策略合规化**：`platform-specs.md` 评论区运营章节增加合规风险声明，并补充“无小号冷启动替代方案”（开放式提问、争议性观点、求助式互动）。
- **叙事型评分体系统一**：`narrative-ad-playbook.md` 中的评分标准和发布阈值与 `evaluation-rubric.md` v2.12 对齐（145 分制，≥110 分发布）。
- **提示词版本管理**：`SKILL.md` 阶段 3 自动为每条提示词附加版本号（如 `PROMPT_v1_产品_钩子_日期`），并记录于追踪表。

### 📚 文档更新
- `SKILL.md` → v2.13
- `references/viral-hook-patterns.md` → v2.13
- `references/calibration-guide.md` → v1.0（新增）
- `references/competitor-analysis-template.md` → v1.0（新增）
- `references/content-calendar-template.md` → v1.0（新增）
- `SKILL-lite.md` → v1.0（新增）
- `references/narrative-ad-playbook.md` → v1.1（评分对齐）
- `references/platform-specs.md` → v2.11（合规声明+无小号方案）
- `CHANGELOG.md` → v2.13


## [v2.12] - 2026-04-23

### 🚀 新增
- **评分表分档阈值**：在 `evaluation-rubric.md` 中，将 Prompt 预评估结果细化为四档（优秀/合格/需小修/需大修），替代简单二值判断。
- **非线性惩罚规则**：钩子强度(H)或声音策略(A)低于 50 分时，评级自动降一档，确保核心要素不被平均。
- **评分表动态校准机制（后台）**：在 `SKILL.md` 阶段 6 中新增数据记录与回归校准逻辑，样本量 ≥50 条时自动计算优化权重。

### 🔄 变更
- `evaluation-rubric.md` 新增 §1.3 分档阈值表与非线性惩罚说明。
- `SKILL.md` 阶段 3.5 增加四档评级输出格式，阶段 6 增加权重动态校准逻辑。
- 版本号统一至 v2.12。

### 📚 文档更新
- `references/evaluation-rubric.md` → v2.12
- `SKILL.md` → v2.12
- `CHANGELOG.md` → v2.12


## [v2.11] - 2026-04-23

### 🚀 新增
- **阶段 3.5：Prompt 文本预评估（积分风控闸门）**：在消耗即梦 AI 积分前强制对 Prompt 五维度打分，≥80 分才允许提交生成视频。
- **Prompt 文本质量评分表**：在 `evaluation-rubric.md` 中新增独立章节，覆盖前 3 秒钩子强度(30分)、声音策略明确度(25分)、垂直领域信号(20分)、原生感设计(15分)、去 AI 味指令完整性(10分)。

### 🔄 变更
- `SKILL.md` 工作流图新增阶段 3.5 节点与迭代循环路径。
- 核心铁律新增“先验证、后投入”。
- 自检报告增加 Prompt 预评估分数检查项。

### 📚 文档更新
- `SKILL.md` → v2.11
- `references/evaluation-rubric.md` → v2.11


## [v2.10] - 2026-04-23

### 🚀 新增
- **内容形态决策节点（阶段 0.5）**：智能切换直给型(15秒)与叙事型(45-60秒)。
- **叙事型软广剧本指南**：新建 `references/narrative-ad-playbook.md`，包含 5 种叙事模板、“零提及”原则、评论区运营 Playbook、分段生成策略。
- **故事型钩子（第 7 类钩子）**：在 `viral-hook-patterns.md` 中新增 5 种故事型钩子。
- **叙事型内容专项评估**：在 `evaluation-rubric.md` 中新增叙事型专项评分（45 分），满分 145 分。
- **美国 TikTok 评论区运营规则**：在 `platform-specs.md` 中新增 §四。
- **叙事型视频自查清单**：在 `self-check-checklist.md` 中新增 §三。

### 🔄 变更
- `SKILL.md` 工作流升级，评分体系扩展，平台规格补充。
- 版本号统一至 v2.10。

### 📚 文档更新
- `SKILL.md` → v2.10
- `references/narrative-ad-playbook.md` → v1.0 (新增)
- `references/viral-hook-patterns.md` → v2.10
- `references/evaluation-rubric.md` → v2.10
- `references/platform-specs.md` → v2.10
- `references/self-check-checklist.md` → v2.10


## [v2.9] - 2026-04-22

### 🚀 新增
- **30秒极简加载指南**：`README.md` 开头。
- **引流强度选择模式**：`SKILL.md` 阶段4。
- **实战案例集**：`references/case-studies.md` (v1.1)。
- **出海场景前置**、**批量生成模式说明**、**提示词字数自检**、**阶段 -1：竞品爆款拆解**、**数据回传对话模板**、**产品图上传建议**。

### 🔄 变更
- `SKILL.md` 工作流增强，`README.md` 结构优化。

### 📚 文档更新
- `README.md` → v2.9
- `SKILL.md` → v2.9
- `references/case-studies.md` → v1.1


## [v2.8] - 2026-04-20

### 🚀 新增
- **声音钩子优先原则**、**品类钩子选型对照表**、**数据驱动迭代指南**、**发布前自查清单**、**声音钩子执行度评分项**。

### 🔄 变更
- 多镜头模板融入声音策略，SKILL.md 工作流升级，评分表权重微调。

### 📚 文档更新
- 核心文档 → v2.8，新增 `data-driven-iteration.md`、`self-check-checklist.md`。


## [v2.7] - 2026-04-19

### 🚀 新增
- 快速诊断决策树、TikTok 垂直领域强化信号、AIGC 合规强制提醒、YouTube Shorts 多平台分享加权、Meta Reels 当日发布优先深度策略、平台特性快速对照卡、垂直领域信号 A/B 测试模块、失败案例扩充至 16 个、多模态参考规范、ACE 方法论落地指南、AIGC 标签地区差异。

### 🔄 变更
- 评分维度微调，产品追踪模板字段增加。

### 📚 文档更新
- 全部核心文档 → v2.7


## [v2.6] - 2026-04-19

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


## [v1.0] - 2026-04-13

### 🎉 初始版本发布
- 核心工作流、基础钩子体系、基础评分表、实战验证。


## 版本号说明

| 版本类型 | 说明 | 示例 |
| :--- | :--- | :--- |
| **主版本号** | 重大架构变更，不兼容旧版 | v1.0 → v2.0（评分体系重构、新增钩子库） |
| **次版本号** | 功能新增，向下兼容 | v2.12 → v2.13（趋势扫描、TikTok Shop转化、变体库、校准闭环） |
| **修订号** | 问题修复、文档优化 | — |

---

**当前版本：v2.13**  
**最后更新：2026-04-23**
