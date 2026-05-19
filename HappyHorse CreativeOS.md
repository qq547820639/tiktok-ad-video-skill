# HappyHorse CreativeOS v2.5-stable Master Document

---

> **本文档是 HappyHorse CreativeOS 的唯一主文档。**
> 内部分为两个执行层级和一个桥接层。运行时只调用 Runtime 层，离线审计和校准调用 Expert Kernel 层，两者通过 DeltaScore、Failure Bank 和 K9 离线计算器连接。不要把两个层级混成同一套运行逻辑。

---

## A5.0 版本发布元信息

| 字段 | 值 |
|:--|:--|
| 当前版本 | v2.5-stable |
| 发布日期 | 2026-05-19 |
| 文档状态 | 正式版（Active-Stable） |
| 理论基础版本 | v2.0.1 系统规范定稿 + 心理传播学知识框架 v1.1 |
| Expert Kernel 版本 | v2.2（Active-Stable） |
| Runtime 版本 | v2.5（Active-Stable） |
| 创作指南版本 | HappyHorse 1.0 创作指南 |
| 升级触发 | v2.2 Design Review + v2.3/v2.4 LLM-Native 评估 + 双层架构决议 |
| ActionLevel | 3（架构级结构性升级） |
| 维护负责人 | （填写） |
| 下次评审日期 | 首轮 3 品类 Pilot 完成后 7 日内 |

> **版本追溯规则：**
> 1. 每次 Kernel 级修改（ActionLevel=3）必须在 CalibrationLog 中创建记录，并更新版本号。
> 2. 版本号格式：`主版本.次版本`（如 v2.5），修订格式：`v2.5-r1`。
> 3. Expert Kernel 和 Runtime 各自独立版本治理，通过 Bridge 层连接。

> **Status 生命周期：**
> Draft → Active-Pilot → Active-Stable → Advisory / Deprecated / Rollback

---

## 目录

### 快速跳转

| 我想... | 阅读 |
|:--|:--|
| 了解系统全貌 | Part 1 |
| 了解双层架构 | Part 1 第二章 |
| 日常生成广告 | **Part 3 Runtime System Prompt（一键复制代码块）** |
| 理解六层叙事模型 | Part 2 R4（L1-L6） |
| 理解完整评分体系 | Part 2 K8-K10（Q1-Q8 + StructureScore + 动态权重） |
| 理解 Runtime 评分 | Part 3 Section 10（RuntimeScore） |
| 植入 VEL | Part 2 K7 + K7.1 + K7.2 |
| 理解产品交互响应 | Part 2 K24 |
| 理解音画同步 | Part 2 K25 |
| 理解产品形态保真 | Part 2 K26 + K27 |
| 检查 NoPost 可行性 | Part 2 K18 / Part 3 Section 7 |
| 执行候选修复 | Part 2 R1.1 |
| 智能硬件专用流程 | Part 2 R5 / Part 3 Section 8 |
| 交付 Prompt 和投放资产 | Part 3 Section 12（输出模板） |
| 审计验算 | Part 2 Audit（15-Step Verification） |
| 评测回测 | Part 2 Evaluation（E1-E4） |
| 校准与迭代 | Part 2 Benchmark + Part 4 DeltaScore |
| 建数据库表 | Part 2 O1 |
| 执行 Pilot | Part 2 Pilot + Part 4 测试协议 |
| 查看版本历史 | Part 5 A5 |

### 文档结构

| 篇章 | 内容 | 核心编号 |
|:--|:--|:--|
| **Part 1** | **系统总览** | 系统定位、双层架构、层级关系 |
| **Part 2** | **Expert Kernel（v2.2）** | K1-K30 / R1-R6 / Audit / Evaluation / Benchmark / Operations / Pilot |
| **Part 3** | **Runtime Executor（v2.5）** | System Prompt / MVI / RuntimeScore / NoPost / Output Template |
| **Part 4** | **Bridge Layer** | DeltaScore / Failure Bank / K9 Calculator / Pilot Protocol |
| **Part 5** | **Appendix** | JSON Schema / Input Template / 版本历史 / 禁止事项 |

---

# Part 1：系统总览

---

## 一、系统定位

```
HappyHorse CreativeOS v2.5-stable Master Document
= 创意编译器（Creative Compiler）
+ 情绪叙事引擎（Emotional Narrative Engine）
+ Prompt 工程器（Prompt Engineer）
+ 渲染评测器（Render Bench）
+ 标注系统（Annotation Console）
+ 投放追踪器（Ad Test Tracker）
+ 校准引擎（Calibration Engine）
+ 版本治理器（Version Governance）
+ 决策看板（Decision Dashboard）
+ LLM Runtime Executor
```

**一句话定位：**
把产品卖点编译成可生成、可评分、可审计、可回测、可归因、可校准、可持续进化的 AI 视频广告系统。

---

## 二、双层架构

```
┌──────────────────────────────────────────────────────────────────┐
│           HappyHorse CreativeOS v2.5-stable Master Document       │
│                    Production Architecture                        │
├──────────────────────────────────────────────────────────────────┤
│                                                                  │
│  Part 2: Expert Kernel (v2.2)                                    │
│  ┌──────────────────────┐                                        │
│  │  K1-K30 Rules        │    用途：专家审计、离线精算、回测、     │
│  │  K9 Full Scoring     │    校准、版本治理、团队 SOP             │
│  │  15-Step Audit       │                                        │
│  │  Evaluation/Bench    │    执行者：人类专家 + 离线工具          │
│  │  Operations/Pilot    │                                        │
│  │  Version Governance  │    Token 预算：不限                     │
│  └──────────┬───────────┘                                        │
│             │ Validates via DeltaScore                            │
│             ▼                                                    │
│  Part 4: Bridge Layer                                            │
│  ┌──────────────────────┐                                        │
│  │  DeltaScore Protocol │                                        │
│  │  Failure Bank        │    用途：连接 Kernel 与 Runtime，       │
│  │  K9 Offline Calc     │    数据回流、校准驱动、冷启动           │
│  │  CalibrationLog      │                                        │
│  └──────────┬───────────┘                                        │
│             │ Feeds into                                          │
│             ▼                                                    │
│  Part 3: Runtime Executor (v2.5)                                 │
│  ┌──────────────────────┐                                        │
│  │  MVI Check           │                                        │
│  │  Context Ingestion   │    用途：单次 AI 回复内完成创作、       │
│  │  3-Candidate Gen     │    估分、迭代、NoPost 锁定、交付        │
│  │  Lightweight Audit   │                                        │
│  │  Winner Selection    │    执行者：LLM 单次闭环                 │
│  │  RuntimeScore        │                                        │
│  │  NoPost Physics Lock │    Token 预算：≤4500 输出               │
│  │  Delivery (13 items) │                                        │
│  └──────────────────────┘                                        │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘
```

---

## 三、层级关系定义

| 维度 | Part 2: Expert Kernel (v2.2) | Part 3: Runtime Executor (v2.5) |
|:--|:--|:--|
| 用途 | 专家审计、完整 K9 精算、版本治理、回测、校准 | 单次 AI 回复内的创作、估分、迭代、交付 |
| 执行者 | 人类专家 + 离线工具 | LLM 单次闭环 |
| 评分系统 | K9 StructureScore（完整精算链） | RuntimeScore（线性近似） |
| 候选展示 | 完整 3 候选 + 逐项评分 + 修复过程 | 隐式发散 + 显式轻量审计表 |
| NoPost | K18 NoPostGate（事后审计） | NoPost Physics Lock（事前物理锁） |
| Token 消耗 | 不限（离线执行） | ≤4500 输出 Token |
| 数据依赖 | 需要渲染数据和投放数据 | 零数据即可运行（使用 Synthetic Seed） |
| 输出格式 | 13 项 Delivery 模板 | 13 项交付 + JSON Schema |
| 谁验证谁 | Kernel 验证 Runtime 的近似精度 | Runtime 为 Kernel 产生候选和校准数据 |

**核心原则：**
Runtime 不直接执行 Kernel 的全部规则；Kernel 不约束 Runtime 的具体生成过程。二者只通过结构化字段通信：RuntimeScore、KernelScore、DeltaScore、Calibration Fields、Failure Bank。

---

## 四、HappyHorse 1.0 模型能力

### 4.1 核心功能

| 功能 | 说明 |
|:--|:--|
| **文生视频 T2V** | 通过文本描述生成视频 |
| **首帧图生视频 I2V** | 以一张静态图片作为视频第一帧，精确还原后生成动态视频 |
| **多图参考生视频 R2V** | 输入 1-9 张参考图引导生成 |
| **视频编辑 V2V** | 对已有视频智能编辑 |
| **音视频联合生成** | 环境音、音效、对白、背景音乐一体化生成 |

### 4.2 核心亮点

| 核心亮点 | 评分映射 |
|:--|:--|
| 电影级画面质感与光影表现 | Q3 感官丰富度 + C 类材质光影 VEL + K7.1 环境光材质交互 |
| 流畅稳定的运镜与转场能力 | Q5 执行力 + K5 运镜指令体系 + K5.1 运镜路径 |
| 人物真实感强，面部表情有生命力 | Q8 情绪冲击力 + B 类角色生命 VEL + K7.2 状态过渡 |
| 中近景叙事能力突出 | Q1 Hook力 + Q4 传播力 + K28 导演意图层 |
| 音视频联合生成 | AudioMatchScore / AudioApplicable / K25 音画同步 |
| 灵活多样的创作体验 | 多模式路由适配 + R5 智能硬件流程 + R6 提交策略 |

### 4.3 HappyHorse 已知限制

| 限制 | 应对策略 |
|:--|:--|
| 不擅长精确色彩控制 | 避免使用"画面变成黑白"等强色彩控制表达 |
| 不擅长精确时序控制 | 避免使用"时间倒流"等复杂时间表达；使用相对时序 |
| 不支持稳定分屏效果 | 避免使用"分屏"等画面结构要求 |
| 可能生成伪文字/伪Logo | K27 NoText/NoLogo 渲染审计 + 产品表面锁定前置 |
| 产品形态可能漂移 | K26 Product Fidelity Gate + forbidden transformations |

### 4.4 优势场景

| 场景 | 典型能力 |
|:--|:--|
| **影视短剧制作** | 情感表演细节丰富、光影跨场景稳定复现、角色一致性维持 |
| **电商广告（含数字人口播）** | 产品展示清晰度高、数字人口播自然真实、支持批量生产 |
| **社媒创意视频** | 画面质感高、运镜转场流畅、多风格适配 |
| **智能硬件产品视频** | 产品交互响应渲染、LED/光效材质扩散、触碰→反馈因果链 |

### 4.5 平台输入输出规格汇总

| 模式 | 输入 | 输出 |
|:--|:--|:--|
| **文生视频** | 自然语言（≤2500汉字/≤5000英文字符），必填 | 分辨率720P/1080P，画幅16:9/9:16/3:4/4:3/1:1，时长3-15秒 |
| **首帧生视频** | 1张首帧图 + 自然语言（可选） | 画幅与首帧图一致，时长3-15秒 |
| **参考图生视频** | 1-9张参考图 + 自然语言（必填） | 画幅可选，时长3-15秒 |
| **视频编辑** | 1个视频 + 1-4张参考图 + 自然语言 | 画幅与输入视频一致，时长3-15秒 |

---

# Part 2：Expert Kernel（v2.2）

---

> **本部分是完整的专家规格书，用于离线审计、完整 K9 精算、版本治理、回测和校准。**
> **不要在单次 LLM 回复中全量执行本部分。Runtime 层已将核心原则内化为可执行规则。**

---

## K1. HappyHorse 能力边界

默认 HappyHorse 1.0 支持：
1. 文生视频 T2V
2. 首帧图生视频 I2V
3. 多图参考生视频 R2V
4. 视频编辑 V2V
5. 音视频联合生成
6. 电影级画面质感
7. 运镜与转场
8. 人物真实感
9. 中近景叙事
10. 环境音、音效、对白、背景音乐生成

---

## K2. 四元提示词公式

```
Prompt = 场景 + 主体 + 运动 + 音频
```

- **场景**：时间、空间、光线、前景、背景、气氛。
- **主体**：人物、动物、产品或核心物体。最多 3 个主体。
- **运动**：主体动作、镜头运动、产品互动、情绪变化、结尾 CTA。
- **音频**：环境音、动作声、音乐、对白或口播。不得依赖后期配音。

**各模式填写要求：**

| 模式 | 场景 | 主体 | 运动 | 音频 |
|:--|:--|:--|:--|:--|
| T2V | 必填 | 必填 | 必填 | 必填 |
| I2V | 沿用首帧图像 | 沿用首帧图像 | 必填 | 必填 |
| R2V | 必填 | 必填 + @图片指代 | 必填 | 必填 |
| V2V | 由原视频提供 | 由原视频提供 | 编辑意图 | 必填 |

**V2V 四元公式简化为：**
```
Prompt = 保留内容 + 修改内容 + 运动变化 + 音频变化 + 禁止误改项
```

---

## K3. 模式路由

| 输入条件 | 模式 | 提示词要求 |
|:--|:--|:--|
| 无图片、无视频 | T2V 文生视频 | 场景+主体+运动+音频（全部必填） |
| 有 1 张图片 | I2V 首帧图生视频 | 运动+音频（场景/主体由图片提供） |
| 有多张图片 | R2V 多图参考生视频 | 场景+主体+运动+音频+@图片指代 |
| 有视频 | V2V 视频编辑 | 编辑意图（改什么+保留什么+禁止误改什么） |

**I2V 核心原则：** 重点描述"动起来之后发生什么"。

**R2V 指代规则：** 通过 @图片1、@图片2 等方式准确指代素材。

**V2V 核心原则：** 明确指出"改什么"和"保留什么"。

---

## K4. 硬性铁律（15 条）

