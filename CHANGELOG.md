# 版本变更日志 (CHANGELOG)

> 本文档记录 TikTok Ad Video Skill 从初始版本至今的所有重要变更。
> 版本号遵循 [语义化版本](https://semver.org/lang/zh-CN/) 规范：主版本号.次版本号.修订号。

---

## [v2.2] - 2026-04-15

### 🚀 新增
- **复播引导体系**：在 `viral-hook-patterns.md` 中新增复播彩蛋设计技巧（信息差、节奏中断、双重结局），并在各钩子脚本中植入具体实施方案。
- **深度互动策略**：新增开放式提问、争议观点、求助式互动、投票式引导四类深度评论激发策略。
- **收藏/分享引导技巧**：新增实用价值锚定、社交货币、信息差独占三类引导方法。
- **五维度评分体系**：`evaluation-rubric.md` 新增“算法信号”维度（15分），含复播率预估、互动质量预估、收藏/分享引导力三个子项。

### 🔄 变更
- **评分维度重组**：`evaluation-rubric.md` 评分从四维度升级为五维度（技术质量20分、爆款钩子30分、平台适配20分、进阶叙事15分、算法信号15分）。
- **爆款钩子维度调整**：将原“完播率潜力”拆分为“完播率潜力”与“复播引导设计”，各占10分。
- **平台适配细化**：TikTok 适配强调深度评论引导，Meta Reels 新增 UTIS 模型一致性评估。
- **核心铁律升级**：`SKILL.md` 新增“必须植入复播钩子”和“互动引导质量优先”两条铁律。
- **工作流增强**：阶段2增加复播彩蛋植入点设计，阶段3提示词模板加入复播引导指令，阶段4新增互动引导话术模板。
- **自检报告扩充**：新增复播彩蛋类型、深度互动策略、算法信号预估等检查项。

### 📚 文档更新
- `references/viral-hook-patterns.md` → v2.2
- `evaluation-rubric.md` → v2.2
- `SKILL.md` → v2.2

---

## [v2.1] - 2026-04-14

### 🚀 新增
- **双镜头叙事语法**：在 `cinematic-vocabulary.md` 中新增多镜头切换指令（两段式对比、快速切入、时间跳跃、匹配动作转场、交叉剪辑）。
- **音频同步指令**：新增重低音、轻快旋律、氛围音乐、ASMR 触发、人声旁白五类音频同步指令。
- **图生视频前置引导**：新增延续图片风格、从静态到动态、相机轻微运动、产品特写转场四类引导指令。
- **四维度评分体系**：`evaluation-rubric.md` 新增“进阶叙事”维度（15分），含多镜头结构完整性、音频同步效果、转场质量。
- **失败案例知识库**：新增 `references/failure-case-library.md`，收录10个典型失败案例及修复方案。
- **A/B测试矩阵模板**：新增 `references/ab-testing-matrix.md`，提供系统化多变量测试框架。

### 🔄 变更
- **默认脚本结构升级**：`SKILL.md` 核心铁律新增“默认双镜头结构”，所有脚本优先使用 0-7s 痛点 + 8-15s 解决。
- **评分体系重构**：从三维度升级为四维度（技术质量25分、爆款钩子35分、平台适配25分、进阶叙事15分）。
- **平台规格更新**：`platform-specs.md` 新增各平台多镜头支持度、音频同步加权说明，新增多镜头叙事最佳实践汇总表。
- **提示词示例全部重写**：`examples/prompt-examples.md` 全部6个示例升级为双镜头结构，并融入音频同步指令。
- **产品追踪模板升级**：`product-tracker-template.md` 新增脚本结构、转场方式、音频同步类型字段，评估表格对齐四维度。

### 📚 文档更新
- `SKILL.md` → v2.1
- `references/viral-hook-patterns.md` → v2.1
- `references/cinematic-vocabulary.md` → v2.1
- `references/platform-specs.md` → v2.1
- `evaluation-rubric.md` → v2.1
- `product-tracker-template.md` → v2.1
- `examples/prompt-examples.md` → v2.1
- `references/failure-case-library.md` → v1.0（新增）
- `references/ab-testing-matrix.md` → v1.0（新增）

---

## [v2.0] - 2026-04-13

### 🚀 新增
- **2026 平台算法全面适配**：
  - TikTok 互动权重更新（评论+分享取代收藏）
  - YouTube Shorts 关键词搜索流量入口
  - Meta Reels “真实兴趣”推荐机制
- **Meta Advantage+ Creative 集成策略**：在 `SKILL.md` 中新增第4章节，提供模块化素材拆分方案。
- **多平台分发策略生成**：工作流新增阶段4，为同一素材提供平台差异化的标题、标签、文案指引。
- **爆款钩子特征库**：新增 `references/viral-hook-patterns.md`，定义6大钩子类型及决策树。

### 🔄 变更
- **评分体系重构**：从单一维度改为“技术质量(30) + 爆款钩子(40) + 平台适配(30)”三层结构。
- **成本控制强化**：明确“禁止盲测”，必须先经过钩子图文三选一验证。
- **平台规格全面更新**：`platform-specs.md` 更新6+平台2026年最新规格与算法规则。
- **词汇表重构**：`cinematic-vocabulary.md` 新增爆款前缀、去AI味指令、平台尾缀、负面词表。
- **产品追踪模板升级**：增加成本追踪、归因分析、Skill迭代建议等模块。

### 📚 文档结构
```
tiktok-ad-video-skill/
├── SKILL.md (v2.0)
├── README.md (v2.0)
├── evaluation-rubric.md (v2.0)
├── product-tracker-template.md (v2.0)
├── examples/
│   └── prompt-examples.md (v2.0)
└── references/
    ├── viral-hook-patterns.md (v2.0)
    ├── cinematic-vocabulary.md (v2.0)
    └── platform-specs.md (v2.0)
```

---

## [v1.0] - 2025-10-15

### 🎉 初始版本发布

- **核心工作流**：选品预判 → 15秒脚本 → Seedance 2.0提示词 → 质量评估 → 数据回流
- **基础钩子体系**：3种钩子类型（价格锚定、生活转变、科技展示）
- **基础评分表**：8维度评分（40分制）
- **支持平台**：TikTok、Meta Reels、YouTube Shorts
- **实战验证**：经过80+条视频、8+个生产日打磨

### 📚 初始文档
- `SKILL.md` (v1.0)
- `README.md` (v1.0)
- `evaluation-rubric.md` (v1.0)
- `product-tracker-template.md` (v1.0)
- `examples/prompt-examples.md` (v1.0)
- `references/platform-specs.md` (v1.0)
- `references/cinematic-vocabulary.md` (v1.0)

---

## 版本号说明

| 版本类型 | 说明 | 示例 |
| :--- | :--- | :--- |
| **主版本号** | 重大架构变更，不兼容旧版 | v1.0 → v2.0（评分体系重构、新增钩子库） |
| **次版本号** | 功能新增，向下兼容 | v2.0 → v2.1（双镜头语法、音频同步） |
| **修订号** | 问题修复、文档优化 | v2.1 → v2.2（算法信号细化、互动策略升级） |

---

## 未来规划

### v2.3 (计划中)
- [ ] 新增 `ad-campaign-testing.md`（广告创意测试完全指南）
- [ ] 新增 `localization-guide.md`（出海短视频本土化完全指南）
- [ ] 工作流集成本土化 SOP

### v3.0 (远期规划)
- [ ] 品牌建设场景扩展（真实兴趣内容系统化）
- [ ] 红人营销创意简报模板
- [ ] 多模态参考生成能力深度集成

- **D. 暂停，当前版本已满足需求**
