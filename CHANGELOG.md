# 版本变更日志 (CHANGELOG)

> 本文档记录 TikTok Ad Video Skill 从初始版本至今的所有重要变更。
> 版本号遵循 [语义化版本](https://semver.org/lang/zh-CN/) 规范：主版本号.次版本号.修订号。


## [v2.5] - 2026-04-16

### 🚀 新增
- **社交货币分享体系**：在 `viral-hook-patterns.md` 中将分享引导话术升级为三类社交货币（展现品味型、展示专业型、圈层归属型），提升分享率预估。
- **原生感默认策略**：在 `SKILL.md` 和 `cinematic-vocabulary.md` 中将原生感（UGC风格）从可选词汇包升级为默认推荐风格，对齐 2026 AI 生成 UGC 广告趋势。
- **中英文混写提示词示例**：在 `prompt-examples.md` 中为每个示例增加混写版变体（中文意境 + 英文精准指令），充分利用 Seedance 2.0 的双语理解优势。
- **多模态参考素材指南**：在 `cinematic-vocabulary.md` 中新增“多模态参考素材准备指南”，指导用户上传风格参考图和动作参考视频。
- **Instagram 当日发布优先说明**：在 `platform-specs.md` 中增加 Meta 算法优先推荐当日发布内容的策略建议。

### 🔄 变更
- **修正 TikTok 分发逻辑**：在 `platform-specs.md` 和 `SKILL.md` 中将“粉丝优先测试”修正为“分阶段测试分发”（300-500 人测试池 → 更大流量池）。
- **强化 TikTok SEO 策略**：在 `platform-specs.md` 中增加标题、字幕关键词优化指南，对齐短视频成为 Z 世代首选搜索引擎的趋势。
- **分享引导话术全面升级**：从简单的 “Tag a friend” 扩展为三类社交货币体系，覆盖展现品味、展示专业、圈层归属场景。
- **关注度数据补充**：在 `SKILL.md` 核心铁律部分补充“关注度持续时间下降 69%”的数据，强化前 3 秒重要性。

### 📚 文档更新
- `SKILL.md` → v2.5
- `references/viral-hook-patterns.md` → v2.5
- `references/cinematic-vocabulary.md` → v2.5
- `references/platform-specs.md` → v2.5
- `examples/prompt-examples.md` → v2.5
- `README.md` → v2.5


## [v2.4] - 2026-04-16

### 🚀 新增
- **平台算法深度更新**：`references/platform-specs.md` 全面刷新，纳入 TikTok 粉丝优先测试、收藏/分享最高权重、TikTok 搜索信号、Meta UTIS 真实兴趣模型、YouTube Shorts 搜索过滤器等 2026 年最新算法规则。
- **收藏/分享引导成为核心互动策略**：明确收藏(Save)和分享(Share)为最高权重信号。

### 🔄 变更
- **运镜质感纳入技术质量评估**：`evaluation-rubric.md` 升级为“运镜质感与构图”。
- **评分维度重构**：将“进阶叙事”升级为“导演执行”(15分)，新增“五维架构执行度”(5分)。
- **算法信号细化**：拆分为“收藏引导力预估”和“分享引导力预估”各 5 分。

### 📚 文档更新
- `references/platform-specs.md` → v2.4
- `evaluation-rubric.md` → v2.3


## [v2.3] - 2026-04-16

### 🚀 新增
- **品类场景化多镜头模板**：功能效果型、高性价比型、情感共鸣型、极简结果型四大模板（3-4 镜头）。
- **五维提示词架构**：技术基底、镜头运动、视觉元素、光影系统、动态设计。
- **标准化运镜词库**：推拉摇移跟环绕等 7 种基础运镜及进阶组合。
- **原生感 (UGC风格) 词汇包**。
- **收藏/分享互动策略**。

### 🔄 变更
- **工作流升级**：阶段 2 升级为根据产品品类匹配多镜头叙事模板。
- **提示词示例全部重写**：采用五维架构并按品类匹配多镜头模板。
- **互动引导优先级调整**：从“点赞评论”全面转向“收藏+分享”优先。

### 📚 文档更新
- `SKILL.md` → v2.3
- `references/viral-hook-patterns.md` → v2.3
- `references/cinematic-vocabulary.md` → v2.3
- `examples/prompt-examples.md` → v2.3


## [v2.2] - 2026-04-15

### 🚀 新增
- **复播引导体系**：信息差、节奏中断、双重结局。
- **深度互动策略**：开放式提问、争议观点、求助式互动、投票式引导。
- **五维度评分体系**：新增“算法信号”维度（15分）。
- **出海本土化完全指南**：`references/localization-guide.md`。
- **广告创意测试完全指南**：`references/ad-campaign-testing.md`。

### 🔄 变更
- **评分维度重组**：技术质量20、爆款钩子30、平台适配20、进阶叙事15、算法信号15。
- **核心铁律升级**：新增“必须植入复播钩子”和“互动引导质量优先”。

### 📚 文档更新
- `SKILL.md` → v2.2
- `references/viral-hook-patterns.md` → v2.2
- `evaluation-rubric.md` → v2.2
- `references/localization-guide.md` → v1.0 (新增)
- `references/ad-campaign-testing.md` → v1.0 (新增)


## [v2.1] - 2026-04-14

### 🚀 新增
- **双镜头叙事语法**：多镜头切换指令。
- **音频同步指令**：重低音、轻快旋律、ASMR 触发等五类。
- **失败案例知识库**：`references/failure-case-library.md`。
- **A/B测试矩阵模板**：`references/ab-testing-matrix.md`。

### 🔄 变更
- **默认脚本结构升级**：核心铁律新增“默认双镜头结构”。
- **评分体系重构**：从三维度升级为四维度。
- **提示词示例全部重写**：升级为双镜头结构并融入音频同步指令。

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
- **2026 平台算法全面适配**：TikTok 互动权重更新、YouTube Shorts 关键词搜索、Meta Reels “真实兴趣”推荐。
- **Meta Advantage+ Creative 集成策略**。
- **爆款钩子特征库**：`references/viral-hook-patterns.md`，定义6大钩子类型。

### 🔄 变更
- **评分体系重构**：改为“技术质量(30) + 爆款钩子(40) + 平台适配(30)”。
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

**当前版本：v2.5**  
**最后更新：2026-04-16**
