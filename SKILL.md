# TikTok Ad Video Skill · Seedance 2.0 专用版 (v3.0)

> **核心目标**：以最小成本、最高概率生成 TikTok/Reels/Shorts/Threads/Lemon8 全域爆款广告视频。
> **设计理念**：**单一文件，全内置。** 复制粘贴即可使用，零外部依赖。覆盖从选品到复盘的完整链路。
> **视频模型**：Seedance 2.0（单次生成最长 **15秒**，叙事型需分段拼接）。
> **强制约束**：默认输出格式 **9:16 竖屏 (1080x1920)**，提示词必须输出为**原子化分段指令**。
> **迭代版本**：v3.0 (2026.05) —— 项目结构精简，SKILL.md 升级为全内置单文件入口。


## 📌 快速诊断矩阵

```
播放量卡在 200-500 → 强化前3秒声音钩子，确认Hook匹配品类与趋势热度
完播率低 → 检查多镜头结构，增加 Snappy motion
收藏率<5% → 增加 "Save for your next ___" 引导
分享率<3% → 更换社交货币类型（对照 §4.3 社交货币话术库）
AI味太重 → 启用原生感词汇（对照 §12 常用指令速查）
美国市场卡300 → 切换到叙事型软广（§5 叙事模板）
想做系列化 → 使用 §6 微短剧模板
指令超长导致画面异常 → 改分段生成，每段≤100词
某段生成翻车 → 局部重生成，不推翻全部（§7.3 容错协议）
```


## 1. 核心铁律（10 条）

1. **前 3 秒定生死**：首帧必须有视觉冲突/悬念，**强制“视觉奇观+ASMR”双管齐下**（口播第 3 秒后进入）。
2. **原生感 (UGC) 优先**：看起来像真实用户分享。评论区一旦出现“这是广告？”的质疑，原生感得分即为 0。
3. **三维匹配**：Hook选择必须交叉验证品类×Hook×趋势热度（上升期🚀优先，衰减期📉警告，衰退期⚰️淘汰）。
4. **原子化分段指令**：直给型提示词每段 30-60 词，单镜头单一运镜，禁止否定式负向词，强制使用正向锚点词。
5. **先验证、后投入**：三层快速诊断未通过绝不消耗积分。
6. **转化紧迫感 (社交货币)**：必须植入收藏与分享引导。分享率每高出大盘均值2%，转化价值便翻倍增长。
7. **垂直领域信号**：前 5 秒口述+字幕双重强化核心主题词。
8. **复播Hook必须植入**：信息差/节奏中断/双重结局。
9. **一稿通投，平台微调**：8 平台差异化发布。
10. **数据闭环**：发布后反馈数据 → 自动迭代 → 样本≥20 条触发校准。


## 2. 内容形态决策

- **直给型 (15s)**：3 秒内可展示效果、中国/东南亚市场、粉丝>10K。
- **叙事型 (45-60s)**：需过程展示、美国/欧洲、连续 3 条直给型<500 播放、产品外观独特。视频内严格 **“零提及”品牌/价格**，转化后置到评论区。
- **微短剧系列 (多集)**：用户明确要求系列化内容时启用（详见 §6）。


## 3. 工作流索引（8 阶段 · 含阶梯式算力分配）

| 阶段 | 名称 | 核心逻辑 | 跳过条件 | 算力模式 |
| :--- | :--- | :--- | :--- | :--- |
| -2 | 趋势扫描 | 输出品类趋势+四档热度标签(🚀📊📉⚰️) | 用户跳过 | — |
| -1 | 竞品拆解 | 3-5 个爆款视频结构分析 | 用户跳过 | — |
| 0 | 选品匹配 | 三维矩阵推荐Hook+声音策略+趋势适配（§4） | — | — |
| 0.5 | 形态决策 | 直给型/叙事型/微短剧分流（§2） | — | — |
| 1 | Hook盲测 | 变体库随机 3 选 1（§4.2） | — | — |
| 2 | 脚本结构化 | 多镜头模板匹配（§4.1） | — | — |
| 3 | 提示词工程 | 原子化分段输出（§7） | — | **阶梯式：镜头1=Standard, 镜头2-4=Fast** |
| 3.5 | 三层诊断 | 致命层/核心层/卫生层快速风控（§8） | — | — |
| 4 | 8 平台分发 | 含 AIGC 标签提醒+最佳发布时间（§9） | — | — |
| 5 | 视频评估 | 生成后评估 | — | — |
| 6 | 数据迭代 | 校准闭环，样本≥20 触发（§11） | — | — |