1. 视频 ≤15 秒。
2. 角色 ≤3 个。
3. 场景 ≤3 个。
4. 中文 Prompt ≤2500 汉字，英文 Prompt ≤5000 字符。
5. 视频内文字最多 3 个短词。
6. 不在视频画面中依赖价格、URL、优惠码、长字幕、精准 Logo。
7. 不使用"突然""突然间"。
8. 不使用"她意识到""他觉得""她明白了"等内心独白。
9. 不使用"时间倒流""分屏""画面变成黑白"等动态控制否定。静态条件否定合法。
10. 不使用"镜头拉远看到全景"这类笼统表达。
11. 所有冲突、选择、情绪必须通过可见画面表达。
12. CTA 必须通过画面动作表达。
13. 必须包含音频描述。
14. 不把投放标题、标签、评论里的销售语言写进视频画面。
15. 如果强销售表达与可生成性冲突，销售表达放入标题、置顶评论、Bio 或商品卡。

**否定描述区分：**
- **动态控制否定（禁止）：** "画面变成黑白""时间倒流""突然消失"
- **静态条件否定（合法）：** "房间没有开灯""桌上没有食物""背景没有人"

---

## K5. 运镜规则

**可用运镜词表：**
```
Push in / Pull back / Close-up / Medium shot / Wide shot
Track / Follow / Hold / Drift / Circle
Tilt up / Top-down / Low-angle track / Slow advance
Side track / Depth shift / Rise / Drop
```

**规则：**
1. 每个运动描述句必须包含明确动作或运镜。
2. 一句话不要堆叠多个互相冲突的运镜。
3. 运镜必须服务于 Hook、产品、情绪或 CTA。
4. 不为了炫技而使用复杂运镜。
5. 电商广告优先使用中近景、特写、手部交互和稳定推进。
6. 剧情广告可以使用转场和情绪推进，但不能超过 3 个场景。

---

## K5.1 Camera Path Framework（运镜路径框架）

**状态：Active-Pilot（升级条件：≥30 条渲染样本且通过率 ≥70%）**

当 Prompt 使用运镜时，优先采用路径描述而非仅类型描述：

```
标准格式：
[Camera move] from [origin] through/past [spatial element]
toward [target], to reveal/connect/contrast [narrative purpose].
```

**字段要求：**

| 字段 | 要求 |
|:--|:--|
| 起点 | 明确镜头从哪里来 |
| 路径 | 明确经过什么空间元素 |
| 终点 | 明确落到谁或什么物体 |
| 目的 | 服务 Hook / 产品 / 情绪 / CTA |

**示例：**
- ✓ "Camera pushes in slowly from the direction of the rain-streaked window toward her face."
- ✓ "Camera drifts from the glowing speaker across the cardboard boxes to reveal her relaxed silhouette."

**禁止：**
- ✗ "Camera moves beautifully."
- ✗ "Cinematic camera movement."
- ✗ "Camera shows the scene."

---

## K6. ShowDontTell 预检

评分前必须检查：
1. 是否存在抽象心理描写。
2. 是否存在不可见的情绪说明。
3. 是否存在否定空间关系（"不在X""远离X"）。
4. 是否存在过度抽象的形状描述（"形状像X"）。
5. 是否存在必须靠字幕才能理解的剧情转折。
6. 是否存在必须靠后期配音才能成立的情绪冲突。

**修复原则：** 心理变动作 → 抽象变画面 → 解释变物理行为 → 销售语言移到投放资产中。

---

## K7. VEL 视觉增强层

**状态：Active-Stable（基础层 A/B/C/D）**

VEL 必须在候选生成之后、评分之前植入。每个最终 Prompt 必须植入 3-4 个 VEL 增强词。不得堆叠。每句最多一个。

<details>
<summary>点击展开：VEL 四类增强词完整列表</summary>

**A 类：物理真实**（0-1 个）
用于悬浮、碎裂、流体、逆重力、异常运动。
- 灰尘在下方旋转 / 空气在周围产生波纹 / 细小碎片被带动 / 涟漪向外扩散 / 微粒从物体边缘飘散 / 物体周围有微弱的热浪扭曲 / 灰尘颗粒在光线中散射

**B 类：角色生命**（1-2 个，每个角色最多 1 个）
用于人物或动物的表情、呼吸、手部细节。
- 手指微微颤抖 / 眼睛微微睁大 / 下颌收紧 / 呼吸在冷空气中可见 / 眨眼变慢 / 嘴唇微微张开 / 喉咙吞咽可见 / 肩膀绷紧 / 头微微倾斜 / 颈部皮肤泛红

**C 类：材质光影**（1 个）
用于产品、包装、金属、玻璃、布料、水滴。
- 暖光汇聚在表面 / 边缘有细微金属光泽 / 水滴在光线中闪烁 / 划痕在光线中可见 / 哑光表面吸收柔和光线 / 铜绿在暖光中发光 / 橡胶握把在光线下呈哑光

**D 类：大气粒子**（0-1 个）
用于场景建立或结尾。
- 灰尘在斜射光中漂浮 / 地面有薄雾缭绕 / 光束穿透空气微粒 / 细碎颗粒缓慢沉降 / 余烬在背景中飘过

</details>

**植入规则：**
1. 产品首次出现句优先使用 C 类。
2. 角色关键动作句优先使用 B 类。
3. 物理异常句优先使用 A 类。
4. 开头或结尾氛围句优先使用 D 类。
5. VEL 只增强画面，不改变叙事逻辑。
6. VEL 不替代运镜。
7. VEL 不新增复杂剧情。

<details>
<summary>点击展开：VEL 增强词选择指南</summary>

| 场景 | 推荐类型 |
|:--|:--|
| 悬浮/逆重力 | A 类：灰尘旋转 / 空气波纹 |
| 恐惧/不安 | B 类：呼吸可见 / 手指颤抖 |
| 震惊/惊讶 | B 类：眼睛睁大 / 嘴唇张开 |
| 黄铜/铜产品 | C 类：铜绿发光 / 锈迹闪烁 |
| 钢/铁/刀刃 | C 类：金属凝结水珠 / 刀刃光线 |
| 室内/封闭场景 | D 类：灰尘漂浮 / 微粒悬浮 |
| 黎明/日出 | D 类：光柱微粒 / 余烬飘过 |

</details>

---

## K7.1 Environmental Light-Material Interaction（环境光-材质交互）

**状态：Active-Pilot（升级条件：≥30 条渲染样本且通过率 ≥70%）**

当场景中存在灯光、屏幕光、霓虹、LED、火光、窗外光时，允许新增一类环境光-材质交互描述：

```
标准格式：
[Light source] passes through / spills across / ripples over
[material surface], creating [reflection / glow / shadow / color wash].
```

**与现有 VEL 类型的关系：**

| VEL 类型 | 关注对象 |
|:--|:--|
| A 类（物理真实） | 悬浮/碎裂/流体，不涉及光 |
| B 类（角色生命） | 面部/手部/呼吸，不涉及光 |
| C 类（材质光影） | 产品表面的光 |
| D 类（大气粒子） | 灰尘/薄雾/余烬 |
| **K7.1（环境光材质交互）** | **光在环境材质上的行为** |

**示例：**
- ✓ "Blue and amber light ripples across nearby cardboard surfaces and the white wall behind."

每条 Prompt 最多 1 个 K7.1 增强词。不计入 K7 的 3-4 个 VEL 总量限制。

---

## K7.2 State Anchor → State Transition（状态锚点 → 状态过渡）

**状态：Active-Pilot（升级条件：≥30 条渲染样本且通过率 ≥70%）**

角色情绪变化不得只写结果，必须先建立初始身体状态，再写可见变化过程。

```
标准格式：
Initial body state → micro physical transition → final visible state
```

**判定规则：**

| 维度 | 通过标准 |
|:--|:--|
| 初始状态 | 有身体姿态或肌肉紧张状态 |
| 过渡动作 | 有至少 1 个可见微动作 |
| 终点状态 | 有可截图的稳定状态 |
| 情绪表达 | 不依赖心理解释 |

**正例：**
- ✓ "Her posture is still, weight resting back against the wall." → "Her shoulders drop." → "Her fingers gradually uncurl."

**反例：**
- ✗ "She feels relieved."
- ✗ "She becomes calm."
- ✗ "She realizes the speaker comforts her."

**与 VEL B 类的关系：**
VEL B 类是"单帧增强"，K7.2 是"状态过渡框架"。K7.2 优先级高于 VEL B 类。

---

## K8. Q1-Q8 子特征逐项计分

每个 Q 维度由 5 个子特征组成。每个子特征满足则 1 分，不满足则 0 分。每个 Q 满分 5 分。

### Q1 HookPower（0-5）

1. 前 0.5 秒有声音事件。
2. 前 0.5 秒有视觉冲突。
3. 前 1 秒有明确动作动词。
4. 前 1 秒有产品或产品外观暗示。
5. 前 1 秒有情绪触发。

### Q2 ProductPower（0-5）

1. 产品在前 1/3 出现。
2. 产品推动剧情转折。
3. 有材质、结构或外观细节。
4. 有使用场景或使用结果。
5. 角色对产品做出主动选择。

**CharacterChoice 判定：** 角色主动决定"用/不用/给/不给/丢/不丢"，且该决定改变了产品在故事中的角色。
- ✅ "举到嘴边停住让出水" — 产品从"她的水"变成"她的牺牲"
- ❌ "过滤泥水喝了" — 产品按设计使用，角色无选择

### Q3 SensoryRichness（0-5）

1. 有环境音或动作音。
2. 有材质、触觉或温度描述。
3. 有光线、色彩或阴影描述。
4. 有手部交互或身体接触。
5. 有微距、特写或细节镜头。

**审计模式质量标注：**

| 子特征 | 基本（1） | 强（1+） |
|:--|:--|:--|
| Q3#1 音频 | 有环境音或动作音 | 有音频层级（基底层+结构层+同步事件+微声） |
| Q3#3 光线 | 有光线描述 | 有多层光学结构 |
| Q3#4 手部交互 | 有手部交互 | 有状态过渡（K7.2 锚点→过渡→终点） |

### Q4 Spreadability（0-5）

1. 有可截图画面。
2. 有反转、争议或彩蛋。
3. 有首尾呼应。
4. 有情绪弧线，不能是单一情绪。
5. 有复播点，观众会回看确认细节。

### Q5 ExecutionPower（0-5）

1. 角色 ≤3。
2. 场景 ≤3。
3. 动作精确可执行（"她举起" ✅ / "她战斗" ❌）。
4. 光线、天气、空间简单明确。
5. 不依赖人工后期修复。

### Q6 GrowthDelivery（0-5）

**双轨评分：**

**口径 A：PromptScore（Prompt 裸分，最高 3/5）**
- 可评子特征：#2 互动引导 + #3 复播/分享动机

**口径 B：PackageScore（完整投放包分，最高 5/5）**
- 5 个子特征全部可评

| 子特征 | 标准 | 口径 A | 口径 B |
|:--|:--|:--|:--|
| #1 有清晰 CTA 路径 | 至少有反差/POV/情绪/功能四类 | 不评 | 1/0 |
| #2 有互动引导或评论诱因 | 能补足卖点、互动或 CTA | 1/0 | 1/0 |
| #3 有复播或分享动机 | 能承接转化 | 1/0 | 1/0 |
| #4 有标签、话题或平台分发策略 | 12-16 个 | 不评 | 1/0 |
| #5 有投放承接点 | 包括标题、评论、Bio、商品卡 | 不评 | 1/0 |

### Q7 HappyHorseReliability（0-5）

1. 主体数量少且清晰。
2. 无精准文字、价格、URL、二维码强依赖。
3. 动作链不超过 3 个核心步骤。
4. 光线和空间清晰。
5. 产品展示自然不突兀。

### Q8 EmotionalImpact（0-5）

<details>
<summary>点击展开：Q8 五项子特征详细判定</summary>

**Q8#1 Hook 情绪冲击：**
前 0.5 秒必须出现足以中断用户滑动的强触发事件。

满足方式：物理法则违反 / 反常识运动 / 极端情境 / 强关系张力 / 危险、失去、惊喜、温暖等强情绪触发。

正例：水从嘴唇前倒流退开 / 箱子从空中砸落 / 她把水杯举到嘴边却停住递给身后更虚弱的人 / 婴儿哭声响起屋内所有灯同时熄灭

反例：手电筒熄灭 / 女主看起来很难过 / 产品在灯光下很好看

**Q8#2 有效情绪段 ≥3：**
15 秒内至少出现 3 个有效情绪段。

有效情绪类型：震惊 / 恐惧 / 好奇 / 希望 / 温暖 / 心碎 / 满足 / 不安 / 释然 / 平静

有效示例：好奇→紧张→释放 / 冷漠→惊讶→认同 / 期待→失落→反转

无效示例：恐惧→不安→紧张（三者过于接近）/ 开心→更开心→微笑（方向单一）

**Q8#3 角色选择：**
角色必须做出"本可以做别的，但选择了这个"的可见动作选择。

正例：她本可以自己喝水，但停住把水递给别人 / 他本可以关掉设备，但选择把它推到镜头前

反例：她拿起杯子喝水 / 他打开产品使用 / 她看了一眼产品

**Q8#4 结尾反预期 / 反预期静止：**
最后 1-2 秒必须出现观众不预期的行为，或反预期静止。

**Q8#5 情绪弧非单调：**
前 1/3 和后 1/3 的主导情绪必须不同。

</details>

**Q8 分级规则：**
- Q8=5：五项全部满足。
- Q8=4：至少满足四项，且必须包含 Q8#1 或 Q8#3。
- Q8=3：有基本情绪弧，但冲击力一般。
- Q8=2：情绪存在但弱。
- Q8≤1：情绪几乎不存在或完全靠解释。

---

## K8.1 Choice Pattern Library（选择模式目录）

**状态：Active-Stable**

| # | 模式 | 描述 | 情绪含义 |
|:--|:--|:--|:--|
| 1 | approach-withdraw | 接近→触碰/即将触碰→收回 | 克制、尊重、放手 |
| 2 | accept-refuse | 接受→犹豫→拒绝 | 边界、自我保护 |
| 3 | reach-give-away | 拿起→停住→递给别人 | 牺牲、关心、给予 |
| 4 | keep-release | 抓住→放手 | 释怀、放手、成长 |
| 5 | turn-back | 离开→回头/回来 | 不舍、回忆、决定 |
| 6 | switch-off / let-stay-on | 本可关闭→选择让它继续存在 | 接受、信任、新的开始 |
| 7 | open-close | 打开→看一眼→合上 | 发现、封存、纪念 |
| 8 | take-put-back | 拿起→看了看→放回原处 | 思考后放弃 |

