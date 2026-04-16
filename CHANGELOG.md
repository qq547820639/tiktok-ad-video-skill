# 版本变更日志 (CHANGELOG)

> 本文档记录 TikTok Ad Video Skill 从初始版本至今的所有重要变更。
> 版本号遵循 [语义化版本](https://semver.org/lang/zh-CN/) 规范：主版本号.次版本号.修订号。


## [v2.7] - 2026-05-19

### 🚀 新增
- **快速诊断决策树**：在 `SKILL.md` 开头新增决策树，用户可根据问题直接跳转到对应章节（测试池突破、完播率低、收藏率低、分享率低、AI味重、画面单调、广告投放、出海、Fast模式）。
- **TikTok 垂直领域强化信号**：在 `SKILL.md` 核心铁律中新增“垂直领域信号强化”，要求前5秒口述+字幕双重强化核心主题词。`viral-hook-patterns.md` 所有脚本模板强制融入垂直领域信号，`evaluation-rubric.md` 新增“垂直领域信号执行度”子项（3分）。
- **AIGC 合规强制提醒**：在 `SKILL.md` 阶段4新增独立合规区块，发布时强制提醒勾选各平台 AI 标签（TikTok: AI-generated、Meta: Made with AI、YouTube: Altered content）。`platform-specs.md` 新增各平台 AIGC 标签要求，`failure-case-library.md` 新增 FC-015（AIGC标签未勾选限流）。
- **YouTube Shorts 多平台分享加权**：在 `SKILL.md` 和 `platform-specs.md` 中新增引导观众跨平台分享策略，获取额外算法加权。
- **Meta Reels 当日发布优先深度策略**：在 `SKILL.md` 核心铁律中新增“Meta Reels 当日发布优先”，建议每日1-3条分散发布，最大化获取 50%+ 额外分发权重。
- **平台特性快速对照卡**：在 `platform-specs.md` 开头新增一句话总结对照卡，便于快速查阅各平台核心信号、关键动作和 AIGC 标签要求。
- **垂直领域信号 A/B 测试模块**：在 `ab-testing-matrix.md` 中新增模板2.5（垂直领域信号对比测试）和模板3.2（原生感 × 垂直领域信号交叉测试）。
- **失败案例扩充至 16 个**：新增 FC-014（垂直领域信号缺失，流量不精准）、FC-015（AIGC标签未勾选限流）、FC-016（YouTube Shorts 划走率过高）。
- **多模态参考素材输入规范完善**：在 `cinematic-vocabulary.md` 中补充参考素材格式、分辨率要求及最佳组合建议（全要素控制：1风格图+1产品图+1动作视频）。
- **TikTok Shop ACE 方法论落地操作指南**：在 `localization-guide.md` 中新增三场域联动本土化指南（达人内容场、商家内容场、商城&搜索场）及投流策略简报模板。
- **AIGC 标签地区差异说明**：在 `localization-guide.md` 中新增各市场 AIGC 合规要求对照表（美国、欧盟、中东、东南亚、日本、韩国）。

### 🔄 变更
- **评分维度微调**：`evaluation-rubric.md` 中平台适配新增垂直领域信号评估，TikTok 深度互动与垂直领域合并为4分，YouTube Shorts 适配调整为4分（增加划走率考量），Pinterest 适配调整为3分。导演执行维度新增垂直领域信号执行度3分，多镜头结构、音频同步、转场质量各调整为2分。
- **平台适配评分细化**：`evaluation-rubric.md` 中 YouTube Shorts 适配增加划走率预估和多平台分享引导评估。
- **产品追踪模板字段增加**：`product-tracker-template.md` 新增核心主题词、垂直领域信号执行度、AIGC 合规状态、YouTube 划走率等字段。
- **A/B 测试模板扩展**：`ab-testing-matrix.md` 新增垂直领域信号对比测试、原生感×垂直领域信号交叉测试，补充 AIGC 合规对测试影响说明。
- **广告测试指南更新**：`ad-campaign-testing.md` 新增 AIGC 合规对广告测试的影响章节，补充垂直领域信号对广告素材的 CTR 提升数据。
- **本土化指南升级**：`localization-guide.md` 新增垂直领域信号本土化章节（§5.4），提供各市场主题词对照表。

### 📚 文档更新
- `SKILL.md` → v2.7
- `README.md` → v2.7
- `evaluation-rubric.md` → v2.7
- `references/platform-specs.md` → v2.7
- `references/viral-hook-patterns.md` → v2.7
- `references/cinematic-vocabulary.md` → v2.7
- `examples/prompt-examples.md` → v2.7
- `product-tracker-template.md` → v2.7
- `references/failure-case-library.md` → v2.7
- `references/ab-testing-matrix.md` → v2.7
- `references/ad-campaign-testing.md` → v2.7
- `references/localization-guide.md` → v2.7


## [v2.6] - 2026-05-19

### 🚀 新增
- **版本号全面统一**：所有核心文档统一至 v2.6。
- **TikTok 测试池精确化**：将分发逻辑精确为“约 200-500 人小批量测试池”，补充算法月度迭代频率。
- **原生感升级为核心创作原则**：在核心铁律中新增“原生感优先”，评分表新增“原生感执行度”子项。
- **社交货币 A/B 测试模块**：新增社交货币话术对比测试模板。
- **Fast 模式全面集成**：新增 Fast 模式提示词技巧章节，增加精简版示例。
- **多模态参考数量明确**：明确 Seedance 2.0 最多支持 9 张图片、3 个视频、3 个音频。
- **YouTube Shorts 划走率指标**：新增划走率作为关键负向指标。
- **Pinterest 多格式加权**：补充多格式创作者额外曝光加权策略。
- **失败案例扩充至 13 个**：新增测试池突破失败、原生感不足、Fast 模式画质下降案例。
- **本土化指南升级**：对齐 TikTok Shop ACE 方法论，新增多模态参考素材本土化策略。

### 🔄 变更
- **导演执行维度微调**：五维架构4分，原生感3分，多镜头3分，音频2分，转场3分。
- **产品追踪模板字段增加**：新增原生感启用、Fast模式成本、社交货币分享类型等字段。

### 📚 文档更新
- 全部核心文档 → v2.6


## [v2.5] - 2026-04-16

### 🚀 新增
- **社交货币分享体系**：分享引导升级为三类社交货币。
- **原生感默认策略**：原生感从可选升级为默认推荐。
- **中英文混写提示词示例**：每个示例增加混写版变体。
- **多模态参考素材指南**：新增准备指南。
- **Instagram 当日发布优先说明**：增加策略建议。

### 🔄 变更
- **修正 TikTok 分发逻辑**：从“粉丝优先”修正为“分阶段测试分发”。
- **强化 TikTok SEO 策略**：增加标题、字幕关键词优化指南。
- **分享引导话术全面升级**：从简单 Tag 扩展为三类社交货币体系。

### 📚 文档更新
- `SKILL.md`、`viral-hook-patterns.md`、`cinematic-vocabulary.md`、`platform-specs.md`、`prompt-examples.md`、`README.md` → v2.5


## [v2.4] - 2026-04-16

### 🚀 新增
- **平台算法深度更新**：纳入 TikTok 粉丝优先测试、收藏/分享最高权重、Meta UTIS、YouTube Shorts 搜索过滤器等。

### 🔄 变更
- **运镜质感纳入技术质量评估**。
- **评分维度重构**：“进阶叙事”升级为“导演执行”，新增“五维架构执行度”。

### 📚 文档更新
- `platform-specs.md` → v2.4
- `evaluation-rubric.md` → v2.3


## [v2.3] - 2026-04-16

### 🚀 新增
- **品类场景化多镜头模板**：四大模板（3-4 镜头）。
- **五维提示词架构**：技术基底、镜头运动、视觉元素、光影系统、动态设计。
- **标准化运镜词库**：7 种基础运镜及进阶组合。
- **原生感 (UGC风格) 词汇包**。

### 🔄 变更
- **工作流升级**：阶段 2 升级为品类匹配多镜头模板。
- **互动引导优先级调整**：转向“收藏+分享”优先。

### 📚 文档更新
- `SKILL.md`、`viral-hook-patterns.md`、`cinematic-vocabulary.md`、`prompt-examples.md` → v2.3


## [v2.2] - 2026-04-15

### 🚀 新增
- **复播引导体系**：信息差、节奏中断、双重结局。
- **深度互动策略**：四类深度评论激发策略。
- **五维度评分体系**：新增“算法信号”维度。
- **出海本土化完全指南**、**广告创意测试完全指南**。

### 🔄 变更
- **评分维度重组**：五维度（技术质量20、爆款钩子30、平台适配20、进阶叙事15、算法信号15）。

### 📚 文档更新
- `SKILL.md`、`viral-hook-patterns.md`、`evaluation-rubric.md` → v2.2
- `localization-guide.md`、`ad-campaign-testing.md` → v1.0 (新增)


## [v2.1] - 2026-04-14

### 🚀 新增
- **双镜头叙事语法**、**音频同步指令**。
- **失败案例知识库**、**A/B测试矩阵模板**。

### 🔄 变更
- **默认脚本结构升级**：核心铁律新增“默认双镜头结构”。
- **评分体系重构**：从三维度升级为四维度。

### 📚 文档更新
- 全部核心文档 → v2.1
- `failure-case-library.md`、`ab-testing-matrix.md` → v1.0 (新增)


## [v2.0] - 2026-04-13

### 🚀 新增
- **2026 平台算法全面适配**。
- **Meta Advantage+ Creative 集成策略**。
- **爆款钩子特征库**：6大钩子类型。

### 🔄 变更
- **评分体系重构**：技术质量(30) + 爆款钩子(40) + 平台适配(30)。
- **词汇表重构**：新增爆款前缀、去AI味指令、负面词表。

### 📚 文档结构建立
```
tiktok-ad-video-skill/
├── SKILL.md (v2.0)
├── README.md (v2.0)
├── evaluation-rubric.md (v2.0)
├── product-tracker-template.md (v2.0)
├── examples/prompt-examples.md (v2.0)
└── references/
    ├── viral-hook-patterns.md (v2.0)
    ├── cinematic-vocabulary.md (v2.0)
    └── platform-specs.md (v2.0)
```


## [v1.0] - 2025-10-15

### 🎉 初始版本发布
- **核心工作流**：选品预判 → 15秒脚本 → Seedance 2.0提示词 → 质量评估 → 数据回流
- **基础钩子体系**：3种钩子类型
- **基础评分表**：8维度评分（40分制）
- **支持平台**：TikTok、Meta Reels、YouTube Shorts
- **实战验证**：经过80+条视频、8+个生产日打磨


## 版本号说明

| 版本类型 | 说明 | 示例 |
| :--- | :--- | :--- |
| **主版本号** | 重大架构变更，不兼容旧版 | v1.0 → v2.0（评分体系重构、新增钩子库） |
| **次版本号** | 功能新增，向下兼容 | v2.0 → v2.1（双镜头语法、音频同步） |
| **修订号** | 问题修复、文档优化 | v2.6 → v2.7（垂直领域信号、AIGC合规、决策树） |

---

**当前版本：v2.7**  
**最后更新：2026-05-19**