## 4. Hook体系（三维匹配 + 变体库）

### 4.1 三维匹配速查表

| 品类 | ✅ 推荐Hook | 声音策略 | 趋势适配 |
| :--- | :--- | :--- | :--- |
| 锅具/厨房 | 视觉奇观/故事型 | 纯 ASMR 前 3 秒 | #cookinghack + 治愈系烹饪音频 |
| 香水/美妆 | 场景共鸣 POV | 环境音，口播第 3 秒 | #selfcare + 季节性主题 |
| 清洁用品 | 认知失调型 | ASMR 擦拭声 + 叮声 | #cleaninghack + 强迫症舒适音频 |
| 收纳用品 | 极简结果型 | ASMR 物品碰撞/归位声 | #homeorganization + 收纳改造 |
| 鞋服/百货 | 百搭展示/性价比反差 | 轻快旋律 + 价格字幕 | #OOTD + 当季流行款 |
| 3C/家电 | 痛点对比/技术下放 | 口播先入 + 对比画面 | #techreview + 科技感 BGM |
| 食品饮料 | 视觉奇观/Adulting Win | ASMR 酥脆/爆浆声 | #foodtok + ASMR 烹饪音频 |

### 4.2 各Hook变体库（部分示例，完整版见 references/core-knowledge.md）

**认知失调型**：
1. "Stop using [旧方法]. This is what you need."
2. "Your [旧方法] is lying to you."
3. "There's no way this works... wait."
4. "I thought this was a gimmick. I was wrong."
5. "They don't want you to know this hack."

**视觉奇观型**：
1. "Watch what happens when I crack this egg."
2. "No oil. No butter. Just slide."
3. "I've never seen a pan do this."
4. "Sound on for the most satisfying slide."
5. "The way this just... glides."

**故事型 Mystery Object**（美国市场）：
1. "My mom sent me this from [country]. I had no idea what it was."
2. "Found this at a flea market. Changed how I cook."
3. "I bought this from a random link. Still don't know the name."
4. "My roommate said this thing is useless. Watch this."
5. "Everyone asks me what this is. Here's the answer."

### 4.3 社交货币话术库

| 类型 | 话术示例 | 适用场景 |
| :--- | :--- | :--- |
| **展现品味型** | "Share this if you have good taste 💅" | 美妆、服饰、家居 |
| **展示专业型** | "Real chefs know this hack 👨‍🍳" | 厨具、清洁、DIY |
| **圈层归属型** | "Tag your nail bestie" / "Share with your renter friends 🏠" | 垂直品类、兴趣社群 |

**收藏引导话术**：`"Save for your next ___"` / `"Save this, thank me later"`


## 5. 叙事型软广模板库（5 种）

| 模板 | 核心叙事逻辑 | 适用场景 | 时长 |
| :--- | :--- | :--- | :--- |
| **Mystery Object** | 困境→发现→验证→收尾 | 产品外观独特或效果反常识 | 50-55s |
| **Before You Judge** | 偏见→尝试→打脸→认输 | 产品看起来普通但效果惊人 | 45-50s |
| **Adulting Win** | 困境→行动→成果→升华 | 22-35 岁独立生活人群 | 50-55s |
| **Secret Ingredient** | 展示结果→追问→揭秘→彩蛋 | 产品是惊艳结果的隐藏原因 | 40-50s |
| **Routine Reveal** | 开始→流程→细节特写→收尾 | 产品融入日常流程 | 45-55s |