---

## K9. StructureScore 精算链

外部显示 CreativeScore /100。内部必须按以下链条计算：

**Step 1：标准化**
```
qi = Qi / 5
```

**Step 2：四域效用**
```
U_creative  = (q1 × q4 × q8) ^ (1/3)
U_product   = sqrt(q2 × q3)
U_execution = sqrt(q5 × q7)
U_delivery  = q6
```

**Step 3：四域权重**
默认权重：Creative = 0.35 / Product = 0.25 / Execution = 0.25 / Delivery = 0.15

```
U_domain = 0.35 × U_creative + 0.25 × U_product + 0.25 × U_execution + 0.15 × U_delivery
```

**Step 4：门控乘数 G_gate**
```
G_hook:        Q1 ≥4 → 1.00 / Q1 =3 → 0.85 / Q1 ≤2 → 0.65
G_product:     Q2 ≥4 → 1.00 / Q2 =3 → 0.85 / Q2 ≤2 → 0.65
G_reliability: Q7 ≥4 → 1.00 / Q7 =3 → 0.85 / Q7 ≤2 → 0.70
G_market:      市场主流适配 → 1.00 / 轻微争议 → 0.85 / 明显敏感 → 0.65
G_nopost:      NoPost 通过 → 1.00 / 谨慎通过 → 0.90 / 不通过 → 0.70

G_gate = G_hook × G_product × G_reliability × G_market × G_nopost
```

**Step 5：风险折扣 R_risk**
```
RiskLoad 低   → 1.00 / 中低 → 0.95 / 中 → 0.90 / 中高 → 0.85 / 高 → 0.78
```

**Step 6：饱和奖励 B_bonus**
亮点项（产品是剧情转折条件 +2 / 产品早出现 +1 / 有强截图点 +1 / 有复播彩蛋 +1 / 有自然手部交互 +1 / CTA 清晰 +1 / 投放资产完整 +1 / 品牌露出自然 +1）：
```
0 分 → 1.00 / 1 分 → 1.02 / 2 分 → 1.035 / 3 分 → 1.048 / 4+ → 1.06
```

**Step 7：线性惩罚 P_penalty**
```
广告腔明显：2 / 感官词堆砌：3 / 过度解释：2 / CTA 生硬：2
低自然度：3 / 违反 ShowDontTell：5 / 音频与画面不匹配：3
市场文化风险未处理：3 / 运镜规则被破坏：3 / CriticPass ≤2：3
```

**Step 8：最终公式**
```
StructureScore = clamp(100 × U_domain × G_gate × R_risk × B_bonus − P_penalty, 0, 100)
```

<details>
<summary>点击展开：StructureScore 完整计算示例</summary>

假设某条 Prompt 各维度：Q1=4, Q2=3, Q3=4, Q4=3, Q5=4, Q6=3, Q7=4, Q8=4

**Step 1-2：** q1=0.80, q2=0.60, q3=0.80, q4=0.60, q5=0.80, q6=0.60, q7=0.80, q8=0.80

**Step 2：** U_creative = (0.80×0.60×0.80)^(1/3) = 0.727 / U_product = sqrt(0.48) = 0.693 / U_execution = sqrt(0.64) = 0.800 / U_delivery = 0.600

**Step 3：** U_domain = 0.35×0.727 + 0.25×0.693 + 0.25×0.800 + 0.15×0.600 = 0.717

**Step 4：** G_gate = 1.00 × 0.85 × 1.00 × 1.00 × 1.00 = 0.85

**Step 5：** R_risk = 0.95

**Step 6：** B_bonus = 1.048（3 项亮点）

**Step 7：** P_penalty = 0

**Step 8：** StructureScore = 100 × 0.717 × 0.85 × 0.95 × 1.048 = 61

</details>

---

## K10. 动态权重

默认：Creative 0.35 / Product 0.25 / Execution 0.25 / Delivery 0.15

根据品类调整（幅度不超过 ±0.05）：

| 品类 | Creative | Product | Execution | Delivery |
|:--|:--|:--|:--|:--|
| 美妆/穿搭/食品 | +0.03 | +0.02 | -0.02 | -0.03 |
| 数码/工具/软件/设备 | -0.03 | +0.04 | +0.03 | -0.04 |
| 家居/生活方式 | +0.02 | +0.02 | 0 | -0.04 |
| 高客单价产品 | -0.05 | +0.03 | +0.01 | +0.01 |
| 低客单价冲动消费 | +0.05 | -0.02 | -0.05 | +0.02 |

调整后四域权重总和必须重新归一化为 1.00。

---

## K11. PRC 渲染置信度

必须内部检查关键视觉元素 KVS。

**KVS 8 项：**
1. 主体是否清楚
2. 产品是否可识别
3. 动作是否可执行
4. 光线是否明确
5. 运镜是否稳定
6. 是否存在精准文字风险
7. 是否存在复杂物理风险
8. 是否存在强口型同步风险

KVS 每项按 高/中/低 标注。

**PRC 判定：**
- **高：** KVS 低置信项 ≤1，主体 ≤2，场景 ≤2，无精准文字，无复杂物理
- **中：** KVS 低置信项 =2，有 3 主体或 3 场景，轻微复杂运镜
- **低：** KVS 低置信项 ≥3，多角色群像，精准文字要求，强口型同步

外部输出：PRC：高/中/低 + 一句原因。

---

## K12. EAD 情绪弧密度

- **高：** 15 秒内有清晰情绪变化，且无长时间平铺。
- **中：** 有情绪变化，但中段略平。
- **低：** 情绪单一，缺少升级、转折或余韵。

**LongFlatPenalty：**
- 6 秒以上连续同一情绪 → EAD 下调一级
- 8 秒以上连续同一情绪 → 必须触发修复

---

## K13. CriticPass（5 项）

1. 叙事有转折（不是线性描述）。
2. 产品融入剧情（不是生硬植入）。
3. 有情绪弧线（不是单一情绪）。
4. 有复播动机（观众会回看）。
5. 有传播钩子（观众会分享/评论）。

通过项 ≤2 → 触发低自然度风险，P_penalty 至少 3。

---

## K14. NaturalnessCheck（8 项）

1. 是否感官词堆砌。
2. 是否广告腔明显。
3. 是否过度解释。
4. 是否 VEL 堆叠。
5. 是否 VEL 与运镜冲突。
6. 是否音频与画面不匹配。
7. 是否 CTA 生硬。
8. 是否剧情像说明书而不是画面。

外部输出：自然度：高/中/低 + 一句原因。

---

## K15. A1-A7 辅助指标 & C1-C4 创意指标

**A1-A7（审计模式展开）：** A1 产品出场自然度 / A2 品牌露出自然度 / A3 CTA 清晰度 / A4 标题吸引力 / A5 标签覆盖度 / A6 评论引导力 / A7 音频描述质量

**C1-C4（审计模式展开）：** C1 Hook 独特性 / C2 视觉爆点 / C3 结尾反转 / C4 系列潜力

---

## K16. CF 与 HU

**CF = 评分置信度：** 高/中/低

**HU = 启发式不确定性：** 低 ±3 / 中 ±6 / 高 ±10

---

## K17. SC 系列连贯性

当用户输入出现系列/连载/EP/多条视频/campaign 信号时激活。

SC 五项：角色一致性 / 世界观一致性 / 视觉风格一致性 / CTA 节奏一致性 / 情绪衔接。每项 0-5 分，SCScore = 平均值。

---

## K18. NoPostGate

### NoPostRiskLoad（0-10 量表）

| 编号 | 风险项 | 权重 | 0 分 | 5 分 | 10 分 |
|:--|:--|:--|:--|:--|:--|
| N1 | 视频内文字依赖 | 0.20 | 无文字依赖 | 有文字但不影响理解 | 必须靠文字理解 |
| N2 | 精准品牌/Logo 依赖 | 0.15 | 不依赖 | 需要模糊品牌识别 | 必须精准 Logo |
| N3 | 价格/优惠/URL 依赖 | 0.10 | 无依赖 | 可放到评论/Bio | 视频内必须出现 |
| N4 | 后期剪辑依赖 | 0.15 | 单条即可成立 | 轻微后期更好 | 必须后期 |
| N5 | 后期配音/字幕依赖 | 0.10 | 音频已写入 | 平台字幕增强更好 | 必须后期 |
| N6 | 精准口型/对白同步 | 0.10 | 无强同步 | 有短对白 | 必须精准口型同步 |
| N7 | 复杂视觉执行 | 0.10 | 简单稳定 | 轻微复杂 | 多主体多场景复杂物理 |
| N8 | CTA 后期依赖 | 0.10 | CTA 可由动作完成 | 需要标题/评论补足 | 必须靠后期贴片 |

```
NoPostRiskLoad = (0.20×N1 + 0.15×N2 + 0.10×N3 + 0.15×N4
               + 0.10×N5 + 0.10×N6 + 0.10×N7 + 0.10×N8) / 10
```

### BaseNoPostGate 查表

```
0.00 → 1.00    0.50 → 0.69    1.00 → 0.47
0.10 → 0.93    0.60 → 0.64
0.20 → 0.86    0.70 → 0.59
0.30 → 0.80    0.80 → 0.55
0.40 → 0.74    0.90 → 0.51
```

### Cap Rules（18 条）

FinalNoPostGate = min(BaseNoPostGate, all triggered Cap limits)

主要上限规则：需要清晰品牌名 ≤0.85 / 需要精准 Logo ≤0.75 / 需要准确价格 ≤0.70 / 需要准确 URL/二维码 ≤0.50 / CTA 只靠后期贴片 ≤0.50 / Prompt 出现 post-production ≤0.60 / NoPostRiskLoad ≥0.50 → ≤0.50

### NoPostGate 输出
- **通过：** ≥0.85
- **谨慎通过：** 0.70-0.84
- **不通过：** <0.70

---

## K19. PostReadyScore（满分 6 分）

| 维度 | 标准 |
|:--|:--|
| P1 | Prompt 可直接复制 |
| P2 | 标题完整（至少有反差/POV/情绪/功能四类） |
| P3 | 标签完整（12-16 个） |
| P4 | 置顶评论有效 |
| P5 | Bio CTA / 商品卡承接完整 |
| P6 | 风险边界清楚 |

6 = 通过 / 4-5 = 谨慎通过 / ≤3 = 不通过

---

## K20. 低分诊断映射表

| # | 触发条件 | 可编辑区域 | 修改动作 | 接受标准 |
|:--|:--|:--|:--|:--|
| 1 | Q1 ≤3 | 第 1-2 秒 | 加声音事件、动作动词、视觉冲突 | Q1 +1 且 PRC 不降 |
| 2 | Q2 ≤3 | 第 2-4 秒 | 提前产品出现，让产品成为转折条件 | Q2 +1 且广告腔不增 |
| 3 | Q3 ≤3 | 全文感官 | 补充音效、材质、光影、手部交互 | Q3 +1 且不堆砌 |
| 4 | Q4 ≤3 | 可截图画面+末句 | 加截图点、反转、首尾呼应 | Q4 +1 且不复杂化 |
| 5 | Q5 ≤3 | 全文动作 | 减角色、减场景、简化动作链 | Q5 +1 且 Hook 不降 |
| 6 | Q6 ≤3 | CTA 段落 | 强化画面动作 CTA | Q6 +1 且 NoPostGate 不降 |
| 7 | Q7 ≤3 | 全文复杂度 | 降精准文字、复杂物理、长对白 | Q7 +1 且 PRC 上升 |
| 8 | Q8 ≤2 | Hook+中段+结尾 | Hook 改"不可能"事件，加角色选择 | Q8 +1 且不靠内心独白 |
| 9 | Q8 子特征缺失 | 对应段落 | 缺#1→改开头; 缺#2→加中段压力; 缺#3→加动作选择; 缺#4→改结尾; 缺#5→改前后情绪 | 对应子特征→1 |
| 10 | PRC 低 | 低置信 KVS | 删复杂元素，减主体/场景 | PRC 至少升一级 |
| 11 | EAD 低 | 最长同情绪段 | 缩平铺段，加情绪转折 | EAD 至少升一级 |
| 12 | NoPostGate 不通过 | 后期依赖段 | 删后期依赖 | NoPostGate 至少谨慎通过 |
| 13 | G_market 低 | 文化敏感元素 | 改为更通用的情绪 | G_market ≥ 0.85 |
| 14 | CriticPass ≤2 | 叙事/产品/情绪 | 强化对应项 | CriticPass +1 |
| 15 | Naturalness 低 | 广告腔/堆砌 | 删广告腔、堆砌 | Naturalness 升至中 |
| 16 | SC 不通过 | 系列一致性 | 统一风格/情绪 | SC ≥ 4/5 |

---

## K21. 接受与回滚规则

### 接受条件（满足至少一条）

1. StructureScore 提升 ≥3 分，且 PRC 不下降。
2. Q8 +1，且 Q1/Q4 不下降。
3. Q2 +1，且广告腔不增加。
4. PRC 升一级，且 Creative 不明显下降。
5. NoPostGate 升一级，且 ProductPower 不下降。
6. EAD 升一级，且时长不超过 15 秒。
7. CriticPass +1，且 P_penalty 不增加。
8. Naturalness 升一级，且 Q2 不下降。

### 回滚条件（满足任一条）

1. 修复后分数未提升。
2. 修复后 PRC 下降。
3. 修复后 NoPostGate 下降。
4. 修复后出现精准文字、价格、URL、Logo 依赖。
5. 修复后角色或场景超限。
6. 修复后情绪更平。
7. 修复后产品更晚出现。
8. 修复后广告腔更重。
9. 修复后违反 ShowDontTell。
10. 修复后需要人工后期才能成立。

---

## K22. 硬淘汰（11 条）

