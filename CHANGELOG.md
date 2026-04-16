# 版本变更日志 (CHANGELOG)

> 本文档记录 TikTok Ad Video Skill 从初始版本至今的所有重要变更。
> 版本号遵循 [语义化版本](https://semver.org/lang/zh-CN/) 规范：主版本号.次版本号.修订号。


## [v2.4] - 2026-04-16

### 🚀 新增
- **平台算法深度更新**：`references/platform-specs.md` 全面刷新，纳入 TikTok 粉丝优先测试、收藏/分享最高权重、TikTok 搜索信号、Meta UTIS 真实兴趣模型、YouTube Shorts 搜索过滤器等 2026 年最新算法规则。
- **收藏/分享引导成为核心互动策略**：明确收藏(Save)和分享(Share)为最高权重信号，在每个脚本模板中强制植入收藏和分享引导话术。

### 🔄 变更
- **运镜质感纳入技术质量评估**：`evaluation-rubric.md` 中将原“运镜流畅度”升级为“运镜质感与构图”，强调镜头运动指令的执行精准度。
- **评分维度重构**：将“进阶叙事”升级为“导演执行”(15分)，新增“五维架构执行度”(5分)作为核心评估项。
- **算法信号细化**：将原“互动质量预估”拆分为“收藏引导力预估”和“分享引导力预估”各 5 分。
- **失败模式扩充**：新增运镜质感差、五维架构缺失、收藏率低、分享率低等修复方案。

### 📚 文档更新
- `references/platform-specs.md` → v2.4
- `evaluation-rubric.md` → v2.3


## [v2.3] - 2026-04-16

### 🚀 新增
- **品类场景化多镜头模板**：在 `references/viral-hook-patterns.md` 中，将一刀切的“通用双镜头”升级为功能效果型、高性价比型、情感共鸣型、极简结果型四大多镜头叙事模板（3-4 镜头）。
- **五维提示词架构**：在 `references/cinematic-vocabulary.md` 中引入结构化提示词体系，从技术基底、镜头运动、视觉元素、光影系统、动态设计五个维度独立控制视频生成。
- **标准化运镜词库**：新增推、拉、摇、移、跟、环绕、升降等 7 种基础运镜及进阶组合指令。
- **原生感 (UGC风格) 词汇包**：为对齐 2026 真实化内容趋势，新增素人演员、生活化场景、手持自拍感等专属词汇。
- **收藏/分享互动策略**：为每个钩子设计专属的收藏引导语和分享引导语，对齐 2026 最高权重信号。

### 🔄 变更
- **工作流升级**：`SKILL.md` 阶段 2 升级为根据产品品类匹配多镜头叙事模板。
- **提示词示例全部重写**：`examples/prompt-examples.md` 全部 6 个示例采用五维架构并按品类匹配多镜头模板。
- **互动引导优先级调整**：从“点赞评论”全面转向“收藏+分享”优先。
- **评分卡字段增加**：新增产品品类、镜头模板、镜头数量字段。

### 📚 文档更新
- `SKILL.md` → v2.3
- `references/viral-hook-patterns.md` → v2.3
- `references/cinematic-vocabulary.md` → v2.3
- `examples/prompt-examples.md` → v2.3


## [v2.2] - 2026-04-15

### 🚀 新增
- **复播引导体系**：在 `viral-hook-patterns.md` 中新增复播彩蛋设计技巧（信息差、节奏中断、双重结局）。
- **深度互动策略**：新增开放式提问、争议观点、求助式互动、投票式引导四类深度评论激发策略。
- **五维度评分体系**：`evaluation-rubric.md` 新增“算法信号”维度（15分），含复播率预估、互动质量预估、收藏/分享引导力。
- **出海本土化完全指南**：新增 `references/localization-guide.md`。
- **广告创意测试完全指南**：新增 `references/ad-campaign-testing.md`。

### 🔄 变更
- **评分维度重组**：从四维度升级为五维度（技术质量20、爆款钩子30、平台适配20、进阶叙事15、算法信号15）。
- **核心铁律升级**：新增“必须植入复播钩子”和“互动引导质量优先”。
- **工作流增强**：阶段2增加复播彩蛋植入点设计，阶段3提示词模板加入复播引导指令。

### 📚 文档更新
- `SKILL.md` → v2.2
- `references/viral-hook-patterns.md` → v2.2
- `evaluation-rubric.md` → v2.2
- `references/localization-guide.md` → v1.0 (新增)
- `references/ad-campaign-testing.md` → v1.0 (新增)


## [v2.1] - 2026-04-14

### 🚀 新增
- **双镜头叙事语法**：在 `cinematic-vocabulary.md` 中新增多镜头切换指令。
- **音频同步指令**：新增重低音、轻快旋律、ASMR 触发等五类音频同步指令。
- **失败案例知识库**：新增 `references/failure-case-library.md`。
- **A/B测试矩阵模板**：新增 `references/ab-testing-matrix.md`。

### 🔄 变更
- **默认脚本结构升级**：核心铁律新增“默认双镜头结构”。
- **评分体系重构**：从三维度升级为四维度（技术质量25、爆款钩子35、平台适配25、进阶叙事15）。
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
- **成本控制强化**：明确“禁止盲测”，必须先经过钩子图文三选一验证。
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
- **基础钩子体系**：3种钩子类型（价格锚定、生活转变、科技展示）
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

**当前版本：v2.3 / v2.4 (部分文档)**  
**最后更新：2026-04-16**