**美国市场专属规则**：视频内零提及品牌名、价格、购买链接。所有转化动作后置到评论区和个人主页。评论区运营策略详见 `references/narrative-playbook.md`。


## 6. 微短剧系列模板库

### 6.1 系列化结构设计

| 模块 | 作用 | 示例 |
| :--- | :--- | :--- |
| **角色设定** | 系列化的灵魂，1-2 个核心角色 | 生存专家、生活小白、职业达人 |
| **世界观构建** | 决定独特性和记忆点 | 末日生存、普通日常、行业揭秘 |
| **单集结构** | 1分钟左右：开头Hook(0-5s)→困境展开(5-20s)→产品登场(20-40s)→收尾Hook(40-60s) | — |
| **长效Hook** | 驱动追更：未完成结局、角色成长线、观众参与决策、隐藏彩蛋 | — |

### 6.2 转化点植入时机

| 系列阶段 | 转化策略 |
| :--- | :--- |
| 第1集 | **零转化**，纯粹吸引关注 |
| 第2-3集 | **评论区软引导**，回应评论时提及产品 |
| 第4-5集 | **bio链接显性化**，简介更新为链接 |
| 第6集以后 | **专属系列折扣**，为追更粉丝提供专属折扣码 |


## 7. 提示词输出规范（原子化分段指令 · 阶梯式算力分配）

> **原则**：直给型视频必须输出为独立镜头段落，每段 30-60 词（绝对不超过 100 词），单镜头单一运镜。

### 7.1 官方 6 步公式

**主体/角色 → 动作/剧情 → 环境/场景 → 镜头/运镜 → 风格/氛围 → 约束/避坑**

### 7.2 正/负向词对照表

| ✅ 使用（正向锚点词） | ❌ 禁止（否定式负向词·严格禁用） |
| :--- | :--- |
| `Well-formed hands` | ~~`No extra fingers`~~ |
| `Stable object geometry` | ~~`No warping`~~ |
| `Natural facial features` | ~~`No face distortion`~~ |
| `Steady motion` | ~~`No jitter`~~ |
| `Crystal-clear` / `Sharp focus on product` | ~~`No blur`~~ |

### 7.3 分镜容错与补偿协议

- **局部重生成**：“第X镜头生成失败，原因是[具体问题]。请微调提示词并重新生成这一段，保持与其他镜头的色调、光影和主体风格一致。”
- **补偿机制**：若某个镜头连续失败，立即调整剧本，用相邻镜头的画面素材进行剪辑覆盖。

### 7.4 直给型输出模板

```
[镜头1: 0-3s | 黄金Hook | **Standard模式**]
4K UHD, 48fps, [焦段]。 [单种主导运镜] + [主体动作]。 [光影风格]。 [正向约束锚点词]。

[镜头2: 3-4s | 转场+微距 | **Fast模式**]
[明确转场方式]。 4K UHD, 30fps, 100mm macro lens。 [微距动作]。 Visual sync with [音效]。 [正向约束]。

[镜头3: 4-7s | 多角度快切 | **Fast模式**]
4K UHD, 30fps, 50mm lens。 Multi-angle quick cuts of [核心过程]。 Natural window light, crisp highlights。 Steady motion。

[镜头4: 7-15s | 结果定格+CTA | **Fast模式**]
4K UHD, 30fps, 50mm lens。 Slow dolly-out to [最终结果] wide shot。 Freeze frame on [完美画面] for 2 seconds。 Clear space for text overlay。 [社交货币/收藏引导文案]。
```


## 8. 预评估：三层快速诊断（量化版）

| 层级 | 检查项 | 量化标准 | 不通过动作 |
| :--- | :--- | :--- | :--- |
| 🔴 **致命层** | Hook是否有视觉冲突？是否有声音Hook？ | 二选一：任一不满足即不通过 | **禁止提交**，退回阶段 2 |
| 🟡 **核心层** | 垂直信号是否前 5 秒口述+字幕双出现？原生感是否启用？ | **垂直信号缺失扣 5 分**；**原生感未启用扣 3 分**。累计扣分 ≥5 分即不通过 | **警告 + 微调**，用户确认后提交 |
| 🟢 **卫生层** | 是否含否定式负向词？是否超过 100 词/段？ | 含否定词自动替换为正向锚点词；超长自动拆分为独立段落 | **自动修正**，直接提交 |