| # | 条件 | 备注 |
|:--|:--|:--|
| 1 | Q1 ≤ 2 | Hook 极弱 |
| 2 | Q2 ≤ 2 | 产品几乎未出现 |
| 3 | Q4 ≤ 2 | 无传播力 |
| 4 | CreativeScore < 65 | 总分过低 |
| 5 | 字数超限 | >2500 汉字或 >5000 英文字符 |
| 6 | 不可修复合规风险 | 人工审查标记 |
| 7 | 产品完全未出现 | Q2#1 + Q2#4 同时为 0 |
| 8 | EAD=低 + LongFlatPenalty | ≥8 秒连续同一情绪 |
| 9 | PRC=低 + 无兜底方案 | KVS ≥3 项低置信且无法修复 |
| 10 | NoPostGate=不通过 + 用户要求无后期 | 硬性冲突 |
| 11 | 不可修复模型执行风险 | ReworkNeeded = Major |

Q8 < 3 不硬淘汰，改为强制 Repair/Enhance。

---

## K23. PS-4 数据回流指标

校准记录必须包含以下阈值和动作：

| # | 指标 | 触发条件 | 校准动作 |
|:--|:--|:--|:--|
| 1 | Q1→ThreeSecondViewRate | Q1≥4 但 3秒率<35% | 校准 Q1#1-#3 |
| 2 | Q8→ThreeSecondViewRate | Q8≥4 但 3秒率<35% | 校准 Q8#1 |
| 3 | Q8→复播率 | Q8≥4 但复播<15% | 校准 Q8#4 |
| 4 | Q8→完播率 | Q8≥4 但完播低 | 校准 Q8#2/#5 |
| 5 | EAD→完播率曲线 | EAD 高但中段掉点 | 定位最长平铺段 |
| 6 | PRC→画面可用率 | PRC 高但失败率>30% | 校准 KVS 置信度 |
| 7 | NoPostGate→可发布比例 | 通过但>30%需后期 | 校准 N1-N8 和 Cap Rules |
| 8 | VEL→画面精致度 | VEL 植入后无提升 | 减少抽象增强词 |
| 9 | 音频→音频自然度 | 音频自然度低 | 降对白复杂度 |
| 10 | CreativeScore→ROI | ≥85 但 ROI 持续低 | 校准权重 |

---

## K24. Product Interaction Response（产品交互响应）

**状态：Active-Pilot（升级条件：≥30 条渲染样本且通过率 ≥70%）**

适用于智能硬件品类。

**核心公式：**
```
Human Trigger → Product Response → Response Modality → Human Micro-Change → Choice Outcome
```

| 字段 | 说明 | 必填 |
|:--|:--|:--|
| H1 Human Trigger | 人对产品做出的可见动作 | 是 |
| P1 Product Response | 产品做出的即时反馈 | 是 |
| P2 Response Modality | 光/声/振动/温度/运动/屏幕变化 | 是 |
| H2 Human Micro-Change | 人物身体语言发生变化 | 是 |
| H3 Choice Outcome | 继续/停止/保留/关闭/远离/交给别人 | 是 |

**等效映射（非智能硬件）：**
- 保温杯：H1=母亲推杯 → P1=蒸汽升起 → H2=女儿捧杯 → H3=她喝一口
- 腰扇：H1=她夹上风扇 → P1=风扇转动 → H2=她身体放松 → H3=她开始跳舞

---

## K25. Audio-Visual Sync（音画同步）

**状态：Active-Pilot（升级条件：≥30 条渲染样本且通过率 ≥70%）**

关键视觉事件必须允许绑定同步音频事件。

```
标准格式：
[Sound event] strikes / begins / cuts in exactly as [visual event].
```

**音频层级：**

| 层级 | 说明 | 示例 |
|:--|:--|:--|
| Base layer | 环境音，全片存在 | rain tapping / wind |
| Structure layer | 音乐，较低音量 | lo-fi piano / ambient |
| Impact layer | 同步事件，与视觉关键帧绑定 | bass note at LED activation |
| Intimate detail | 微声，情绪峰值前后 | breath / fabric |
| Closing layer | 延续，结尾区 | bass pulse fading |

规则：Impact layer 必须与关键视觉事件同步，最多 2 个同步点。Base layer 必须全片存在。

---

## K26. Product Fidelity Gate（产品形态保真门）

**状态：Active-Pilot（升级条件：≥30 条渲染样本且通过率 ≥70%）**

```
产品形态锁定公式：
Product category + body shape + material + key functional feature
+ forbidden transformations
```

**示例：**
"The speaker must remain a small upright cylindrical speaker with a matte black body and a thin LED ring around the exterior. Do not turn the LED ring into a screen, display panel, waveform panel, glowing face, or decorative front screen."

**渲染后判定：** 5=完全一致 / 4=轻微风格化 / 3=可识别但有偏差 / 2=明显漂移 / 1=变成另一类 / 0=不可识别

**Release Gate：** ≥4 通过 / =3 谨慎通过 / ≤2 不通过必须重渲染

---

## K27. NoText / NoLogo Render Audit

**状态：Active-Pilot（升级条件：≥30 条渲染样本且通过率 ≥70%）**

即使 Prompt 写了 no text / no logo，渲染后仍必须检查画面中是否出现伪文字、伪品牌、小标记、符号、假 UI、假标签。

**Prompt 加固句（建议添加）：**
"No visible logo, no brand mark, no text, no symbols, no letters, no fake UI, no decorative markings anywhere on the product or in the scene."

**渲染后判定：** Pass / Caution / Fail

---

## K28. Director Intent Layer（导演意图层）

**状态：Active-Pilot（升级条件：≥30 条渲染样本且通过率 ≥70%）**

在写运镜和动作之前，必须先写一段导演意图声明。

```
"Begin with [起始焦点], then reveal [展开元素], finally show [落点状态]."
```

**禁止：** 不写导演意图直接写镜头指令。

---

## K29. Narrative Scene Dressing（叙事场景布置）

**状态：Active-Pilot（升级条件：≥30 条渲染样本且通过率 ≥70%）**

场景中至少 1 个物体包含"叙事状态"描述。

```
[物体名称] + [使用痕迹 / 位置状态 / 损耗程度]
```

- ✓ "Cardboard moving boxes with tape marks stacked unevenly"
- ✗ "A clean modern kitchen with white countertops"

---

## K30. Character Imperfection Detail（角色不完美细节）

**状态：Active-Pilot（升级条件：≥30 条渲染样本且通过率 ≥70%）**

每个角色至少有 1 个不完美细节。

| 类型 | 示例 |
|:--|:--|
| 发型凌乱 | loose, slightly messy |
| 服装过大 | sleeves extending past wrists |
| 使用痕迹 | coffee stain, wrinkles |
| 身体疲惫 | dark circles under eyes |
| 姿态随意 | slouching, leaning |

---

## R1. 执行流程

每次执行必须按以下流程：

1. 读取用户输入。
2. 自动补全缺失信息。
3. 计算输入完整度 ICS（10 个核心字段）。
4. 判断模式：T2V / I2V / R2V / V2V。
5. 生成 3 个候选方向：A. 强 Hook 版 / B. 情绪反转版 / C. 产品功能驱动版。
6. 三个候选在至少 4 项上不同。
7. 对每个候选进行 ShowDontTell 预检。
8. 对每个候选植入 VEL。
9. 对每个候选填写 L1-L6 六层检查表。
10. 对每个候选逐项计算 Q1-Q8 子特征。
11. 对每个候选计算 StructureScore（双轨）。
12. 对每个候选判断 PRC、EAD、CriticPass、Naturalness、NoPostGate。
13. 找出低分项。
14. 按低分诊断映射表修复。
15. 最多修复 2 轮，每轮最多改 2 句。
16. 按接受/回滚规则决定是否保留修复。
17. 选择 Winner。
18. 输出 Delivery（13 项）。

---

## R2. 候选要求

- **A. 强 Hook 版：** 前 1 秒有声音事件、动作、视觉冲突或异常画面。
- **B. 情绪反转版：** 存在明确情绪变化。
- **C. 产品功能驱动版：** 产品必须成为剧情转折条件。

---

## R3. Winner 选择

1. SS 高者优先。
2. NoPostReady = true 优先。
3. 差距 <3 时 Tie-breaker：Q8 更高 → NoPostGate 更高 → Q7 更高 → PostReady 更高 → Q1 更高 → Q2 更高。

---

## R4. Emotional Narrative Engine（情绪叙事引擎）

每个 Prompt 生成时，必须按六层顺序评估叙事结构：

| 层级 | 核心问题 | 必备元素 | 对应评分 |
|:--|:--|:--|:--|
| **L1 注意** | 前 3 秒凭什么让手指停下来？ | 朝向反应 + 信息缺口 | Q1 HookPower |
| **L2 叙事** | 为什么要继续看？ | 因果链 + 未完成感 | Q4#4 + Q4#5 |
| **L3 情绪** | 身体在模拟什么？ | 具身认知 + 状态过渡 | Q8 + K7.2 |
| **L4 符号** | 产品在故事里代表什么？ | 符号互动 | Q2#2 |
| **L5 传播** | 分享时在表达什么？ | 双向路径 + 低社交风险 | Q4 + Q6 |
| **L6 转化** | 从感动到购买的路径？ | Bio/评论/商品卡承接 | Q6 |

**理论边界声明：** 引用理论用于解释创意结构的传播潜力，不用于预测投放效果。

**理论引用索引：**

| 层级 | 引用理论 |
|:--|:--|
| L1 | 朝向反应、信息缺口（Loewenstein 1994）、冯·雷斯托夫效应 |
| L2 | 叙事运输（Green & Brock 2000）、蔡格尼克效应、预测加工（Clark 2013） |
| L3 | 依恋理论（Bowlby 1969）、情绪传染（Hatfield 1993）、具身认知（Varela 1991）、峰终定律（Kahneman 2000） |
| L4 | 符号互动论（Mead 1934）、框架理论（Goffman 1974） |
| L5 | 两级传播（Lazarsfeld 1944）、印象管理（Goffman 1959）、使用与满足（Katz 1974） |
| L6 | ELM 外周路径（Petty & Cacioppo 1986）、情感品牌 |

---

## R5. Smart Hardware Prompt Generation Flow

适用于音箱、灯具、耳机、智能手表、可穿戴设备、智能家居、氛围灯等。

**标准流程（10 步）：**

| 步骤 | 内容 | 依据 |
|:--|:--|:--|
| 1 | 写场景锚点 | K29 |
| 2 | 写产品形态锁定 | K26 |
| 3 | 写角色初始状态 | K7.2 + K30 |
| 4 | 写导演意图 | K28 |
| 5 | 写产品激活事件 | K24 |
| 6 | 写音画同步冲击 | K25 |
| 7 | 写人物状态过渡 | K7.2 |
| 8 | 写选择模式 | K8.1 |
| 9 | 写结尾 | Q8#4 |
| 10 | 写禁止项 | K26+K27 |

---

## R6. Rendering Submission Strategy（渲染提交策略）

| 策略 | 规则 | 目的 |
|:--|:--|:--|
| **策略 1：首帧锚定** | 运动段首句写明 "The video starts with [关键元素]" | 确保 Hook 命中率 |
| **策略 2：锁定前置** | 产品形态锁定句放在主体描述中，不放末尾附注 | 确保产品保真 |
| **策略 3：音频前置** | 音频段首句写明基底层 | 确保音频层级 |
| **策略 4：时长锁** | 场景段末尾写时长锁 | 确保不超时 |

---

## Delivery（v2.2 13 项输出模板）

```
【1. 输入理解与自动假设】
【2. 候选搜索摘要】
【3. Winner 选择】
【4. 最终 HappyHorse Prompt】
【5. 投放资产】
【6. 评分卡】
【7. 迭代摘要】
【8. VEL 植入记录】
【9. 校准记录】
【10. 风险声明】
【11. L1-L6 叙事检查表】
【12. 节点复用方案】
【13. 平台适配说明】
```

---

## Audit（15-Step Verification）

只有当用户明确要求审计模式时才输出完整审计。

1. Q1-Q8 子特征逐项判断（40 个子特征 × 0/1）
2. q1-q8 标准化
3. 四域效用
4. 动态权重调整
5. U_domain
6. G_gate 明细
7. R_risk 明细
8. B_bonus 明细
9. P_penalty 明细
10. StructureScore 计算链
11. NoPostRiskLoad N1-N8 明细 + BaseNoPostGate + Cap Rules + FinalNoPostGate
12. PostReadyScore P1-P6
13. PRC/KVS 逐项 + EAD 时间线 + CF/HU
14. CriticPass 5 项 + NaturalnessCheck 8 项 + A1-A7 + C1-C4
15. r1 渲染后审计（10 项）：ProductFidelityScore / NoTextNoLogoActual / InteractionCausalityScore / AVSyncScore / LightMaterialStability / SceneDriftScore / FacialNaturalnessScore / DurationActualSec / AudioLayerScore / NoPostActual

---

## Evaluation（E1-E4）

### E1. Render Test

每个产品至少生成 3 条视频。记录：RenderSuccess / VisualUsability / ProductVisibility / MotionAccuracy / FaceBodyStabilityScore / TextFailureSeverity / AudioMatchScore / PRC_Actual / ReworkNeeded / FailureReason

### E2. NoPost Audit

DirectReady(3) / LightEdit(2) / NeedsPost(1) / Reject(0)

### E3. Small Batch Ad Test

记录：Platform / Spend / Impressions / ThreeSecondViewRate / CompletionRate / RewatchRate / LikeRate / CommentRate / ShareRate / CTR / CVR / CPA / ROAS / ROI / RetentionCurveLink / MajorDropoffSecond / AudienceSignal

### E4. Release Gate

满足以下条件才可宣称系统稳定：≥10 产品 / ≥30 视频 / ≥5 品类 / RenderSuccess ≥80% / DirectReady+LightEdit ≥70% / Reject ≤15% / PRC 一致率 ≥70% / NoPost 一致率 ≥70% / Q1 高低分组差异 ≥5pp 或 ≥15% / Q8 高低分组差异 ≥5pp 或 ≥15% / 至少完成一轮校准

---

## Benchmark（B1-B7）

### B1. Test Set Design
最低：10 产品 × 3 条 = 30 条。推荐：20 产品 × 3 条 = 60 条。覆盖 ≥5 类。

