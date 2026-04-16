# 版本变更日志 (CHANGELOG)

> 本文档记录 TikTok Ad Video Skill 从初始版本至今的所有重要变更。
> 版本号遵循 [语义化版本](https://semver.org/lang/zh-CN/) 规范：主版本号.次版本号.修订号。


## [v2.6] - 2026-05-19

### 🚀 新增
- **版本号全面统一**：所有核心文档统一至 v2.6，消除版本不一致问题（`evaluation-rubric.md`、`product-tracker-template.md` 从 v2.3/v2.4 升级至 v2.6）。
- **TikTok 测试池精确化**：在 `SKILL.md` 和 `platform-specs.md` 中，将分发逻辑精确为“约 200-500 人小批量测试池”，并补充算法月度迭代频率说明。
- **原生感升级为核心创作原则**：在 `SKILL.md` 核心铁律中新增“原生感优先”，`evaluation-rubric.md` 新增“原生感执行度”子项（3分），`viral-hook-patterns.md` 所有脚本强制融入原生感策略。
- **社交货币 A/B 测试模块**：在 `ab-testing-matrix.md` 中新增社交货币话术对比测试模板（展现品味型/展示专业型/圈层归属型）。
- **Fast 模式全面集成**：在 `cinematic-vocabulary.md` 中新增 Fast 模式提示词技巧章节，`SKILL.md` 和 `prompt-examples.md` 增加 Fast 模式精简版示例，`ad-campaign-testing.md` 增加 Fast 模式素材测试策略。
- **多模态参考数量明确**：在 `cinematic-vocabulary.md` 中明确 Seedance 2.0 最多支持 9 张图片、3 个视频、3 个音频作为参考。
- **YouTube Shorts 划走率指标**：在 `platform-specs.md` 和 `evaluation-rubric.md` 中新增划走率作为关键负向指标。
- **Pinterest 多格式加权**：在 `platform-specs.md` 中补充 2026 年 3 月多格式创作者额外曝光加权策略。
- **失败案例扩充至 13 个**：在 `failure-case-library.md` 中新增 FC-011（测试池突破失败）、FC-012（原生感不足）、FC-013（Fast 模式画质下降）。
- **本土化指南升级**：在 `localization-guide.md` 中对齐 TikTok Shop ACE 方法论，新增多模态参考素材本土化策略和投流策略简报模板。

### 🔄 变更
- **导演执行维度微调**：`evaluation-rubric.md` 中五维架构执行度调整为 4 分，原生感执行度新增 3 分，多镜头结构调整为 3 分，音频同步调整为 2 分，转场质量保持 3 分。
- **平台适配评分细化**：`evaluation-rubric.md` 中 YouTube Shorts 适配增加划走率考量。
- **产品追踪模板字段增加**：`product-tracker-template.md` 新增原生感启用、Fast模式成本、社交货币分享类型等字段。
- **A/B 测试模板扩展**：`ab-testing-matrix.md` 新增原生感策略对比测试、Fast vs 标准模式成本效益测试。

### 📚 文档更新
- `SKILL.md` → v2.6
- `README.md` → v2.6
- `evaluation-rubric.md` → v2.6
- `references/platform-specs.md` → v2.6
- `references/viral-hook-patterns.md` → v2.6
- `references/cinematic-vocabulary.md` → v2.6
- `examples/prompt-examples.md` → v2.6
- `product-tracker-template.md` → v2.6
- `references/failure-case-library.md` → v2.6
- `references/ab-testing-matrix.md` → v2.6
- `references/ad-campaign-testing.md` → v2.6
- `references/localization-guide.md` → v2.6


## [v2.5] - 2026-04-16

### 🚀 新增
- **社交货币分享体系**：在 `viral-hook-patterns.md` 中将分享引导升级为三类社交货币。
- **原生感默认策略**：在 `SKILL.md` 和 `cinematic-vocabulary.md` 中将原生感从可选升级为默认推荐。
- **中英文混写提示词示例**：在 `prompt-examples.md` 中为每个示例增加混写版变体。
- **多模态参考素材指南**：在 `cinematic-vocabulary.md` 中新增准备指南。
- **Instagram 当日发布优先说明**：在 `platform-specs.md` 中增加策略建议。

### 🔄 变更
- **修正 TikTok 分发逻辑**：从“粉丝优先”修正为“分阶段测试分发”。
- **强化 TikTok SEO 策略**：增加标题、字幕关键词优化指南。
- **分享引导话术全面升级**：从简单 Tag 扩展为三类社交货币体系。
- **关注度数据补充**：补充“关注度持续时间下降 69%”数据。

### 📚 文档更新
- `SKILL.md` → v2.5
- `references/viral-hook-patterns.md` → v2.5
- `references/cinematic-vocabulary.md` → v2.5
- `references/platform-specs.md` → v2.5
- `examples/prompt-examples.md` → v2.5
- `README.md` → v2.5


## [v2.4] - 2026-04-16

### 🚀 新增
- **平台算法深度更新**：纳入 TikTok 粉丝优先测试、收藏/分享最高权重、Meta UTIS、YouTube Shorts 搜索过滤器等。
- **收藏/分享成为核心互动策略**。

### 🔄 变更
- **运镜质感纳入技术质量评估**。
- **评分维度重构**：“进阶叙事”升级为“导演执行”，新增“五维架构执行度”。
- **算法信号细化**：拆分为收藏引导力预估和分享引导力预估。

### 📚 文档更新
- `references/platform-specs.md` → v2.4
- `evaluation-rubric.md` → v2.3


## [v2.3] - 2026-04-16

### 🚀 新增
- **品类场景化多镜头模板**：四大模板（3-4 镜头）。
- **五维提示词架构**：技术基底、镜头运动、视觉元素、光影系统、动态设计。
- **标准化运镜词库**：7 种基础运镜及进阶组合。
- **原生感 (UGC风格) 词汇包**。
- **收藏/分享互动策略**。

### 🔄 变更
- **工作流升级**：阶段 2 升级为品类匹配多镜头模板。
- **提示词示例全部重写**：采用五维架构。
- **互动引导优先级调整**：转向“收藏+分享”优先。

### 📚 文档更新
- `SKILL.md` → v2.3
- `references/viral-hook-patterns.md` → v2.3
- `references/cinematic-vocabulary.md` → v2.3
- `examples/prompt-examples.md` → v2.3


## [v2.2] - 2026-04-15

### 🚀 新增
- **复播引导体系**：信息差、节奏中断、双重结局。
- **深度互动策略**：四类深度评论激发策略。
- **五维度评分体系**：新增“算法信号”维度。
- **出海本土化完全指南**。
- **广告创意测试完全指南**。

### 🔄 变更
- **评分维度重组**：五维度（技术质量20、爆款钩子30、平台适配20、进阶叙事15、算法信号15）。
- **核心铁律升级**：新增复播钩子和互动引导质量优先。

### 📚 文档更新
- `SKILL.md` → v2.2
- `references/viral-hook-patterns.md` → v2.2
- `evaluation-rubric.md` → v2.2
- `references/localization-guide.md` → v1.0 (新增)
- `references/ad-campaign-testing.md` → v1.0 (新增)


## [v2.1] - 2026-04-14

### 🚀 新增
- **双镜头叙事语法**：多镜头切换指令。
- **音频同步指令**：五类音频同步指令。
- **失败案例知识库**：`failure-case-library.md`。
- **A/B测试矩阵模板**：`ab-testing-matrix.md`。

### 🔄 变更
- **默认脚本结构升级**：核心铁律新增“默认双镜头结构”。
- **评分体系重构**：从三维度升级为四维度。
- **提示词示例全部重写**：升级为双镜头结构并融入音频同步。

### 📚 文档更新
- `SKILL.md` → v2.1
- `references/viral-hook-patterns.md` → v2.1
- `references/cinematic-vocabulary.md` → v2.1
- `references/platform-specs.md` → v2.1
- `evaluation-rubric.md` → v2.1
- `examples/prompt-examples.md` → v2.1
- `references/failure-case-library.md` → v1.0 (新增)
- `references/ab-testing-matrix.md` → v1.0 (新增)


## [v2.0] - 2026-04-13

### 🚀 新增
- **2026 平台算法全面适配**。
- **Meta Advantage+ Creative 集成策略**。
- **爆款钩子特征库**：6大钩子类型。

### 🔄 变更
- **评分体系重构**：技术质量(30) + 爆款钩子(40) + 平台适配(30)。
- **成本控制强化**：明确“禁止盲测”。
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
| **修订号** | 问题修复、文档优化 | v2.2 → v2.3（品类多镜头模板、五维架构） |

---

**当前版本：v2.6**  
**最后更新：2026-05-19**