## 9. 8 平台分发矩阵（含最佳发布时间）

| 平台 | 发布时间窗（美东） | 素材复用策略 | AIGC标签 |
| :--- | :--- | :--- | :--- |
| TikTok | 晚 7:00-10:00 | 母版视频 | AI-generated content |
| YouTube Shorts | 早 8:00-10:00 | 同母版，改标题 SEO | Altered content |
| IG/FB Reels | 晚 8:00-10:00 | 同母版，分散日期发布 | Made with AI |
| Threads | 随 Reels 同步 | 复用 Reels 视频，加文案 | Made with AI |
| Pinterest | 晚 8:00-11:00 | 改封面 + 文字叠加 | 建议标注 |
| Lemon8 | 午 12:00-2:00 | 改封面图+长尾标签 | AI-assisted content |
| Snapchat | 下午 3:00-5:00 | 同母版，去水印 | 暂未强制 |


## 10. 高频失败模式速查

| 失败表现 | 修复方案 |
| :--- | :--- |
| 三层诊断致命层不通过 | 退回阶段 2，强化Hook和声音策略 |
| 核心层不通过（垂直信号缺失） | 前5秒增加口述+字幕的关键词强化 |
| 核心层不通过（原生感未启用） | 添加 `Natural window light`, `Handheld POV` |
| 播放量卡在 200-500 | 强化前3秒声音Hook；确认趋势热度阶段；美国市场切叙事型 |
| 完播率低 | 增加 `Snappy motion, Quick cuts` |
| 指令超长导致画面异常 | 改分段生成，每段≤100 词 |
| 某段生成翻车 | 局部重生成，不推翻全部，保持色调一致 |


## 11. 成本控制

| 场景 | 模式 | 积分 | 性价比系数 |
| :--- | :--- | :--- | :--- |
| 冷启动（前 3 条） | Fast | 60-84 | 目标 >1.5 |
| 验证成功后复制 | Standard | 120 | — |
| 正式投放 | Standard | 120 | — |
| A/B 次要变体 | Fast | 60-84 | — |
| 叙事型分段（4段） | 混合 | 360-408 | — |

> **性价比系数 = (预估播放量 / 消耗积分) × 100**。系数 >1.5 为优秀；<0.8 为不及格，需要优化流程。


## 12. 常用指令速查

**声音Hook**：`前3秒纯 ASMR 音效` / `Visual beats sync with heavy bass`

**原生感词汇**：`Authentic unscripted reaction` / `Lived-in messy background` / `Natural window light` / `Handheld POV`

**正向锚点词**：`Well-formed hands` / `Stable object geometry` / `Crystal-clear` / `Steady motion` / `Sharp focus on product`

**平台尾缀**：`9:16 vertical, 15 seconds loop-ready, sharp focus on product`

**AIGC 标签**：TikTok: "AI-generated content" / Meta: "Made with AI" / YouTube: "Altered content"


## 📚 深度知识库

> **本文档已包含日常生成所需的全部核心规则。** 以下文件提供更详细的知识库，按需查阅：
>
> | 场景 | 查阅文件 |
> | :--- | :--- |
> | 完整Hook变体库（40+）、详细评分标准、平台算法规则 | `references/core-knowledge.md` |
> | 详细叙事型剧本展开、微短剧系列指南、评论区运营策略 | `references/narrative-playbook.md` |
> | 16 个完整失败案例与修复方案 | `references/failure-case-library.md` |


**记住**：前 3 秒声音Hook比画面更重要；趋势踩对事半功倍；原子化分段指令，每段不超过 100 词；正向锚点词替代否定式负向词；致命层不通过绝不消耗积分。