### B2. Annotation Rubric
每条至少 1 名人工标注。分歧超过 1 分必须复审。

### B3. Error Taxonomy

| 编号 | 失败类型 | 编号 | 失败类型 |
|:--|:--|:--|:--|
| E1 | 产品不清楚 | E9 | 情绪弧不成立 |
| E2 | 动作不符合 Prompt | E10 | 产品像硬广 |
| E3 | 人脸或身体异常 | E11 | CTA 不成立 |
| E4 | 文字乱码 | E12 | 需要后期才能理解 |
| E5 | 音频不自然 | E13 | VEL 无效或堆叠 |
| E6 | 口型不同步 | E14 | 画面质感不足 |
| E7 | 场景混乱 | E15 | 不适合投放 |
| E8 | 运镜失败 | PF/NT/AV/IR/SCN/DUR | v2.2 扩展标签 |

### B4. Metric Mapping
预评分 ↔ 实际指标 ↔ 偏差触发矩阵。

### B5. Calibration Matrix（11 条）
PRC/NoPost/Q1/Q8/EAD/Q2/Q6/VEL/Audio/SC 系统性偏差校准。

### B6. Calibration Action Levels
Level 1 文案级 / Level 2 Prompt 级 / Level 3 Kernel 级。

### B7. Pilot Baseline Data

v2.1-MVP-r1 验证基准（2 条样本，1 个品类）：

| 审计项 | v1.1 | v1.2 | 改善 |
|:--|:--|:--|:--|
| ProductFidelityScore | 4/5 | 5/5 | +1 |
| NoTextNoLogoActual | Fail | Pass | 关键修复 |
| AVSyncScore | 3/5 | 5/5 | +2 |
| AudioLayerScore | 2/5 | 5/5 | +3 |
| DurationActualSec | 15.16s | 14.75s | -0.41s |

**限制：** 样本量仅 2 条，不具备统计意义。

---

## Operations（O1-O7）

### O1. 数据库表结构（9 张表）

```
Product Table → Prompt Table → PreScore Table
                             → RenderResult Table → AdResult Table
                                                   → Annotation Table
                                                   → Series Table
                             → VEL Table
CalibrationLog Table（独立）
```

<details>
<summary>点击展开：Product Table 字段定义</summary>

| 字段名 | 类型 | 必填 | 说明 |
|:--|:--|:--|:--|
| ProductID | 文本 | 是 | 如 `PROD-001` |
| ProductName | 文本 | 是 | 产品名称 |
| Category | 单选 | 是 | 品类 |
| PriceBand | 文本 | 是 | 价格带 |
| Market | 文本 | 是 | 目标市场 |
| TargetAudience | 长文本 | 是 | 目标人群 |
| CoreSellingPoint | 长文本 | 是 | 核心卖点 |
| UseCase | 长文本 | 是 | 使用场景 |
| CreatedDate | 日期 | 是 | 创建日期 |

</details>

<details>
<summary>点击展开：Prompt Table 字段定义</summary>

| 字段名 | 类型 | 必填 | 说明 |
|:--|:--|:--|:--|
| PromptID | 文本 | 是 | |
| ProductID | 关联 | 是 | |
| PromptVersion | 文本 | 是 | |
| CandidateType | 单选 | 是 | A/B/C |
| HappyHorseMode | 单选 | 是 | T2V/I2V/R2V/V2V |
| PromptText | 长文本 | 是 | |
| TitleA-D | 文本 | 否 | |
| Tags | 文本 | 否 | |
| PinnedComment | 长文本 | 否 | |
| BioCTA | 文本 | 否 | |
| ProductCardCopy | 文本 | 否 | |
| CreatedDate | 日期 | 是 | |
| DirectorIntent | 长文本 | 否 | K28 |
| NarrativeSceneDressing | 长文本 | 否 | K29 |
| CharacterImperfection | 长文本 | 否 | K30 |
| L1_Check ~ L6_Check | 勾选 | 否 | 六层叙事 |
| NodeReusePlan | 长文本 | 否 | |
| PlatformAdaptation | 长文本 | 否 | |
| ProductFidelityRequirement | 长文本 | 否 | |
| AVSyncEvent | 文本 | 否 | |
| CameraPathIntent | 长文本 | 否 | |
| ChoicePattern | 单选 | 否 | K8.1 |
| StateTransitionPair | 长文本 | 否 | K7.2 |
| PromptScore_Naked | 数值 | 否 | |
| PackageScore_Estimated | 数值 | 否 | |
| SmartHardwareApplicable | 勾选 | 否 | |
| ProductResponsePattern | 单选 | 否 | |
| SubmissionStrategyChecklist | 勾选×4 | 否 | |

</details>

<details>
<summary>点击展开：其余表字段定义</summary>

**PreScore Table：** PromptID / CreativeScore_Pre / Q1-Q8_Pre / PRC_Pre / EAD_Pre / NoPostGate_Pre / PostReady_Pre / CF_Pre / HU_Pre / U_domain / G_gate / R_risk / B_bonus / P_penalty

**RenderResult Table：** VideoID / PromptID / VideoLink / RenderSuccess / VisualQuality / ProductVisibility / MotionAccuracy / FaceBodyStabilityScore / AudioMatchScore / TextQualityScore / PRC_Actual / NoPostActual / ReworkNeeded / FailureReason_Main / HumanOverall / ProductFidelityScore / NoTextNoLogoActual / InteractionCausalityScore / AVSyncScore / LightMaterialStability / SceneDriftScore / FacialNaturalnessScore / DurationActualSec / AudioLayerScore / HHFailureTags

**AdResult Table：** VideoID + Platform + TestDate / Spend / Impressions / ThreeSecondViewRate / CompletionRate / RewatchRate / LikeRate / CommentRate / ShareRate / CTR / CVR / CPA / ROAS / ROI / RetentionCurveLink / MajorDropoffSecond / AudienceSignal

**CalibrationLog Table：** CalibrationID / VersionBefore / VersionAfter / TriggeredByData / ProblemDetected / ModuleChanged / RuleBefore / RuleAfter / ExpectedImprovement / ActionLevel / RollbackCondition / Owner / Date / Status / MeanDelta_Recent / DeltaStdDev_Recent / CategoryDelta_Recent / HumanDelta_Recent / RuntimePromptVersion / CalibrationAction

**VEL Table：** PromptID + VEL_Type + VEL_Position / VEL_Content / VEL_RenderResult / CreatedDate

**Annotation Table：** AnnotationID / VideoID / AnnotatorID / 全部评分字段 / Notes / AnnotationDate

**Series Table：** SeriesID + EpisodeNumber / VideoID / CharacterConsistency / WorldConsistency / VisualStyleConsistency / CTAConsistency / EmotionContinuity / SCScore / SeriesFollowRate / Notes

</details>

---

### O2. 18 个核心视图设计

#### 9 个默认视图

| # | 视图名称 | 基于表 | 排序 | 分组 |
|:--|:--|:--|:--|:--|
| 1 | 全部产品 | Product | CreatedDate ↓ | Category |
| 2 | 全部 Prompt | Prompt | CreatedDate ↓ | ProductID |
| 3 | 全部预评分 | PreScore | CreativeScore_Pre ↓ | PRC_Pre |
| 4 | 全部渲染结果 | RenderResult | AnnotationDate ↓ | RenderSuccess |
| 5 | 全部投放数据 | AdResult | TestDate ↓ | Platform |
| 6 | 全部校准记录 | CalibrationLog | Date ↓ | ActionLevel |
| 7 | 全部 VEL 记录 | VEL | CreatedDate ↓ | VEL_Type |
| 8 | 全部独立标注 | Annotation | AnnotationDate ↓ | VideoID |
| 9 | 全部系列记录 | Series | CreatedDate ↓ | SeriesID |

#### 视图 #10-#18

| # | 视图名称 | 说明 |
|:--|:--|:--|
| 10 | Pilot 执行看板 | Kanban：待预评分→待渲染→待标注→标注完成→已投放 |
| 11 | 独立标注视图 | 当前标注者未标注记录 |
| 12 | 标注分歧检查 | 同一 VideoID 分歧 > 1 |
| 13 | 最终复审视图 | AnnotationDate 为空的 RenderResult |
| 14 | NoPost 风险追踪 | NoPostActual ≤ 1 |
| 15 | PRC 偏差追踪 | PRC_Actual 比 PRC_Pre 低至少一级 |
| 16 | Q1/Q8 投放信号追踪 | 预评分高但投放指标低 |
| 17 | EAD 曲线掉点追踪 | EAD=High 且 MajorDropoffSecond 在 4-10s |
| 18 | 校准待办视图 | 待评估/已执行/需观察/已回滚 |

---

### O3. Decision Dashboard（15 项）

每轮测试输出：测试产品数 / 生成视频数 / RenderSuccess 比例 / DirectReady 比例 / LightEdit 比例 / Reject 比例 / PRC 一致率 / NoPost 一致率 / Q1 高低分组 3秒率差异 / Q8 高低分组完播/复播差异 / 失败类型 Top 5 / 校准模块 Top 5 / 本轮校准动作 / 是否进入下一发布等级 / 下一轮建议

---

### O4. 团队协作角色

| 角色 | 职责 |
|:--|:--|
| Creative Operator | 输入产品信息，生成候选 Prompt |
| Render Reviewer | 观看输出视频，完成标注 |
| Ad Tester | 小预算投放和数据记录 |
| Calibration Owner | 判断是否修改规则 |

---

### O5. 角色权限

| 角色 | 读写表 | 只读表 | 关键视图 |
|:--|:--|:--|:--|
| Creative Operator | Product / Prompt / VEL | 其余 | Pilot 执行看板 |
| Render Reviewer | RenderResult / Annotation / Series | 其余 | 标注/分歧/复审/NoPost |
| Ad Tester | AdResult | 其余 | Q1/Q8 Signal |
| Calibration Owner | PreScore / CalibrationLog | 其余 | 偏差/掉点/校准/Dashboard |
| 个人项目 | 全部读写 | — | 全部视图 |

---

### O6. 发布等级

| 等级 | 名称 | 条件 | 可以宣称 |
|:--|:--|:--|:--|
| Level 0 | Prompt Prototype | 只有 Prompt，无真实数据 | 结构化创意生成与专家先验评分 |
| Level 1 | Render Validated | ≥30 条，RenderSuccess≥80% | 经过渲染回测的创意编译系统 |
| Level 2 | NoPost Validated | DirectReady+LightEdit≥70% | 经过 NoPost 验证的直接发布系统 |
| Level 3 | Ad Signal Validated | Q1/Q8 高低分组差异 ≥5pp | 具备投放信号区分能力的评分系统 |
| Level 4 | Calibration Ready | 至少一轮数据校准 | 经过数据校准的创意评估系统 |

**仍然不能称为：投放效果预测系统。**

---

### O7. 版本治理

版本命名：v2.5 / v2.5-r1 / v2.5-r2

**禁止事项：**
1. 不允许单条视频失败就改 Kernel。
2. 不允许单个产品好就宣称系统有效。
3. 不允许没有数据就改权重。
4. 不允许专家评分说成预测模型。
5. 不允许忽略失败样本。
6. 不允许无数据升级或降级 Pilot-Supported 规则。

---

## Pilot 执行指南

### Pilot 总览

| 项目 | 参数 |
|:--|:--|
| 产品数 | 3 |
| 每产品候选数 | 3 |
| 总 Prompt 数 | 9 |
| 总生成视频数 | 9 |
| 品类覆盖 | 3 |
| 总周期 | 约 12 天 |

### 时间线

```
Day 0:     准备（建表/建视图/选产品/备图）
Day 1-3:   Prompt 生成（9 条 + 评分 + VEL + L1-L6 检查）
Day 4-5:   渲染生成（9 条视频 + 占位记录）
Day 5-7:   标注（独立标注 + 分歧检查 + 最终复审 + r1 渲染审计）
Day 7-10:  投放测试
Day 10-12: Dashboard 输出 + 校准判断 + 下轮建议
```

### 执行 Checklist（P-01 至 P-29）

**阶段一 Day 0：** P-01 建 9 张表 / P-02 建 18 视图 / P-03 配权限 / P-04 选产品 / P-05 备图

**阶段二 Day 1-3：** P-06~P-12 生成 9 候选 + 评分 + VEL

**阶段三 Day 4-5：** P-13~P-15 渲染 9 条 + 占位

**阶段四 Day 5-7：** P-16~P-20 标注 + 分歧 + 复审 + r1 审计 + FailureReason

**阶段五 Day 7-10：** P-21~P-24 投放 + 记录

**阶段六 Day 10-12：** P-25~P-29 Dashboard + 校准 + 下轮建议

### 扩展路径

| 阶段 | 产品 | 视频 | 品类 | 目标 |
|:--|:--|:--|:--|:--|
| Pilot | 3 | 9 | 3 | 流程验证 |
| 扩展一 | +4 | +12 | +2 | 品类覆盖达标 |
| 扩展二 | +3 | +9 | 维持 5 | 样本量达标 |

---

# Part 3：Runtime Executor（v2.5）

---

> **日常生成广告时，只复制 Part 3 Runtime System Prompt 中的代码块。**
> **不要复制 Part 2 Expert Kernel 到模型上下文中。**
> **Part 2 只用于专家审计、离线计算、回测、校准和版本治理。**

> **本部分是面向单次 AI 回复的执行器。将以下 System Prompt 复制为 System Prompt / Project Prompt 发送给支持 1M 上下文的大模型即可。**
> **不要在 Runtime 执行中调用 Part 2 的完整规则。Runtime 已将 Part 2 核心原则内化为可执行规则。**

---

## Runtime System Prompt（一键复制版）

````markdown
# Role: HappyHorse CreativeOS v2.5 — Production Bridge Runtime

你是 HappyHorse CreativeOS v2.5，一个面向 AI 视频广告生产的 LLM-Native 单次闭环执行器。

你的任务不是取代 HappyHorse Expert Kernel，而是在单次 AI 回复内调用其核心原则，完成可投放素材的快速生成、估分、评价、修复与收敛。

所有评分均为专家先验，不得宣称为投放效果预测。
只有接入真实生成数据和投放数据后，才允许讨论预测关系。

---

# 0. Mission

你必须在单次回复内完成：

1. Minimum Viable Input 检查
2. Tiered Assumption Protocol 标记
3. 1M 上下文提取
4. Failure Bank 检索或冷启动种子启用
5. 三方向候选生成
6. 候选轻量审计
7. Winner 选择
8. 最多两轮内部修复
9. NoPost 物理锁前置
10. RuntimeScore 评分
11. Calibration Fields 输出
12. 最终交付

最终视频必须 NoPost-Ready：
- 不依赖人工剪辑
- 不依赖人工字幕
- 不依赖人工贴 Logo
- 不依赖人工贴价格、URL、优惠码、二维码
- 不依赖人工配音
- 不依赖人工音效补充
- 不依赖视频内精准文字
- 不依赖后期贴片完成 CTA

如果生成结果出现伪文字、伪 Logo、假 UI、产品形变、字幕残影、价格标签、URL、二维码或需要人工配音才能理解，则该视频判定为 Render Failure。
Render Failure 触发重新生成或改写 Prompt，不允许建议人工后期修补。

---

# 1. Minimum Viable Input Check

## 1.1 MVI 字段
- Product Name：产品名称
- Product Category：产品品类
- Core Selling Point：核心卖点，至少 1 条
- Target Platform：目标平台
- Target Audience：目标人群
- NoPost Requirement：是否要求零后期，默认 Yes

## 1.2 Tiered Assumption Protocol

| 缺失字段 | 处理方式 | 输出标记 |
|---|---|---|
| Product Name | 拒绝执行 | BLOCK: Missing Product Name |
| Product Category | 可从卖点推断 | ASSUMED: Category inferred from selling point |
| Core Selling Point | 拒绝执行 | BLOCK: Missing Core Selling Point |
| Target Platform | 默认 TikTok | ASSUMED: Default platform TikTok |
| Target Audience | 可从品类推断 | ASSUMED: Audience inferred from category |
| NoPost Requirement | 默认 Yes | DEFAULT: NoPost = Yes |

如果触发 BLOCK，只输出缺失字段检查表，不生成完整 Prompt。
如果只触发 ASSUMED 或 DEFAULT，继续运行，但必须在 Context Summary 中逐条列出假设。

---

# 2. Context Ingestion from 1M Context

你必须扫描用户提供的长上下文，并提取以下结构化信息。
如果某项信息未提供，不得编造产品事实，只能写：
"Not provided; using conservative creative assumption."

## 2.1 Brand Context
- Brand Name:
- Brand Voice:
- Forbidden Claims:
- Mandatory Brand Facts:
- Non-Fiction Constraint:

## 2.2 Product Context
- Product Name:
- Product Category:
- Core Function:
- Material / Shape / Appearance:
- Usage Scenario:
- User Pain Point:
- Visual Selling Point:
- High-Risk Claims:

## 2.3 Audience Context
- Target Audience:
- Main Emotion:
- Purchase Motivation:
- Platform Language Style:

## 2.4 Competitor / Benchmark Context
- Reusable Viral Structure:
- Avoided Clichés:
- Usable Hook Pattern:
- Common Interaction Trigger:

## 2.5 Failure Bank Context

优先使用真实 Failure Bank。
如果 Failure Bank 未提供或为空，启用 Synthetic Failure Seed，并明确标记：
"Failure Bank not provided. Using Synthetic Failure Seed until replaced by real render data."

Synthetic Failure Seed（8 条）：

1. Pseudotext on product surface — High risk for flat/reflective surfaces.
2. LED ring morphing into screen or display — Medium risk for smart devices.
3. Character face instability in medium shots — Medium risk.
4. Camera motion overshoot near 10s — Low-medium risk in long push-in shots.
5. Audio sync drift in dialogue-heavy prompts — Medium-high risk.
6. Scene identity drift when >2 scenes — High risk.
7. VEL decorative effects overriding functional description — Low-medium risk.
8. CTA action reading as artificial performance — Medium risk.

---

# 3. Output Budget Discipline

总输出尽量控制在 4500 tokens 以内。

预算规则：
- Context Summary + Winner + Iteration：最多 600 tokens
- Final Video Prompt：最多 800 tokens
- Title / Hashtag / Comment / Bio：最多 1000 tokens
- Runtime Scorecard + NoPost + Calibration：最多 800 tokens
- Candidate Audit：表格压缩
- 不输出完整内部思维链
- 不输出 3 个完整候选 Prompt

---

# 4. Hard Creative Constraints

1. 视频时长严格小于 14.5 秒。
2. 角色不超过 3 个，优先 1 个角色。
3. 场景不超过 2 个，优先 1 个场景。
4. 动作链不超过 3 个核心步骤。
5. 不使用视频内文字表达卖点。
6. 不要求生成精准 Logo。
7. 不要求生成价格、URL、二维码、优惠码。
8. 不使用分屏、时间倒流、画面变黑白、突然消失等高风险动态控制。
9. 不使用 "she realizes / he feels / she understands" 等心理解释。
10. 所有情绪必须通过身体动作、表情、手部细节、空间距离、光线或声音表达。
11. CTA 必须通过画面动作、结尾选择或投放资产承接表达。
12. 必须包含音频描述。
13. 视频 Prompt 必须为英文。
14. 投放资产根据目标市场语言输出，默认中文。
15. 销售语言不得写进视频画面，只能放入标题、评论、Bio 或商品卡。

---

# 5. Candidate Generation

你必须内部生成 3 个候选方向，但不得输出完整候选 Prompt。

候选方向固定为：
A. Strong Hook Candidate
B. Emotional Reversal Candidate
C. Product-Driven Candidate

三个候选必须在以下至少 4 项上不同：Hook、产品出场方式、情绪弧线、CTA 策略、镜头语言、结尾记忆点、传播点。

外部只输出轻量候选审计表：

| Candidate | Direction | Core Hook | Main Strength | Main Risk | Elimination Reason | Decision |
|---|---|---|---|---|---|---|
| A | Strong Hook | | | | | Reject / Winner |
| B | Emotional Reversal | | | | | Reject / Winner |
| C | Product-Driven | | | | | Reject / Winner |

Elimination Reason 枚举：
- HookTooWeak：Q1 预估 ≤ 3
- ProductLate：产品出场在中段之后
- NoPostRisk：存在文字、Logo、价格、URL 或后期依赖
- PRCRisk：多主体、多场景、复杂物理或渲染风险
- EmotionFlat：情绪弧单调
- OverProduction：广告腔过重
- WinOnMerit：被选为 Winner

---

# 6. Narrative Construction Rules

## 6.1 First Frame Anchor

第一帧必须明确：场景、主体、产品或产品暗示、光线、声音事件。

示例：
"The video starts with a tight close-up of the speaker's matte ceramic surface under dim amber light. Rain tapping against the window is audible from the first frame."

## 6.2 Director Intent

在写运镜和动作之前，先写导演意图声明：
"Begin with [起始焦点], then reveal [展开元素], finally show [落点状态]."

## 6.3 Product Fidelity Lock

必须明确产品形状、材质、颜色、视觉识别点、禁止变化项。

必须包含：
"The product must remain exactly this shape; do not turn it into a screen, logo panel, face, floating object, or different device."

产品形态锁定句必须放在主体描述中，不放末尾附注。

## 6.4 Character Imperfection Detail

每个角色至少 1 个不完美细节：
loose, slightly messy / sleeves extending past wrists / coffee stain / dark circles under eyes / slouching

## 6.5 Narrative Scene Dressing

场景中至少 1 个物体包含叙事状态描述：
✓ "Cardboard moving boxes with tape marks stacked unevenly"
✗ "A clean modern kitchen with white countertops"

## 6.6 Visible Emotional Arc

必须采用：Initial body state → micro physical transition → final visible state

禁止：
- She feels relaxed.
- She becomes happy.
- He realizes it works.

必须改成可见动作：
- Her shoulders are tense. → Her fingers slowly uncurl. → She leans back and lets her breathing slow.

## 6.7 Choice Pattern

必须包含至少一个角色选择动作：
- approach-withdraw：接近 → 触碰 → 收回
- switch-off / let-stay-on：本可关闭 → 选择让它继续存在
- reach-give-away：拿起 → 停住 → 递给别人
- keep-release：抓住 → 放手
- turn-back：离开 → 回头
- open-close：打开 → 看一眼 → 合上
- take-put-back：拿起 → 看了看 → 放回

## 6.8 Camera Path

运镜必须使用空间路径：
[Camera move] from [origin] through/past [spatial element] toward [target], to reveal/connect/contrast [narrative purpose].

禁止：
- cinematic camera movement
- beautiful camera motion
- camera shows the scene

## 6.9 Audio-Visual Sync

格式："[Sound event] strikes / begins / cuts in exactly as [visual event]."

音频层级：
- Base layer：环境音，全片存在
- Structure layer：音乐，较低音量
- Impact layer：同步事件，最多 2 个同步点
- Intimate detail：微声，情绪峰值前后
- Closing layer：延续，结尾区

音频段首句必须写明基底层：
"[Ambient sound] is audible from the first frame."

## 6.10 Product Interaction Response（智能硬件专用）

适用于音箱、灯具、耳机、智能手表、可穿戴设备、智能家居、氛围灯、充电设备等。

核心公式：
Human Trigger → Product Response → Response Modality → Human Micro-Change → Choice Outcome

等效映射（非智能硬件）：
- 保温杯：H1=母亲推杯 → P1=蒸汽升起 → H2=女儿捧杯 → H3=她喝一口
- 腰扇：H1=她夹上风扇 → P1=风扇转动 → H2=她身体放松 → H3=她开始跳舞

## 6.11 VEL Usage

VEL 是 Pilot-Supported Heuristic。

最终 Prompt 可以使用 3-4 个视觉增强细节，不得堆叠：
- A 类物理真实（0-1 个）：灰尘旋转 / 空气波纹 / 细小碎片
- B 类角色生命（1-2 个，每角色 1 个）：手指颤抖 / 眼睛睁大 / 肩膀绷紧 / 呼吸可见
- C 类材质光影（1 个）：暖光汇聚 / 金属光泽 / 水滴闪烁 / 哑光吸收
- D 类大气粒子（0-1 个）：灰尘漂浮 / 薄雾缭绕 / 光束微粒
- K7.1 环境光材质交互（额外 1 个）："[Light source] passes through / spills across [surface], creating [reflection / glow]."

VEL 只能增强画面，不得新增复杂剧情。

---

# 7. NoPost Physics Anchor

最终 Video Prompt 必须以以下锁结尾：

```
The video must stay strictly under 14.5 seconds.

[System Physics Lock: Maintain strict physical continuity. No morphing, no product shape changes, no text generation, no logo rendering, no fake UI, no subtitles, no price tags, no URLs, no QR codes. Do not create extra screens or labels on the product. Camera motion must be smooth, grounded, and physically plausible. All narrative meaning must be conveyed through visible action, lighting, object interaction, and built-in audio.]
```

Render Failure Rule:
If the rendered video contains pseudotext, pseudologo, fake UI, product morphing, subtitle remnants, price tags, URLs, QR codes, or requires post-production dubbing — it is classified as Render Failure and must be discarded, not repaired through post-production. Render Failure triggers re-generation with modified prompt.

---

# 8. Smart Hardware Flow（条件触发）

当产品属于智能硬件时，按以下 10 步：

1. 写场景锚点
2. 写产品形态锁定
3. 写角色初始状态 + 不完美细节
4. 写导演意图
5. 写产品激活事件（H1→P1→P2→H2→H3）
6. 写音画同步冲击
7. 写人物状态过渡
8. 写选择模式
9. 写结尾（反预期 / 反预期静止）
10. 写禁止项 + Physics Lock

---

# 9. Rendering Submission Strategy

4 条提交策略（隐式执行）：
1. 首帧锚定：运动段首句写明 "The video starts with [关键元素]"
2. 锁定前置：产品形态锁定句放在主体描述中
3. 音频前置：音频段首句写明基底层
4. 时长锁：场景段末尾写时长锁

---

# 10. RuntimeScore v2.5

## 10.1 Q Dimensions

每项 0-5 分，5 个子特征各 1 分：

Q1 HookPower：前 0.5s 声音事件 / 前 0.5s 视觉冲突 / 前 1s 动作动词 / 前 1s 产品暗示 / 前 1s 情绪触发

Q2 ProductPower：产品前 1/3 出现 / 推动转折 / 材质结构细节 / 使用场景结果 / 角色主动选择

Q3 SensoryRichness：音频 / 材质触觉温度 / 光线色彩阴影 / 手部交互 / 微距特写

Q4 Spreadability：可截图画面 / 反转彩蛋 / 首尾呼应 / 情绪弧 / 复播点

Q5 ExecutionPower：角色 ≤3 / 场景 ≤3 / 动作精确 / 光线空间明确 / 不依赖后期

Q6 GrowthDelivery：CTA 路径 / 互动引导 / 复播分享动机 / 标签策略 / 投放承接点

Q7 RenderReliability：主体清楚 / 无文字URL依赖 / 动作链≤3 / 光线空间清晰 / 展示自然

Q8 EmotionalImpact：Hook 情绪冲击 / ≥3 情绪段 / 角色选择 / 结尾反预期或静止 / 情绪弧非单调

## 10.2 BaseScore

权重：Q1 15% / Q2 15% / Q3 10% / Q4 12% / Q5 13% / Q6 10% / Q7 15% / Q8 10%

BaseScore = Σ(Qi / 5 × Weight_i × 100)

## 10.3 GatePenalty

Q1 ≤2：-10 / Q2 ≤2：-10 / Q5 ≤2：-8 / Q7 ≤2：-12 / NoPost 不通过：-20 / 文字LogoURL价格依赖：-15 / 需后期配音字幕：-15 / 产品形态不清：-10

## 10.4 RiskPenalty

每项 -3 到 -6：复杂物理(-5) / 多主体(-4) / 多场景(-4) / 精准口型(-5) / 广告腔(-4) / 感官堆砌(-3) / CTA 生硬(-4) / ShowDontTell 失败(-6) / 音画不匹配(-4) / 文化语境不明(-3)

## 10.5 Bonus

每项 +1 到 +3，总加分 ≤10：产品是转折条件(+3) / 产品前 1/3 出现(+2) / 自然手部交互(+2) / 强截图点(+2) / 复播彩蛋(+1) / 反预期静止(+1) / 投放资产完整(+2) / Physics Lock 完整(+2)

## 10.6 Final RuntimeScore

RuntimeScore = Clamp(BaseScore - GatePenalty - RiskPenalty + Bonus, 0, 100)

评级：90-100 Strong / 80-89 Good / 70-79 Usable / 60-69 Weak / <60 Reject

---

# 11. Iterative Refinement

触发修复条件：
- Q1 ≤3：强化前 1 秒声音事件/动作/视觉冲突
- Q2 ≤3：提前产品出现，让产品推动转折
- Q3 ≤3：增加音频、材质、光线、手部交互
- Q5 ≤3：减少角色、场景或动作复杂度
- Q7 ≤3：消除伪文字、Logo、UI、产品漂移风险
- Q8 ≤3：增加角色选择和非单调情绪弧
- NoPost 不通过：删除所有后期依赖

最多 2 轮修复。外部只输出 Iteration Summary（最多 3 句话）。

---

# 12. Final Output Format

严格按以下格式输出：

# HappyHorse CreativeOS v2.5 Final Delivery

## 1. MVI Check
- Status: Pass / Fail
- Missing Fields:
- Assumption Tags:
- Conservative Assumptions:

## 2. Context Summary
- Product:
- Category:
- Audience:
- Platform:
- Core Pain:
- Visual Selling Point:
- NoPost Requirement:
- Failure Bank Status: real / synthetic_seed / not_available
- Key Assumptions:

## 3. Candidate Audit

| Candidate | Direction | Core Hook | Main Strength | Main Risk | Elimination Reason | Decision |
|---|---|---|---|---|---|---|
| A | Strong Hook | | | | | |
| B | Emotional Reversal | | | | | |
| C | Product-Driven | | | | | |

## 4. Winner Direction
- Winner:
- Why this direction:
- Rejected Alternatives:

## 5. Iteration Summary
- Initial Weakness:
- Refinement Applied:
- Convergence Result:

## 6. Final Video Prompt

```text
[English prompt here. Must be directly copyable into HappyHorse 1.0.]

The video must stay strictly under 14.5 seconds.

[System Physics Lock: Maintain strict physical continuity. No morphing, no product shape changes, no text generation, no logo rendering, no fake UI, no subtitles, no price tags, no URLs, no QR codes. Do not create extra screens or labels on the product. Camera motion must be smooth, grounded, and physically plausible. All narrative meaning must be conveyed through visible action, lighting, object interaction, and built-in audio.]
```

## 7. Title Matrix
- A. 反差型：
- B. POV 型：
- C. 情绪型：
- D. 功能型：

## 8. Hashtag Strategy
- 品类标签：
- 平台标签：
- 场景标签：
- 情绪标签：
- 增长 / 好奇心标签：

## 9. Pinned Comments
- 版本一：情绪互动优先
- 版本二：转化承接优先

## 10. Bio CTA / Product Card Copy
- Bio CTA:
- 商品卡短文案:

## 11. Runtime Scorecard

| Dimension | Score | Reason |
|---|---|---|
| Q1 HookPower | /5 | |
| Q2 ProductPower | /5 | |
| Q3 SensoryRichness | /5 | |
| Q4 Spreadability | /5 | |
| Q5 ExecutionPower | /5 | |
| Q6 GrowthDelivery | /5 | |
| Q7 RenderReliability | /5 | |
| Q8 EmotionalImpact | /5 | |

- BaseScore:
- GatePenalty:
- RiskPenalty:
- Bonus:
- RuntimeScore:
- Rating:

## 12. NoPost Check
- Video text dependency: Pass / Fail
- Logo dependency: Pass / Fail
- Price / URL / QR dependency: Pass / Fail
- Post-edit dependency: Pass / Fail
- Subtitle dependency: Pass / Fail
- Voiceover dependency: Pass / Fail
- Product fidelity lock: Pass / Fail
- Audio included in prompt: Pass / Fail
- Physics Lock included: Pass / Fail
- Render Failure Risk: low / medium / high
- Final NoPostReady: Pass / Caution / Fail

## 13. Calibration Fields
- RuntimeScore:
- KernelScoreRequired: true
- KernelScore: pending
- DeltaScore: pending
- ScoreConfidence: high / medium / low
- UncertaintyRange: ±3 / ±6 / ±10
- MainScoreDrivers:
- MainRiskDrivers:
- Suggested A/B Variable:
- Data Needed For Calibration:
- Render Failure Tags:
- Post-Test Metrics To Collect:

---

# 13. Output Discipline

你必须遵守：

1. 不输出冗长思维链。
2. 不输出 3 个完整候选 Prompt。
3. 不执行复杂 K9 浮点精算。
4. 不把 RuntimeScore 伪装成真实投放预测。
5. 不在信息不足时编造产品事实。
6. 不把销售话术写进视频画面。
7. 不建议用后期修补 NoPost 失败。
8. 不把 Pilot-Supported Heuristics 说成充分验证规则。
9. 所有视频 Prompt 必须英文。
10. 所有投放资产默认中文，除非用户指定目标市场语言。
11. 如果触发 Render Failure 风险，必须改写 Prompt。
12. 如果用户输入低于 MVI，必须阻止完整生成。
````

---

# Part 4：Bridge Layer

---

> **本部分连接 Expert Kernel 和 Runtime Executor。核心组件：DeltaScore 校准协议、Failure Bank、K9 离线计算器、Pilot 测试协议。**

---

## 一、DeltaScore 校准协议

### 1.1 三角验证架构

```
RuntimeScore  ←→  KernelScore  ←→  HumanScore
    │                  │                 │
    └── MeanDelta ─────┘                 │
    └── HumanDelta ─────────────────────┘
```

### 1.2 单条校准

| 字段 | 默认值 | 填写时机 |
|:--|:--|:--|
| RuntimeScore | 由 Runtime 计算 | 每条必填 |
| KernelScore | "pending" | 离线 K9 计算后填写 |
| DeltaScore | "pending" | KernelScore 确认后计算 |

```
DeltaScore = RuntimeScore - KernelScore
```

### 1.3 聚合校准

| 指标 | 最小样本量 | 计算公式 | 触发条件 |
|:--|:--|:--|:--|
| MeanDelta | N ≥ 10 | Σ(RuntimeScore_i - KernelScore_i) / N | \|MeanDelta\| > 5 且方向一致 |
| DeltaStdDev | N ≥ 10 | standard deviation | DeltaStdDev > 8 |
| CategoryDelta | N ≥ 20/category | MeanDelta by category | 某品类显著偏离 |

### 1.4 校准判定

| 判定 | 含义 | 校准动作 |
|:--|:--|:--|
| \|MeanDelta\| ≤ 3 | 近似准确 | 无需校准 |
| MeanDelta > 5 且一致为正 | 系统性高估 | 加自动下修系数 |
| MeanDelta < -5 且一致为负 | 系统性低估 | 检查 GatePenalty 是否过重 |
| DeltaStdDev > 8 | 不稳定 | 重新定义评分维度权重 |
| CategoryDelta 偏离 | 品类特殊 | 建立特殊权重表 |

### 1.5 HumanScore 交叉验证

```
HumanDelta = HumanScore - RuntimeScore
```

| 判定 | 含义 |
|:--|:--|
| HumanDelta > 0 且一致 | LLM 自评偏保守，可信任 |
| HumanDelta < 0 且一致 | LLM 自评偏激进，需下修 |
| HumanDelta ≈ 0 | 一致 |

### 1.6 CalibrationLog 新增字段

| 字段 | 类型 | 说明 |
|:--|:--|:--|
| MeanDelta_Recent | 数值 | 最近 N 条 Runtime-Kernel 平均偏差 |
| DeltaStdDev_Recent | 数值 | 最近 N 条标准差 |
| CategoryDelta_Recent | JSON | 按品类分组的 MeanDelta |
| HumanDelta_Recent | 数值 | 最近 N 条 Human-Runtime 平均偏差 |
| RuntimePromptVersion | 文本 | 当前 Runtime Prompt 版本号 |
| CalibrationAction | 文本 | 本轮校准动作描述 |

---

## 二、Failure Bank

### 2.1 架构

Failure Bank 存储所有历史渲染失败和投放失败案例，供 Runtime Context Ingestion 阶段检索。

**数据来源：**
- E1 Render Test 的 FailureReason
- E2 NoPost Audit 的 Reject/Low 分
- E3 Ad Test 的 AudienceSignal 中的质疑点
- r1 渲染后审计的 HHFailureTags

**数据结构：**
| 字段 | 说明 |
|:--|:--|
| FailureID | 唯一标识 |
| ProductCategory | 品类 |
| FailureType | E1-E15 / PF / NT / AV / IR / SCN / DUR |
| FailureDescription | 失败描述 |
| RootCause | 根因分析 |
| AffectedRule | 关联的 Kernel 规则 |
| PreventionAction | 预防措施 |
| Frequency | 出现频率 |
| SampleCount | 样本数 |
| CreatedDate | 创建日期 |

### 2.2 冷启动阶段

当 Failure Bank 为空时，使用 Synthetic Failure Seed（8 条，见 Runtime Section 2.5）。

种子数据来源：
| 种子 | 来源模块 | 风险等级 |
|:--|:--|:--|
| SF-01 伪文字 | K27 / B3 NT-01/02/03 | High（平面/反光产品） |
| SF-02 LED 环变屏幕 | K26 / B3 PF-03 | Medium |
| SF-03 人脸不稳定 | B3 E3 | Medium |
| SF-04 运镜超调 | K5 / B3 E8 | Low-Medium |
| SF-05 音画漂移 | K25 / B3 AV-01 | Medium-High |
| SF-06 场景漂移 | K4 / B3 SCN-02 | High |
| SF-07 VEL 覆盖功能 | K7 / B3 E13 | Low-Medium |
| SF-08 CTA 表演化 | K13 / B3 E10 | Medium |

### 2.3 种子与 Prompt 生成的关联

| 种子 | 对 Prompt 生成的影响 |
|:--|:--|
| SF-01 | 产品表面必须包含 "no text, no logo, no markings" |
| SF-02 | 智能硬件 LED 必须包含禁止变形项 |
| SF-03 | 中景人物优先特写或剪影 |
| SF-04 | 运镜避免超过 10 秒单一方向推进 |
| SF-05 | 对白 ≤5 词，优先环境音 |
| SF-06 | 场景默认 1 个 |
| SF-07 | VEL 不覆盖产品功能描述 |
| SF-08 | CTA 使用自然选择动作 |

---

## 三、K9 离线计算器

### 3.1 用途

K9 离线计算器用于在 Runtime 输出之后，由人类专家或离线工具执行完整的 K9 StructureScore 精算。它不嵌入 Runtime，不执行在 LLM 单次回复内。

### 3.2 输入

| 输入项 | 来源 | 格式 |
|:--|:--|:--|
| Q1-Q8 分数 | Runtime Scorecard 或人类标注 | 整数 0-5 |
| 品类 | Context Summary | 文本 |
| 亮点项 | 人类判断 | 枚举列表 |
| 风险项 | 人类判断 | 枚举列表 |
| 市场适配 | 人类判断 | 高/中/低 |
| NoPostGate | K18 完整计算或 Runtime NoPost Check | 通过/谨慎通过/不通过 |
| PRC | K11 KVS 判断 | 高/中/低 |
| EAD | K12 情绪弧判断 | 高/中/低 |
| CriticPass | K13 5 项判断 | 0-5 通过数 |
| Naturalness | K14 8 项判断 | 高/中/低 |

### 3.3 计算流程

按 K9 的 8 个 Step 依次执行。最终输出：

```
KernelScore = StructureScore /100
DeltaScore = RuntimeScore - KernelScore
```

### 3.4 最小实现方式

**方式一：Google Sheet**
- 列 A：Q1-Q8 输入（整数）
- 列 B-H：Step 1-8 自动计算
- 列 I：KernelScore 输出
- 列 J：DeltaScore 自动计算

**方式二：Python 脚本**
```python
def k9_structure_score(q1, q2, q3, q4, q5, q6, q7, q8,
                       category, bonus_items, penalty_items,
                       market_fit, nopost_gate, prc, ead, critic_pass):
    # Step 1: Normalize
    q = [q1, q2, q3, q4, q5, q6, q7, q8]
    qi = [x / 5 for x in q]
    
    # Step 2: Domain utilities
    u_creative = (qi[0] * qi[3] * qi[7]) ** (1/3)
    u_product = (qi[1] * qi[2]) ** 0.5
    u_execution = (qi[4] * qi[6]) ** 0.5
    u_delivery = qi[5]
    
    # Step 3: Domain weights (with category adjustment)
    # ... dynamic weight logic per K10 ...
    u_domain = 0.35 * u_creative + 0.25 * u_product + 0.25 * u_execution + 0.15 * u_delivery
    
    # Step 4-8: Gate, Risk, Bonus, Penalty, Final
    # ... per K9 Step 4-8 ...
    
    return clamp(100 * u_domain * g_gate * r_risk * b_bonus - p_penalty, 0, 100)
```

---

## 四、Pilot-Supported 规则升级管理

### 4.1 当前状态表

| 规则 | 编号 | 当前状态 | 渲染样本量 | 通过率 | 升级条件 |
|:--|:--|:--|:--|:--|:--|
| VEL A/B/C/D | K7 | Active-Stable | 长期 | — | 已满足 |
| Camera Path | K5.1 | Active-Pilot | 2 | 100% | ≥30 且 ≥70% |
| Env Light-Material | K7.1 | Active-Pilot | 2 | 100% | ≥30 且 ≥70% |
| State Transition | K7.2 | Active-Pilot | 2 | 100% | ≥30 且 ≥70% |
| Product Interaction | K24 | Active-Pilot | 2 | 100% | ≥30 且 ≥70% |
| AV Sync | K25 | Active-Pilot | 2 | 100% | ≥30 且 ≥70% |
| Product Fidelity | K26 | Active-Pilot | 2 | 100% | ≥30 且 ≥70% |
| NoText/NoLogo | K27 | Active-Pilot | 2 | 50% | ≥30 且 ≥70% |
| Director Intent | K28 | Active-Pilot | 0 | — | ≥30 且 ≥70% |
| Scene Dressing | K29 | Active-Pilot | 0 | — | ≥30 且 ≥70% |
| Character Imperfection | K30 | Active-Pilot | 0 | — | ≥30 且 ≥70% |

### 4.2 升级流程

```
样本量达到 30 条 → Calibration Owner 计算通过率
→ 通过率 ≥ 70%？ → 是 → CalibrationLog 记录 → Active-Stable
                  → 否 → 保持 Active-Pilot → 分析失败模式
```

### 4.3 降级流程

Active-Stable 规则在新一轮 Pilot 中通过率 < 60%：
- Calibration Owner 可降级为 Active-Pilot
- 必须在 CalibrationLog 记录数据依据

---

## 五、首轮测试协议

### 5.1 测试目标

验证 v2.5 Runtime 的四件事：
1. 单次 AI 回复内完成闭环（Token 未截断）
2. 稳定输出 NoPost-Ready Prompt（渲染后验证）
3. RuntimeScore 解释清楚（与人类评分对比）
4. 输出可直接进入 K9 离线计算器和 Failure Bank

### 5.2 测试矩阵

| 编号 | 品类 | 示例产品 | 平台 |
|:--|:--|:--|:--|
| T1 | 美妆 | 精华液 / 口红 / 面膜 | TikTok |
| T2 | 数码 | 智能音箱 / 降噪耳机 / 智能手表 | TikTok |
| T3 | 家居 | 香薰机 / 氛围灯 / 保温杯 | TikTok |

每品类 1 条，共 3 条。

### 5.3 每条记录

| 步骤 | 记录内容 | 工具 |
|:--|:--|:--|
| 1 | v2.5 完整输出（Markdown） | 复制保存 |
| 2 | HappyHorse 1.0 渲染视频 | 渲染平台 |
| 3 | 渲染后人工标注（10 项 r1 审计） | 人工 |
| 4 | 人类独立评分（Q1-Q8） | 人工 |
| 5 | Physics Lock 有/无对比（至少 1 组） | 同 Prompt 对比 |
| 6 | K9 离线计算 | 计算器 |

### 5.4 验证 Checklist

```
□ v2.5 输出是否完整（13 项全部存在）
□ MVI Check 是否正确执行
□ 候选审计表是否使用枚举值
□ Video Prompt 是否为英文
□ Video Prompt 是否包含 Physics Lock
□ Video Prompt 是否包含产品形态锁定
□ Video Prompt 是否包含时长锁
□ Video Prompt 是否包含音频描述
□ RuntimeScore 是否按公式正确计算
□ NoPost Check 是否逐项判断
□ Calibration Fields 是否包含所有字段
□ 渲染视频是否满足 NoPost-Ready
□ Physics Lock 有/无对比是否有差异
□ RuntimeScore vs HumanScore 偏差是否可接受
```

### 5.5 结果处理

| 结果 | 处理 |
|:--|:--|
| 3/3 闭环完成 | 进入扩展测试（+4 产品，累计 7） |
| 2/3 闭环完成 | 分析失败原因，修复后重测 |
| 1/3 或 0/3 | 退回 Runtime Prompt 修改 |

---

# Part 5：Appendix

---

## A1. Anti-Pseudoscience 声明

1. 所有权重均为专家先验，不是训练得到的参数。
2. StructureScore 和 RuntimeScore 不预测 CTR、CVR、ROI、销量或平台分发。
3. UncertaintyRange 不是统计置信区间。
4. Synthetic Failure Seed 是基于文档的保守假设，不是真实统计数据。
5. DeltaScore 聚合校准需要真实渲染和投放数据。
6. Physics Lock 的实际生效取决于 HappyHorse 1.0 引擎的指令解析能力，需渲染对比验证。
7. 所有 Pilot-Supported 规则的实际效果需通过渲染数据验证。
8. VEL 增强词的实际渲染效果取决于引擎精度。
9. 音视频联合生成的音频质量需平台实测数据校准。
10. 只有接入 ≥30 条同品类同市场投放数据并完成回归校准后，才允许讨论预测关系。
11. 有限终止证明保证流程在有限步骤内返回，不保证全局最优。
12. 若 HappyHorse 模型更新，Q7、铁律、PRC 参数需重新校准。
13. R4 六层模型引用的理论用于解释创意结构的传播潜力，不用于预测投放效果。
14. K24-K30 的产品交互响应、音画同步、产品保真等规则的实际效果需通过渲染数据验证。

---

## A2. 落地平台映射

| 字段类型 | Airtable | Notion | 飞书 |
|:--|:--|:--|:--|
| 单行文本 | Single line text | Text | 文本 |
| 长文本 | Long text | Text（多行） | 多行文本 |
| 单选 | Single select | Select | 单选 |
| 数值 | Number | Number | 数字 |
| 日期 | Date | Date | 日期 |
| 关联 | Link to record | Relation | 关联 |
| 公式 | Formula | Formula | 公式 |
| 聚合 | Rollup | Rollup | 聚合 |

---

## A3. 结构化输出 JSON Schema

```json
{
  "version": "HappyHorse CreativeOS v2.5",
  "mvi_check": {
    "status": "pass | fail",
    "missing_fields": [],
    "assumption_tags": [],
    "conservative_assumptions": []
  },
  "context_summary": {
    "product": "",
    "category": "",
    "audience": "",
    "platform": "",
    "core_pain": "",
    "visual_selling_point": "",
    "nopost_requirement": "yes | no",
    "failure_bank_status": "real | synthetic_seed | not_available",
    "key_assumptions": []
  },
  "candidate_audit": [
    {
      "candidate": "A",
      "direction": "Strong Hook",
      "core_hook": "",
      "main_strength": "",
      "main_risk": "",
      "elimination_reason": "HookTooWeak | ProductLate | NoPostRisk | PRCRisk | EmotionFlat | OverProduction | WinOnMerit",
      "decision": "reject | winner"
    },
    {
      "candidate": "B",
      "direction": "Emotional Reversal",
      "core_hook": "",
      "main_strength": "",
      "main_risk": "",
      "elimination_reason": "HookTooWeak | ProductLate | NoPostRisk | PRCRisk | EmotionFlat | OverProduction | WinOnMerit",
      "decision": "reject | winner"
    },
    {
      "candidate": "C",
      "direction": "Product-Driven",
      "core_hook": "",
      "main_strength": "",
      "main_risk": "",
      "elimination_reason": "HookTooWeak | ProductLate | NoPostRisk | PRCRisk | EmotionFlat | OverProduction | WinOnMerit",
      "decision": "reject | winner"
    }
  ],
  "winner_direction": {
    "winner": "",
    "why_this_direction": "",
    "rejected_alternatives": []
  },
  "iteration_summary": {
    "initial_weakness": "",
    "refinement_applied": "",
    "convergence_result": ""
  },
  "final_video_prompt": {
    "prompt_text": "",
    "duration_lock": "The video must stay strictly under 14.5 seconds.",
    "physics_lock": "[System Physics Lock: Maintain strict physical continuity. No morphing, no product shape changes, no text generation, no logo rendering, no fake UI, no subtitles, no price tags, no URLs, no QR codes. Do not create extra screens or labels on the product. Camera motion must be smooth, grounded, and physically plausible. All narrative meaning must be conveyed through visible action, lighting, object interaction, and built-in audio.]"
  },
  "title_matrix": {
    "contrast": "",
    "pov": "",
    "emotional": "",
    "functional": ""
  },
  "hashtag_strategy": {
    "category_tags": [],
    "platform_tags": [],
    "scenario_tags": [],
    "emotion_tags": [],
    "growth_curiosity_tags": []
  },
  "pinned_comments": {
    "emotion_interaction": "",
    "conversion_support": ""
  },
  "bio_product_card": {
    "bio_cta": "",
    "product_card_copy": ""
  },
  "runtime_scorecard": {
    "q1_hook_power": { "score": 0, "reason": "" },
    "q2_product_power": { "score": 0, "reason": "" },
    "q3_sensory_richness": { "score": 0, "reason": "" },
    "q4_spreadability": { "score": 0, "reason": "" },
    "q5_execution_power": { "score": 0, "reason": "" },
    "q6_growth_delivery": { "score": 0, "reason": "" },
    "q7_render_reliability": { "score": 0, "reason": "" },
    "q8_emotional_impact": { "score": 0, "reason": "" },
    "base_score": 0,
    "gate_penalty": 0,
    "risk_penalty": 0,
    "bonus": 0,
    "runtime_score": 0,
    "rating": "Strong Candidate | Good Candidate | Usable Candidate | Weak Candidate | Reject"
  },
  "nopost_check": {
    "video_text_dependency": "pass | fail",
    "logo_dependency": "pass | fail",
    "price_url_qr_dependency": "pass | fail",
    "post_edit_dependency": "pass | fail",
    "subtitle_dependency": "pass | fail",
    "voiceover_dependency": "pass | fail",
    "product_fidelity_lock": "pass | fail",
    "audio_included": "pass | fail",
    "physics_lock_included": "pass | fail",
    "render_failure_risk": "low | medium | high",
    "final_nopost_ready": "pass | caution | fail"
  },
  "calibration_fields": {
    "runtime_score": 0,
    "kernel_score_required": true,
    "kernel_score": "pending",
    "delta_score": "pending",
    "score_confidence": "high | medium | low",
    "uncertainty_range": "±3 | ±6 | ±10",
    "main_score_drivers": [],
    "main_risk_drivers": [],
    "suggested_ab_variable": "",
    "data_needed_for_calibration": [],
    "render_failure_tags": [],
    "post_test_metrics_to_collect": []
  }
}
```

---

## A4. 用户输入模板

```markdown
# HappyHorse v2.5 User Input

## Required Fields（MVI 必填）
- Product Name:
- Product Category:
- Core Selling Point:
- Target Platform:
- Target Audience:
- NoPost Requirement: Yes / No

## Optional Fields（选填）
- Brand Name:
- Brand Voice:
- Product Appearance:
- Material / Shape / Color:
- Usage Scenario:
- Main User Pain:
- Desired Emotion:
- Forbidden Claims:
- Competitor Reference:
- Historical Failure Cases:
- Existing Brand Assets:
- Target Market Language:
- First Frame Image: Yes / No
- Reference Images: Yes / No
- Existing Video: Yes / No
```

---

## A5. 版本历史

| 版本 | 核心变更 |
|:--|:--|
| v1.0 | 完整规范文档 |
| v1.7-Final | 精算编译器 |
| v1.8-Eval | 实验协议 |
| v1.9-Bench | 评测工作台 |
| v2.0 | 创意操作系统：7 模块 + 6 张表 + 4 角色 + Level 0-4 |
| v2.0.1 | 系统规范定稿 |
| v2.1-MVP | 表格落地版：9 张表 + 18 视图 + Pilot 指南 |
| v2.1-MVP-r1 | Smart Hardware Sensory Patch |
| v2.2 | 正式版：六层叙事引擎 + Prompt 工程 + 评分精修 |
| v2.3 | LLM-Native 评估报告：计算幻觉、Token 爆炸、NoPost 滞后 |
| v2.4 | 隐式发散、线性评分、Physics Lock、1M 上下文检索 |
| v2.5 | Master Document 初版：双层架构、MVI、DeltaScore、Failure Bank |
| **v2.5-stable** | **Master Document 稳定版：核心原则措辞精确化 + Part 3 使用警告** |

**版本治理链：**
```
v2.2 (Expert Kernel, Active-Stable)
  ↓ Design Review
v2.3 (评估报告, Advisory)
  ↓ 优化方向
v2.4 (初版 Runtime, Draft)
  ↓ 架构重构
v2.5 (Master Document, Active)
  ↓ 稳定化
v2.5-stable (Master Document, Active-Stable)
```

---

## A6. 一句话定位

```
HappyHorse CreativeOS v2.5-stable
= 一个项目、一个文档、一个系统。
Part 2 Expert Kernel 做审计和校准。
Part 3 Runtime Executor 做单次生成和交付。
Part 4 Bridge Layer 把两者连接起来。
目标：把产品卖点编译成可生成、可评分、可审计、可回测、可归因、可校准、可持续进化的 AI 视频广告系统。
```

---

## A7. 最小产品形态

```text
HappyHorse CreativeOS v2.5-stable Master Pack

一个项目包，三个组件：

1. Master Spec / Expert Kernel
   → 本文档 Part 2
   → 用途：专家审计、离线精算、校准、治理

2. Runtime Prompt
   → 本文档 Part 3（一键复制版代码块）
   → 用途：LLM 单次闭环生成

3. Output Schema + Calibration Tables
   → 本文档 Part 5 A3 JSON Schema
   → 本文档 Part 4 DeltaScore + Failure Bank
   → 用途：结构化输出、数据回流、校准驱动
```

---

## A8. 禁止事项（完整列表）

| # | 禁止事项 |
|:--|:--|
| 1 | 不允许把 RuntimeScore 说成投放效果预测 |
| 2 | 不允许把 Pilot-Supported 规则说成充分验证规则 |
| 3 | 不允许没有数据就修改 RuntimeScore 或 KernelScore 权重 |
| 4 | 不允许单条视频失败就修改 Runtime Prompt 或 Kernel 规则 |
| 5 | 不允许建议通过人工后期修补 Render Failure |
| 6 | 不允许在信息不足时编造产品事实 |
| 7 | 不允许把销售话术写进视频画面 |
| 8 | 不允许忽略失败样本 |
| 9 | 不允许把 RuntimeScore 与 KernelScore 混淆使用 |
| 10 | 不允许在未记录 CalibrationLog 的情况下修改任何规则 |
| 11 | 不允许把两个层级混成同一套运行逻辑 |
| 12 | 不允许无数据升级或降级 Pilot-Supported 规则 |

---

**HappyHorse CreativeOS v2.5-stable Master Document — 完整文档结束。**
