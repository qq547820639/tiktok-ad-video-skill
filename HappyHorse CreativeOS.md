# HappyHorse CreativeOS v2.2

> **理论基础：** HappyHorse 1.0 创作指南 + HappyHorse CreativeOS v2.0.1 系统规范定稿 + v2.1-MVP 表格落地版 + v2.1-MVP-r1 Smart Hardware Sensory Patch + 心理传播学知识框架 v1.1
>
> **声明：** 所有评分为专家先验，不是投放效果预测。只有接入真实生成数据和投放数据并完成校准后，才允许讨论预测关系。

---

## A5.0 版本发布元信息

| 字段 | 值 |
|:--|:--|
| 当前版本 | v2.2 |
| 发布日期 | 2026-05-13 |
| 文档状态 | 正式版（Active） |
| 理论基础版本 | v2.0.1 系统规范定稿 + 心理传播学知识框架 v1.1 |
| 执行层版本 | v2.2 |
| 创作指南版本 | HappyHorse 1.0 创作指南 |
| 升级触发 | 逆向拆解12项盲区 + r1 Pilot v1.1→v1.2验证 + 六层模型系统化 |
| ActionLevel | 3（Kernel 级结构性升级） |
| 维护负责人 | （填写） |
| 下次评审日期 | v2.2 首轮完整 Pilot 完成后 7 日内 |

> **版本追溯规则：**
> 1. 每次 Kernel 级修改（ActionLevel=3）必须在 CalibrationLog 中创建记录，并更新版本号（如 v2.2-r1）。
> 2. 版本号格式：`主版本.次版本`（如 v2.2），修订格式：`v2.2-r1`。
> 3. 版本发布元信息表随每次修订更新。
> 4. 历史版本归档至独立文档或 Git 仓库，确保可追溯。

> **Status 生命周期：**
> Draft → Active-Pilot → Active-Stable → Advisory / Deprecated / Rollback

---

## 目录

### 快速跳转

| 我想... | 阅读 |
|:--|:--|
| 了解系统全貌 | 第一篇 + 第二篇 |
| 编写 Prompt | 第三篇 K1-K6 + K28-K30（四元公式 + 铁律 + 运镜 + 导演意图 + 场景布置 + 角色不完美） |
| 理解六层叙事模型 | 第四篇 R4（L1-L6） |
| 理解评分体系 | 第三篇 K8-K10（Q1-Q8 + StructureScore + 动态权重 + 双轨评分） |
| 植入 VEL | 第三篇 K7 + K7.1 + K7.2 |
| 理解产品交互响应 | 第三篇 K24 |
| 理解音画同步 | 第三篇 K25 |
| 理解产品形态保真 | 第三篇 K26 + K27 |
| 理解选择模式 | 第三篇 K8.1 |
| 检查 NoPost 可行性 | 第三篇 K18 |
| 执行候选修复 | 第四篇 R1.1 |
| 理解提交策略 | 第四篇 R6 |
| 智能硬件专用流程 | 第四篇 R5 |
| 交付 Prompt 和投放资产 | 第五篇（13 项） |
| 审计验算 | 第六篇（15-Step Verification） |
| 评测回测 | 第七篇（E1-E4） |
| 校准与迭代 | 第八篇（B5-B7） |
| 建数据库表 | 第九篇 O1 |
| 建视图和看板 | 第九篇 O2 |
| 执行 Pilot | 第十篇 + 第十一篇 |
| 查看版本历史 | 第十二篇 A5 |

### 文档结构

| 篇章 | 内容 | 核心编号 |
|:--|:--|:--|
| 第一篇 | 系统定位与核心能力 | HappyHorse 1.0 创作指南 |
| 第二篇 | 系统架构（七层） | v2.2 架构总览 |
| 第三篇 | Kernel（精算内核） | K1-K30 |
| 第四篇 | Runtime（执行器） | R1-R6 |
| 第五篇 | Delivery（交付界面） | 输出模板 13 项 |
| 第六篇 | Audit（审计模式） | 15-Step Verification |
| 第七篇 | Evaluation（评测协议） | E1-E4 |
| 第八篇 | Benchmark（评测工作台） | B1-B7 |
| 第九篇 | Operations（运营系统） | O1-O7 + 18 视图 |
| 第十篇 | Pilot 执行指南 | 时间线 + 参数 |
| 第十一篇 | 执行 Checklist | P-01 至 P-29 |
| 第十二篇 | 附录 | A1-A8 |

---

# 第一篇：系统定位与核心能力

---

### 一、系统定位

```
HappyHorse CreativeOS v2.2
= 创意编译器（Creative Compiler）
+ 情绪叙事引擎（Emotional Narrative Engine）
+ Prompt 工程器（Prompt Engineer）
+ 渲染评测器（Render Bench）
+ 标注系统（Annotation Console）
+ 投放追踪器（Ad Test Tracker）
+ 校准引擎（Calibration Engine）
+ 版本治理器（Version Governance）
+ 决策看板（Decision Dashboard）
```

**一句话定位：**
把产品卖点编译成可生成、可评分、可审计、可回测、可归因、可校准、可持续进化的 AI 视频广告系统。

---

### 二、HappyHorse 1.0 模型能力

#### 2.1 核心功能

| 功能 | 说明 |
|:--|:--|
| **文生视频 T2V** | 通过文本描述生成视频，适用于从零构思创意、快速验证想法 |
| **首帧图生视频 I2V** | 以一张静态图片作为视频第一帧，精确还原后生成动态视频 |
| **多图参考生视频 R2V** | 输入 1-9 张参考图引导生成，在角色一致性、场景连贯性、风格统一性上精准控制 |
| **视频编辑 V2V** | 对已有视频智能编辑，支持上传参考图或文字描述修改意图 |
| **音视频联合生成** | 环境音、音效、对白、背景音乐一体化生成 |

#### 2.2 核心亮点

| 核心亮点 | 评分映射 |
|:--|:--|
| 电影级画面质感与光影表现 | Q3 感官丰富度 + C 类材质光影 VEL + K7.1 环境光材质交互 |
| 流畅稳定的运镜与转场能力 | Q5 执行力 + K5 运镜指令体系 + K5.1 运镜路径 |
| 人物真实感强，面部表情有生命力 | Q8 情绪冲击力 + B 类角色生命 VEL + K7.2 状态过渡 |
| 中近景叙事能力突出 | Q1 Hook力 + Q4 传播力 + K28 导演意图层 |
| 音视频联合生成 | AudioMatchScore / AudioApplicable / K25 音画同步 |
| 灵活多样的创作体验 | 多模式路由适配 + R5 智能硬件流程 + R6 提交策略 |

#### 2.3 HappyHorse 已知限制

| 限制 | 应对策略 |
|:--|:--|
| 不擅长精确色彩控制 | 避免使用"画面变成黑白"等强色彩控制表达 |
| 不擅长精确时序控制 | 避免使用"时间倒流"等复杂时间表达；使用相对时序（"随后""当……时"） |
| 不支持稳定分屏效果 | 避免使用"分屏"等画面结构要求 |
| 可能生成伪文字/伪Logo | K27 NoText/NoLogo 渲染审计 + 产品表面锁定前置 |
| 产品形态可能漂移 | K26 Product Fidelity Gate + forbidden transformations |

#### 2.4 优势场景

| 场景 | 典型能力 |
|:--|:--|
| **影视短剧制作** | 情感表演细节丰富、光影跨场景稳定复现、角色一致性维持、面部质感真实 |
| **电商广告（含数字人口播）** | 产品展示清晰度高、数字人口播自然真实、指令遵循度高、支持批量素材生产 |
| **社媒创意视频** | 画面质感高、运镜转场流畅、多风格适配、图生视频还原度高 |
| **智能硬件产品视频** | 产品交互响应渲染、LED/光效材质扩散、触碰→反馈因果链 |

#### 2.5 首帧图生视频 vs 多图参考生视频

| 维度 | 首帧图生视频 | 多图参考生视频 |
|:--|:--|:--|
| 图片作用 | 图片 = 视频第一帧画面，精确还原 | 图片 = 视觉参考素材，提取特征后融入视频 |
| 图片数量 | 仅 1 张 | 1-9 张 |
| 图像还原度 | 极高，第一帧几乎与原图一致 | 主体参考：借鉴身份特征但不逐像素复制；关键帧参考：近像素级高保真还原 |
| 画幅比例 | 跟随原图 | 可自由选择 |
| 分辨率 | 720P、1080P | 720P、1080P |
| 文本提示词 | 可选项 | 必选项 |

#### 2.6 平台输入输出规格汇总

| 模式 | 输入 | 输出 |
|:--|:--|:--|
| **文生视频** | 自然语言（≤2500汉字/≤5000英文字符），必填 | 分辨率720P/1080P，画幅16:9/9:16/3:4/4:3/1:1，时长3-15秒，自带音效/语音 |
| **首帧生视频** | 1张首帧图 + 自然语言（可选） | 分辨率720P/1080P，画幅与首帧图一致，时长3-15秒 |
| **参考图生视频** | 1-9张参考图 + 自然语言（必填） | 分辨率720P/1080P，画幅可选，时长3-15秒 |
| **视频编辑** | 1个视频 + 1-4张参考图 + 自然语言 | 分辨率720P/1080P，画幅与输入视频一致，时长3-15秒 |

---

# 第二篇：系统架构（七层）

---

```
┌─────────────────────────────────────────────────────────────────────┐
│                    HappyHorse CreativeOS v2.2                        │
├─────────────────────────────────────────────────────────────────────┤
│  Layer 1: Kernel（精算内核）                                          │
│    规则 / 评分 / 门控 / 风险 / 奖励 / 惩罚 / 修复 / 回滚               │
│    + 情绪叙事引擎 / Prompt 工程规则 / 产品交互响应 / 音画同步            │
├─────────────────────────────────────────────────────────────────────┤
│  Layer 2: Runtime（执行器）                                           │
│    输入理解 / 模式路由 / 候选生成 / 评分 / 修复 / 收敛                   │
│    + 叙事引擎检查 / 智能硬件流程 / 提交策略                              │
├─────────────────────────────────────────────────────────────────────┤
│  Layer 3: Delivery（交付界面）                                        │
│    Prompt / 标题 / 标签 / 评论 / Bio / 评分卡 / 风险声明               │
│    + L1-L6检查表 / 节点复用 / 平台适配 / 双轨评分                        │
├─────────────────────────────────────────────────────────────────────┤
│  Layer 4: Audit（审计模式）                                           │
│    15-Step Verification / 子特征 / KVS / EAD / CF/HU                  │
│    + 产品保真 / 伪文字 / 音画同步 / 光效材质 / 场景漂移 / 面部自然度       │
├─────────────────────────────────────────────────────────────────────┤
│  Layer 5: Evaluation（评测协议）                                      │
│    Render Test / NoPost Audit / Small Batch Ad Test                  │
├─────────────────────────────────────────────────────────────────────┤
│  Layer 6: Benchmark（评测工作台）                                      │
│    Test Set / Annotation Rubric / Error Taxonomy / Calibration       │
│    + Pilot Baseline Data                                             │
├─────────────────────────────────────────────────────────────────────┤
│  Layer 7: Operations（运营系统）                                       │
│    Database / Dashboard / Version Governance / Team Roles             │
└─────────────────────────────────────────────────────────────────────┘
```

---

# 第三篇：Layer 1 — Kernel（精算内核）

---

### K1. HappyHorse 能力边界

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

### K2. 四元提示词公式

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
| V2V | 由原视频提供 | 由原视频提供 | 编辑意图（改什么+保留什么） | 必填（描述音频变化或保留） |

**V2V 四元公式简化为：**

```
Prompt = 保留内容 + 修改内容 + 运动变化 + 音频变化 + 禁止误改项
```

---

### K3. 模式路由

| 输入条件 | 模式 | 提示词要求 |
|:--|:--|:--|
| 无图片、无视频 | T2V 文生视频 | 场景+主体+运动+音频（全部必填） |
| 有 1 张图片 | I2V 首帧图生视频 | 运动+音频（场景/主体由图片提供） |
| 有多张图片 | R2V 多图参考生视频 | 场景+主体+运动+音频+@图片指代 |
| 有视频 | V2V 视频编辑 | 编辑意图（改什么+保留什么+禁止误改什么） |

**I2V 核心原则：** 重点描述"动起来之后发生什么"，无需重复描述图片中已有的静态内容。

**R2V 指代规则：** 在提示词中通过 @图片1、@图片2 等方式准确指代素材。图片按顺序上传，顺序有意义。

**V2V 核心原则：** 明确指出"改什么"和"保留什么"。禁止误改项用于明确告知模型哪些内容不应被修改。

---

### K4. 硬性铁律（15 条）

1. 视频 ≤15 秒。
2. 角色 ≤3 个。
3. 场景 ≤3 个。
4. 中文 Prompt ≤2500 汉字，英文 Prompt ≤5000 字符。
5. 视频内文字最多 3 个短词。
6. 不在视频画面中依赖价格、URL、优惠码、长字幕、精准 Logo。
7. 不使用"突然""突然间"。
8. 不使用"她意识到""他觉得""她明白了"等内心独白。
9. 不使用"时间倒流""分屏""画面变成黑白"等动态控制否定。静态条件否定（如"房间没有开灯"）合法。
10. 不使用"镜头拉远看到全景"这类笼统表达。
11. 所有冲突、选择、情绪必须通过可见画面表达。
12. CTA 必须通过画面动作表达。
13. 必须包含音频描述。
14. 不把投放标题、标签、评论里的销售语言写进视频画面。
15. 如果强销售表达与可生成性冲突，销售表达放入标题、置顶评论、Bio 或商品卡。

**禁止项适用范围：** 铁律 #6-#14 仅适用于【叙事】段和视频内可见内容。不适用于投放标题、标签、置顶评论、Bio CTA、商品卡。

**否定描述区分（v2.2 新增）：**
- **动态控制否定（禁止）：** "画面变成黑白""时间倒流""突然消失"——模型无法稳定执行的动态状态切换。
- **静态条件否定（合法）：** "房间没有开灯""桌上没有食物""背景没有人"——建立场景初始条件的描述。

---

### K5. 运镜规则

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

### K5.1 Camera Path Framework（运镜路径框架）

**v2.1-MVP-r1 新增。**

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

**与 K5 运镜词表的关系：**
K5 定义"可用运镜类型"，K5.1 定义"运镜必须包含空间路径"。两者同时生效。

---

### K6. ShowDontTell 预检

评分前必须检查：
1. 是否存在抽象心理描写。
2. 是否存在不可见的情绪说明。
3. 是否存在否定空间关系（"不在X""远离X"）。
4. 是否存在过度抽象的形状描述（"形状像X"）。
5. 是否存在必须靠字幕才能理解的剧情转折。
6. 是否存在必须靠后期配音才能成立的情绪冲突。

**修复原则：** 心理变动作 → 抽象变画面 → 解释变物理行为 → 销售语言移到投放资产中。

---

### K7. VEL 视觉增强层

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

### K7.1 Environmental Light-Material Interaction（环境光-材质交互）

**v2.1-MVP-r1 新增。**

当场景中存在灯光、屏幕光、霓虹、LED、火光、窗外光时，允许新增一类环境光-材质交互描述：

```
标准格式：
[Light source] passes through / spills across / ripples over
[material surface], creating [reflection / glow / shadow / color wash].
```

**与现有 VEL 类型的关系：**

| VEL 类型 | 关注对象 | 示例 |
|:--|:--|:--|
| A 类（物理真实） | 悬浮/碎裂/流体 | 不涉及光 |
| B 类（角色生命） | 面部/手部/呼吸 | 不涉及光 |
| C 类（材质光影） | 产品表面的光 | "暖光汇聚在产品表面" |
| D 类（大气粒子） | 灰尘/薄雾/余烬 | 粒子本身 |
| **K7.1（环境光材质交互）** | **光在环境材质上的行为** | **"蓝琥珀光涟漪般扩散到纸板箱表面和白墙上"** |

C 类关注产品，K7.1 关注环境。

**示例：**
- ✓ "Blue and amber light ripples across nearby cardboard surfaces and the white wall behind."
- ✓ "Faint city lights glow diffusely through wet glass, casting soft color reflections across the hardwood floor."

每条 Prompt 最多 1 个 K7.1 增强词。不计入 K7 的 3-4 个 VEL 总量限制。

---

### K7.2 State Anchor → State Transition（状态锚点 → 状态过渡）

**v2.1-MVP-r1 新增。**

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
- ✓ "Her posture is still, weight resting back against the wall." → "Her shoulders drop." → "Her fingers gradually uncurl — knuckles softening, palms flattening."
- ✓ "His jaw is clenched, knuckles white on the steering wheel." → "His grip loosens." → "He rests his forehead on the steering wheel."

**反例：**
- ✗ "She feels relieved."（心理描写）
- ✗ "She becomes calm."（结果，无过渡）
- ✗ "She realizes the speaker comforts her."（内心独白）

**与 VEL B 类的关系：**
VEL B 类是"单帧增强"（一个瞬间的细节），K7.2 是"状态过渡框架"（跨数秒的连续变化）。K7.2 优先级高于 VEL B 类——当两者冲突时，先满足 K7.2 的三步结构，再在其中嵌入 VEL B 类增强词。

---

### K8. Q1-Q8 子特征逐项计分

每个 Q 维度由 5 个子特征组成。每个子特征满足则 1 分，不满足则 0 分。每个 Q 满分 5 分。

#### Q1 HookPower（0-5）

1. 前 0.5 秒有声音事件。
2. 前 0.5 秒有视觉冲突。
3. 前 1 秒有明确动作动词。
4. 前 1 秒有产品或产品外观暗示。
5. 前 1 秒有情绪触发。

#### Q2 ProductPower（0-5）

1. 产品在前 1/3 出现。
2. 产品推动剧情转折。
3. 有材质、结构或外观细节。
4. 有使用场景或使用结果。
5. 角色对产品做出主动选择。

**CharacterChoice 判定：** 角色主动决定"用/不用/给/不给/丢/不丢"，且该决定改变了产品在故事中的角色。
- ✅ "举到嘴边停住让出水" — 产品从"她的水"变成"她的牺牲"
- ❌ "过滤泥水喝了" — 产品按设计使用，角色无选择

#### Q3 SensoryRichness（0-5）

1. 有环境音或动作音。
2. 有材质、触觉或温度描述。
3. 有光线、色彩或阴影描述。
4. 有手部交互或身体接触。
5. 有微距、特写或细节镜头。

**v2.2 质量标注（审计模式下额外标注）：**

| 子特征 | 基本（1） | 强（1+） |
|:--|:--|:--|
| Q3#1 音频 | 有环境音或动作音 | 有音频层级（基底层+结构层+同步事件+微声） |
| Q3#3 光线 | 有光线描述 | 有多层光学结构（光源+传播介质+材质反射+色彩对比） |
| Q3#4 手部交互 | 有手部交互 | 有状态过渡（K7.2 锚点→过渡→终点） |

"强"标注不改变 Q3 总分（仍为 0-5），但用于内部品质追踪和校准。

#### Q4 Spreadability（0-5）

1. 有可截图画面。
2. 有反转、争议或彩蛋。
3. 有首尾呼应。
4. 有情绪弧线，不能是单一情绪。
5. 有复播点，观众会回看确认细节。

#### Q5 ExecutionPower（0-5）

1. 角色 ≤3。
2. 场景 ≤3。
3. 动作精确可执行（"她举起" ✅ / "她战斗" ❌）。
4. 光线、天气、空间简单明确。
5. 不依赖人工后期修复。

#### Q6 GrowthDelivery（0-5）

**v2.2 双轨评分永久化：**

**口径 A：PromptScore（Prompt 裸分，最高 3/5）**
- 评分对象：仅 Prompt 正文
- 可评子特征：#2 互动引导 + #3 复播/分享动机
- #1（CTA路径）/ #4（标签策略）/ #5（承接点）不在 Prompt 中，不评分

**口径 B：PackageScore（完整投放包分，最高 5/5）**
- 评分对象：Prompt + 标题×4 + 标签 + 评论 + Bio + 商品卡
- 5 个子特征全部可评

| 子特征 | 标准 | 口径 A | 口径 B |
|:--|:--|:--|:--|
| #1 有清晰 CTA 路径 | 至少有反差/POV/情绪/功能四类 | 不评 | 1/0 |
| #2 有互动引导或评论诱因 | 能补足卖点、互动或 CTA | 1/0 | 1/0 |
| #3 有复播或分享动机 | 能承接转化 | 1/0 | 1/0 |
| #4 有标签、话题或平台分发策略 | 12-16 个，覆盖品类/平台/场景/增长 | 不评 | 1/0 |
| #5 有投放承接点 | 包括标题、评论、Bio、商品卡或落地页 | 不评 | 1/0 |

**输出规则：**
- 交付版（Delivery 模式）：输出 PackageScore
- 审计版（Audit 模式）：同时输出 PromptScore 和 PackageScore
- 单独 Prompt 评审：只输出 PromptScore

品牌曝光类内容不能因缺少直接转化而给低分。

#### Q7 HappyHorseReliability（0-5）

1. 主体数量少且清晰。
2. 无精准文字、价格、URL、二维码强依赖。
3. 动作链不超过 3 个核心步骤。
4. 光线和空间清晰。
5. 产品展示自然不突兀。

**HappyHorse 特有评估：**
- 运镜指令遵循度（高置信）
- 面部真实感（高置信）
- 音频生成质量（中置信，需实测）

#### Q8 EmotionalImpact（0-5）

<details>
<summary>点击展开：Q8 五项子特征详细判定（含正例/反例）</summary>

**Q8#1 Hook 情绪冲击：**
前 0.5 秒必须出现足以中断用户滑动的强触发事件。

满足方式：物理法则违反 / 反常识运动 / 极端情境 / 强关系张力 / 危险、失去、惊喜、温暖等强情绪触发。

正例：
- 水从嘴唇前倒流退开。
- 箱子从空中砸落但没有来源。
- 她把水杯举到嘴边，却停住递给身后更虚弱的人。
- 婴儿哭声响起，屋内所有灯同时熄灭。
- 一只手把产品放在桌上，桌面灰尘自动向外散开。

反例：
- 手电筒熄灭。
- 女主看起来很难过。
- 产品在灯光下很好看。
- 一个人慢慢走进房间。
- 背景音乐变紧张。

**Q8#2 有效情绪段 ≥3：**
15 秒内至少出现 3 个有效情绪段。

有效情绪类型枚举：震惊 / 恐惧 / 好奇 / 希望 / 温暖 / 心碎 / 满足 / 不安 / 释然 / 平静

有效示例：好奇→紧张→释放 / 冷漠→惊讶→认同 / 期待→失落→反转 / 恐惧→希望→温暖 / 不安→选择→释然

无效示例：恐惧→不安→紧张（三者过于接近）/ 开心→更开心→微笑（方向单一）

**Q8#3 角色选择：**
角色必须做出"本可以做别的，但选择了这个"的可见动作选择。

正例：
- 她本可以自己喝水，但停住，把水递给别人。
- 他本可以关掉设备，但选择把它推到镜头前。
- 她本可以离开，却转身按下按钮。
- 她伸手触碰音箱，光回应了她，她选择收回手，让光自己存在。

反例：
- 她拿起杯子喝水。
- 他打开产品使用。
- 她看了一眼产品。
- 他跟着人群跑。

只有"唯一合理动作"的行为不算角色选择。必须存在替代可能性。

**Q8#4 结尾反预期 / 反预期静止：**
最后 1-2 秒必须出现观众不预期的行为、无法立即解释的画面元素、反转动作、强记忆落点，**或**反预期静止。

**反预期动作（原有）：**

正例：
- 她没有喝水，而是把水放回空杯旁。
- 盒盖自己掀开。
- 影子已经离开，但人还站着没动。

反例：
- 画面静止。
- 她微笑看向镜头。
- 产品停在桌面上。

**反预期静止（v2.2 新增）：**
观众预期一个结局动作（拥抱、告别、回头），但只得到一个安静的画面。静止本身成为反预期。

正例：
- "Hold on the speaker glowing warm gold. The woman's relaxed silhouette remains visible, still and at ease." → 预期：她站起来做点什么。实际：什么都没发生。
- "The mother holds the mug against her own cheek, eyes closed. The daughter watches for one breath. Then turns and walks through the door." → 预期：拥抱。实际：安静离开。

反例：
- 画面静止且无情绪锚点。
- 产品停在桌面上，无叙事意义。
- 风声消失。

**Q8#5 情绪弧非单调：**
前 1/3 和后 1/3 的主导情绪必须不同。

正例：恐惧→好奇→温暖 / 冷漠→震惊→认同 / 平静→紧张→释然 / 期待→失落→反转

反例：恐惧→不安→恐惧 / 开心→兴奋→满足 / 平静→安静→放松

</details>

**Q8 分级规则：**
- Q8=5：五项全部满足。
- Q8=4：至少满足四项，且必须包含 Q8#1 或 Q8#3。
- Q8=3：有基本情绪弧，但冲击力一般。
- Q8=2：情绪存在但弱，像普通产品片。
- Q8≤1：情绪几乎不存在或完全靠解释。

---

### K8.1 Choice Pattern Library（选择模式目录）

**v2.1-MVP-r1 新增。**

Q8#3 "角色选择"不只判定有/无，还需标注选择模式。

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

当 Q8#3 满足时，必须在评分卡中标注使用了哪种选择模式。
当 Q8#3 不满足时，建议参考此目录增加选择动作。

---

### K9. StructureScore 精算链

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
U_domain = 0.35 × U_creative
         + 0.25 × U_product
         + 0.25 × U_execution
         + 0.15 × U_delivery
```

**Step 4：门控乘数 G_gate**

```
G_hook:
  Q1 ≥4 → 1.00 / Q1 =3 → 0.85 / Q1 ≤2 → 0.65

G_product:
  Q2 ≥4 → 1.00 / Q2 =3 → 0.85 / Q2 ≤2 → 0.65

G_reliability:
  Q7 ≥4 → 1.00 / Q7 =3 → 0.85 / Q7 ≤2 → 0.70

G_market:
  市场主流适配 → 1.00 / 市场轻微争议或文化不确定 → 0.85 / 市场明显敏感或不适配 → 0.65

G_nopost:
  NoPost 通过 → 1.00 / NoPost 谨慎通过 → 0.90 / NoPost 不通过 → 0.70
  用户强要求无后期且 NoPost 不通过 → 0.50

G_gate = G_hook × G_product × G_reliability × G_market × G_nopost
```

**Step 5：风险折扣 R_risk**

```
RiskLoad 根据以下风险判断：
  精准文字风险 / 复杂物理风险 / 后期依赖风险
  多主体风险 / 多场景风险 / 长对白同步风险
  品牌/价格/URL 依赖风险

RiskLoad 低   → R_risk = 1.00
RiskLoad 中低 → R_risk = 0.95
RiskLoad 中   → R_risk = 0.90
RiskLoad 中高 → R_risk = 0.85
RiskLoad 高   → R_risk = 0.78
```

**Step 6：饱和奖励 B_bonus**

亮点项：
- 产品是剧情转折条件：+2
- 产品早出现：+1
- 有强截图点：+1
- 有复播彩蛋：+1
- 有自然手部交互：+1
- CTA 清晰：+1
- 投放资产完整：+1
- 品牌露出自然：+1

```
0 分 → 1.00 / 1 分 → 1.02 / 2 分 → 1.035 / 3 分 → 1.048 / 4 分及以上 → 1.06
```

**Step 7：线性惩罚 P_penalty**

P_penalty 各分项为非负惩罚值：

```
广告腔明显：2 / 感官词堆砌：3 / 过度解释：2 / CTA 生硬：2
低自然度：3 / 违反 ShowDontTell 但未修复：5 / 音频与画面不匹配：3
市场文化风险未处理：3 / 运镜规则被破坏：3 / CriticPass ≤2：3
```

**Step 8：最终公式**

```
StructureScore = clamp(
  100 × U_domain × G_gate × R_risk × B_bonus − P_penalty,
  0, 100
)

外部输出时称为 CreativeScore。
```

**v2.2 双轨输出：**
- PromptScore：Q6 使用口径 A（裸分），Q6 最高 3/5
- PackageScore：Q6 使用口径 B（完整包分），Q6 最高 5/5

<details>
<summary>点击展开：StructureScore 完整计算示例</summary>

假设某条 Prompt 各维度评分如下：

| 维度 | 分数 | 标准化 |
|:--|:--|:--|
| Q1 HookPower | 4 | q1 = 0.80 |
| Q2 ProductPower | 3 | q2 = 0.60 |
| Q3 SensoryRichness | 4 | q3 = 0.80 |
| Q4 Spreadability | 3 | q4 = 0.60 |
| Q5 ExecutionPower | 4 | q5 = 0.80 |
| Q6 GrowthDelivery | 3 | q6 = 0.60 |
| Q7 HappyHorseReliability | 4 | q7 = 0.80 |
| Q8 EmotionalImpact | 4 | q8 = 0.80 |

**Step 2：四域效用**

```
U_creative  = (0.80 × 0.60 × 0.80) ^ (1/3) = (0.384) ^ 0.333 = 0.727
U_product   = sqrt(0.60 × 0.80) = sqrt(0.48) = 0.693
U_execution = sqrt(0.80 × 0.80) = sqrt(0.64) = 0.800
U_delivery  = 0.60
```

**Step 3：四域效用加权**

```
U_domain = 0.35 × 0.727 + 0.25 × 0.693 + 0.25 × 0.800 + 0.15 × 0.600
         = 0.254 + 0.173 + 0.200 + 0.090
         = 0.717
```

**Step 4：门控乘数**

```
G_hook       = 1.00 (Q1=4)
G_product    = 0.85 (Q2=3)
G_reliability = 1.00 (Q7=4)
G_market     = 1.00 (市场主流适配)
G_nopost     = 1.00 (NoPost 通过)

G_gate = 1.00 × 0.85 × 1.00 × 1.00 × 1.00 = 0.85
```

**Step 5：风险折扣**

```
RiskLoad = 中低（有 1 个短对白同步要求）
R_risk = 0.95
```

**Step 6：饱和奖励**

```
亮点项：产品早出现(+1)、有自然手部交互(+1)、CTA 清晰(+1) = 3 项
B_bonus = 1.048
```

**Step 7：线性惩罚**

```
P_penalty = 0（无触发项）
```

**Step 8：最终分数**

```
StructureScore = clamp(100 × 0.717 × 0.85 × 0.95 × 1.048 − 0, 0, 100)
               = clamp(100 × 0.605, 0, 100)
               = 60.5 → 四舍五入为 61

CreativeScore = 61/100
```

</details>

---

### K10. 动态权重

默认使用四域权重：Creative 0.35 / Product 0.25 / Execution 0.25 / Delivery 0.15

根据品类调整（调整幅度不超过 ±0.05）：

| 品类 | Creative | Product | Execution | Delivery |
|:--|:--|:--|:--|:--|
| 美妆/穿搭/食品 | +0.03 | +0.02 | -0.02 | -0.03 |
| 数码/工具/软件/设备 | -0.03 | +0.04 | +0.03 | -0.04 |
| 家居/生活方式 | +0.02 | +0.02 | 0 | -0.04 |
| 高客单价产品 | -0.05 | +0.03 | +0.01 | +0.01 |
| 低客单价冲动消费 | +0.05 | -0.02 | -0.05 | +0.02 |

调整后四域权重总和必须重新归一化为 1.00。动态权重只在内部使用，外部默认不展开。

---

### K11. PRC 渲染置信度

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

KVS 每项按 高 / 中 / 低 标注。

**PRC 判定：**
- **PRC 高：** KVS 8 项中低置信项 ≤ 1，主体 ≤2，场景 ≤2，动作清晰，光线明确，无精准文字，无复杂物理，无复杂群像，无长对白强同步要求。
- **PRC 中：** KVS 8 项中低置信项 = 2，有 3 个主体或 3 个场景，有轻微复杂运镜，有少量对白，有轻微物理异常，仍可生成但需检查。
- **PRC 低：** KVS 8 项中低置信项 ≥ 3，多角色群像，多场景快速切换，精准文字要求，复杂时间控制，强口型同步，过多物理异常，过度依赖模型精确执行。

**PRC 判定保守优先级：** 若描述性风险条件与 KVS 低置信项数量冲突，采用更保守等级。

外部输出：PRC：高 / 中 / 低 + 一句原因。

---

### K12. EAD 情绪弧密度

- **EAD 高：** 15 秒内有清晰情绪变化，并且没有长时间平铺。
- **EAD 中：** 有情绪变化，但中段略平。
- **EAD 低：** 情绪单一，缺少升级、转折或余韵。

**LongFlatPenalty：**
- 如果存在 6 秒以上连续同一情绪，EAD 下调一级。
- 如果存在 8 秒以上连续同一情绪，必须触发修复。

外部输出：EAD：高 / 中 / 低 + 一句话情绪时间线。

---

### K13. CriticPass（5 项）

1. 叙事有转折（不是线性描述）。
2. 产品融入剧情（不是生硬植入）。
3. 有情绪弧线（不是单一情绪）。
4. 有复播动机（观众会回看）。
5. 有传播钩子（观众会分享/评论）。

每项通过记 ✓，未通过记 ✗。若通过项 ≤2：触发低自然度风险，P_penalty 至少 3，必须尝试修复一次。

---

### K14. NaturalnessCheck（8 项）

1. 是否感官词堆砌。
2. 是否广告腔明显。
3. 是否过度解释。
4. 是否 VEL 堆叠。
5. 是否 VEL 与运镜冲突。
6. 是否音频与画面不匹配。
7. 是否 CTA 生硬。
8. 是否剧情像说明书而不是画面。

外部只输出：自然度：高 / 中 / 低 + 一句原因。

---

### K15. A1-A7 辅助指标 & C1-C4 创意指标

**A1-A7（内部记录，审计模式展开）：**
- A1 产品出场自然度
- A2 品牌露出自然度
- A3 CTA 清晰度
- A4 标题吸引力
- A5 标签覆盖度
- A6 评论引导力
- A7 音频描述质量

**C1-C4（内部记录，审计模式展开）：**
- C1 Hook 独特性
- C2 视觉爆点
- C3 结尾反转
- C4 系列潜力

---

### K16. CF 与 HU

**CF = 评分置信度：**
- CF 高：输入完整、品类明确、卖点清楚、生成风险低、自然度高。
- CF 中：部分信息缺失，但自动假设合理。
- CF 低：产品、受众、卖点或使用场景严重缺失。

**HU = 启发式不确定性：**
- HU 低：±3 分 / HU 中：±6 分 / HU 高：±10 分

外部输出：评分置信度：高 / 中 / 低 + 可能浮动：±x 分。

---

### K17. SC 系列连贯性

只有当用户输入出现以下信号时激活：系列 / 连载 / EP / Episode / 第几集 / campaign / 多条视频 / 连续投放。

**SC 五项评估维度：**
1. 角色一致性（CharacterConsistency）
2. 世界观一致性（WorldConsistency）
3. 视觉风格一致性（VisualStyleConsistency）
4. CTA 节奏一致性（CTAConsistency）
5. 与前后集的情绪衔接（EmotionContinuity）

每项评分 0-5。SCScore = 五项平均值，范围 0-5。

非系列内容不输出 SC。

---

### K18. NoPostGate

#### NoPostRiskLoad

使用 0-10 量表，每项 0-10 分，越高风险越大。

| 编号 | 风险项 | 权重 | 0 分 | 5 分 | 10 分 |
|:--|:--|:--|:--|:--|:--|
| N1 | 视频内文字依赖 | 0.20 | 无文字依赖 | 有文字但不影响理解 | 必须靠文字理解 |
| N2 | 精准品牌/Logo 依赖 | 0.15 | 不依赖精准 Logo | 需要模糊品牌识别 | 必须精准 Logo 才成立 |
| N3 | 价格/优惠/URL 依赖 | 0.10 | 无价格/URL 依赖 | 销售信息可放到评论/Bio | 视频内必须出现价格/URL |
| N4 | 后期剪辑依赖 | 0.15 | 单条生成即可成立 | 轻微后期更好 | 必须后期剪辑才成立 |
| N5 | 后期配音/字幕依赖 | 0.10 | 音频已写入 Prompt | 平台字幕增强更好 | 必须后期配音或字幕 |
| N6 | 精准口型/对白同步依赖 | 0.10 | 无强同步 | 有短对白 | 必须精准口型同步 |
| N7 | 复杂视觉执行依赖 | 0.10 | 简单稳定 | 有轻微复杂物理或运镜 | 多主体、多场景、复杂物理 |
| N8 | CTA 后期依赖 | 0.10 | CTA 可由动作完成 | CTA 需要标题/评论补足 | CTA 必须靠后期贴片 |

```
NoPostRiskLoad = (0.20×N1 + 0.15×N2 + 0.10×N3 + 0.15×N4
               + 0.10×N5 + 0.10×N6 + 0.10×N7 + 0.10×N8) / 10
```

#### BaseNoPostGate 查表

```
0.00 → 1.00    0.50 → 0.69    1.00 → 0.47
0.10 → 0.93    0.60 → 0.64
0.20 → 0.86    0.70 → 0.59
0.30 → 0.80    0.80 → 0.55
0.40 → 0.74    0.90 → 0.51
```

#### Cap Rules（18 条）

FinalNoPostGate 必须受以下上限规则限制：

1. 视频内需要清晰品牌名 → ≤ 0.85
2. 视频内需要清晰 Logo → ≤ 0.75
3. 视频内需要准确价格 → ≤ 0.70
4. 视频内需要准确 URL / 优惠码 / 二维码 → ≤ 0.50
5. CTA 只能靠后期贴片完成 → ≤ 0.50
6. Prompt 出现 post-production → ≤ 0.60 且 NoPostReady = false
7. 黑底卡文字必须由模型生成 → ≤ 0.75
8. 品牌识别只依赖包装文字或 Logo → ≤ 0.75
9. 产品功能违反常识或不可验证 → ≤ 0.50
10. 涉及监管敏感声明 → ≤ 0.50
11. 核心叙事转折依赖后期音频设计 → ≤ 0.80
12. 对白或口播内容需要精确匹配脚本 → ≤ 0.75
13. 音频需要特定音色、语速或情感 → ≤ 0.70
14. Prompt 中没有音频描述 → ≤ 0.80，并触发修复
15. 视频内文字超过 3 个短词 → ≤ 0.75
16. 多场景快速切换且需要后期剪辑 → ≤ 0.50
17. 用户明确要求"无需后期"但 NoPostRiskLoad ≥0.30 → ≤ 0.60
18. NoPostRiskLoad ≥0.50 → ≤ 0.50

```
FinalNoPostGate = min(BaseNoPostGate, all triggered Cap limits)
```

#### NoPostGate 输出

- **通过：** FinalNoPostGate ≥ 0.85
- **谨慎通过：** FinalNoPostGate 0.70-0.84
- **不通过：** FinalNoPostGate < 0.70

---

### K19. PostReadyScore

满分 6 分。

| 维度 | 标准 | 1 分 | 0 分 |
|:--|:--|:--|:--|
| P1 | Prompt 可直接复制 | 是 | 否 |
| P2 | 标题完整 | 至少有反差/POV/情绪/功能四类 | 否 |
| P3 | 标签完整 | 12-16 个，覆盖品类/平台/场景/增长 | 否 |
| P4 | 置顶评论有效 | 能补足卖点、互动或 CTA | 否 |
| P5 | Bio CTA / 商品卡承接完整 | 能承接转化 | 否 |
| P6 | 风险边界清楚 | 明确说明 NoPost、先验、生成风险、A/B 建议 | 否 |

PostReadyScore：6 = 通过 / 4-5 = 谨慎通过 / ≤3 = 不通过

---

### K20. 低分诊断映射表

| # | 触发条件 | 可编辑区域 | 修改动作 | 接受标准 |
|:--|:--|:--|:--|:--|
| 1 | Q1 ≤3 | 第 1-2 秒 | 加声音事件、动作动词、视觉冲突 | Q1 +1 且 PRC 不降 |
| 2 | Q2 ≤3 | 第 2-4 秒 | 提前产品出现，让产品成为转折条件，加材质细节 | Q2 +1 且广告腔不增 |
| 3 | Q3 ≤3 | 全文感官 | 补充音效、材质、光影、手部交互 | Q3 +1 且不堆砌 |
| 4 | Q4 ≤3 | 可截图画面+末句 | 加截图点、反转、首尾呼应、复播点 | Q4 +1 且不复杂化 |
| 5 | Q5 ≤3 | 全文动作 | 减角色、减场景、简化动作链 | Q5 +1 且 Hook 不降 |
| 6 | Q6 ≤3 | CTA 段落 | 强化画面动作 CTA，销售表达移到标题/评论/Bio | Q6 +1 且 NoPostGate 不降 |
| 7 | Q7 ≤3 | 全文复杂度 | 降精准文字、复杂物理、长对白、复杂运镜 | Q7 +1 且 PRC 上升 |
| 8 | Q8 ≤2 | Hook+中段+结尾 | Hook 改"不可能"事件，加角色选择，结尾改反预期 | Q8 +1 且不靠内心独白 |
| 9 | Q8 子特征缺失 | 对应段落 | 缺#1→改开头; 缺#2→加中段压力; 缺#3→加动作选择; 缺#4→改结尾; 缺#5→改前后情绪 | 对应子特征→1 |
| 10 | PRC 低 | 低置信 KVS | 删复杂元素，减主体/场景，降强同步 | PRC 至少升一级 |
| 11 | EAD 低 | 最长同情绪段 | 缩平铺段，加情绪转折 | EAD 至少升一级 |
| 12 | NoPostGate 不通过 | 后期依赖段 | 删后期依赖、精准文字、价格、Logo、URL | NoPostGate 至少谨慎通过 |
| 13 | G_market 低 | 文化敏感元素 | 改为更通用的情绪或产品行为 | G_market ≥ 0.85 |
| 14 | CriticPass ≤2 | 叙事/产品/情绪/复播/传播 | 强化对应项 | CriticPass +1 |
| 15 | Naturalness 低 | 广告腔/堆砌/解释 | 删广告腔、堆砌、解释，改动作和画面 | Naturalness 升至中 |
| 16 | SC 不通过 | 系列一致性 | 统一角色/世界观/风格/CTA/情绪 | SC ≥ 4/5 |

---

### K21. 接受与回滚规则

#### 接受条件（满足至少一条）

1. StructureScore 提升 ≥3 分，且 PRC 不下降。
2. Q8 +1，且 Q1/Q4 不下降。
3. Q2 +1，且广告腔不增加。
4. PRC 升一级，且 Creative 不明显下降。
5. NoPostGate 升一级，且 ProductPower 不下降。
6. EAD 升一级，且时长不超过 15 秒。
7. CriticPass +1，且 P_penalty 不增加。
8. Naturalness 升一级，且 Q2 不下降。
9. G_market 升一级，且情绪冲击不下降。
10. A1-A7 或 C1-C4 有明确提升，且总风险不增加。

#### 回滚条件（满足任一条）

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
11. 修复后 G_market 下降。
12. 修复后 Naturalness 下降。
13. 修复后运镜规则被破坏。
14. 修复后 CriticPass 下降。
15. 修复后字数超限。

---

### K22. 硬淘汰（11 条）

| # | 条件 | 对应模块 | 备注 |
|:--|:--|:--|:--|
| 1 | Q1 ≤ 2 | Q1 HookPower | Hook 极弱 |
| 2 | Q2 ≤ 2 | Q2 ProductPower | 产品几乎未出现 |
| 3 | Q4 ≤ 2 | Q4 Spreadability | 无传播力 |
| 4 | CreativeScore < 65 | StructureScore | 总分过低 |
| 5 | 字数超限 | 铁律 #4 | >2500 汉字或 >5000 英文字符 |
| 6 | 不可修复合规风险 | NaturalnessCheck | 人工审查标记 |
| 7 | 产品完全未出现 | Q2#1 + Q2#4 | 两个子特征同时为 0 |
| 8 | EAD=低 + LongFlatPenalty | K12 EAD | ≥8 秒连续同一情绪 |
| 9 | PRC=低 + 无兜底方案 | K11 PRC | KVS ≥3 项低置信且无法修复 |
| 10 | NoPostGate=不通过 + 用户要求无后期 | K18 NoPostGate | 硬性冲突 |
| 11 | 不可修复模型执行风险 | E3/E4/E8 | ReworkNeeded = Major |

Q8 < 3 不硬淘汰，改为强制 Repair/Enhance。

---

### K23. PS-4 数据回流指标

校准记录必须包含以下阈值和动作：

| # | 指标 | 触发条件 | 校准动作 |
|:--|:--|:--|:--|
| 1 | Q1→ThreeSecondViewRate | Q1≥4 但 3秒率<35% | 校准 Q1#1-#3 |
| 2 | Q8→ThreeSecondViewRate | Q8≥4 但 3秒率<35% | 校准 Q8#1 |
| 3 | Q8→复播率 | Q8≥4 但复播<15% | 校准 Q8#4 |
| 4 | Q8→完播率 | Q8≥4 但完播低 | 校准 Q8#2/#5 |
| 5 | EAD→完播率曲线 | EAD 高但中段掉点 | 定位最长平铺段 |
| 6 | PRC→画面可用率 | PRC 高但失败率>30% | 校准 KVS 置信度 |
| 7 | SC→系列追看率 | SC≥4 但追看<20% | 校准 SC 评估标准 |
| 8 | NoPostGate→可发布比例 | 通过但>30%需后期 | 校准 N1-N8 和 Cap Rules |
| 9 | VEL→画面精致度 | VEL 植入后无提升 | 减少抽象增强词 |
| 10 | 音频→音频自然度 | 音频自然度低 | 降对白复杂度 |
| 11 | CreativeScore→ROI | ≥85 但 ROI 持续低 | 校准权重 |

---

### K24. Product Interaction Response（产品交互响应）

**v2.1-MVP-r1 新增。**

适用于智能硬件品类：音箱、灯具、耳机、智能手表、可穿戴设备、智能家居、氛围灯、充电设备等。

**核心公式：**

```
Human Trigger → Product Response → Human Micro-Change → Choice Outcome
```

**字段要求：**

| 字段 | 说明 | 必填 |
|:--|:--|:--|
| H1 Human Trigger | 人对产品做出的可见动作 | 是 |
| P1 Product Response | 产品做出的即时反馈 | 是 |
| P2 Response Modality | 光/声/振动/温度/运动/屏幕变化 | 是 |
| H2 Human Micro-Change | 人物身体语言发生变化 | 是 |
| H3 Choice Outcome | 继续/停止/保留/关闭/远离/交给别人 | 是 |

**示例（音箱场景）：**
- H1: Her fingertips make contact with the matte surface.
- P1: The ambient light shifts to warm gold and pulses once.
- P2: 光色变化 + 脉冲节奏
- H2: Her hand pauses above the surface.
- H3: She lets the light stay on.

**等效映射（非智能硬件）：**
- 保温杯：H1=母亲推杯 → P1=蒸汽升起 → H2=女儿捧杯 → H3=她喝一口
- 腰扇：H1=她夹上风扇 → P1=风扇转动 → H2=她身体放松 → H3=她开始跳舞

**判定等级：**
- **高：** H1+P1+H2+H3 四项完整
- **中：** 有 H1+P1，但 H2 或 H3 较弱
- **低：** 产品只是被展示，没有对人物行为产生反馈

外部输出：产品交互响应：高/中/低 + 一句话说明。

---

### K25. Audio-Visual Sync（音画同步）

**v2.1-MVP-r1 新增。**

关键视觉事件必须允许绑定同步音频事件。

**标准格式：**

```
[Sound event] strikes / begins / cuts in exactly as [visual event].
```

**音频层级模板：**

| 层级 | 说明 | 示例 |
|:--|:--|:--|
| Base layer | 环境音，全片存在 | rain tapping / wind / crowd |
| Structure layer | 音乐，保持较低音量 | lo-fi piano / ambient / beat |
| Impact layer | 同步事件，与视觉关键帧绑定 | bass note at LED activation |
| Intimate detail | 微声，情绪峰值前后 | breath / fabric / fingertip |
| Closing layer | 延续，结尾区 | bass pulse fading / rain continuing |

**规则：**
1. Impact layer 必须与一个关键视觉事件同步。
2. 不得超过 2 个同步点（避免音画过载）。
3. Base layer 必须全片存在（除非场景本身无声）。
4. Structure layer 不得压过 Base layer（除非有意设计）。
5. Intimate detail 在情绪峰值前后出现。

**与 K2 四元公式的关系：**
K2 要求"必须包含音频描述"，K25 进一步要求"音频中至少有 1 个事件与视觉关键帧同步"。两者同时生效。

---

### K26. Product Fidelity Gate（产品形态保真门）

**v2.1-MVP-r1 新增。**

当产品具有明确结构特征时，Prompt 必须写入产品形态锁定句，并在渲染后检查是否漂移。

**产品形态锁定公式：**

```
Product category + body shape + material + key functional feature
+ forbidden transformations
```

**示例：**
"The speaker must remain a small upright cylindrical speaker with a matte black body and a thin LED ring around the exterior. Do not turn the LED ring into a screen, display panel, waveform panel, glowing face, or decorative front screen."

**渲染后判定：**

| 分数 | 判定 |
|:--|:--|
| 5 | 产品形态完全一致 |
| 4 | 轻微风格化，但核心结构一致 |
| 3 | 可识别为同类产品，但关键结构有偏差 |
| 2 | 产品功能或结构明显漂移 |
| 1 | 产品变成另一类物体 |
| 0 | 产品不可识别 |

**Release Gate：**
- ProductFidelityScore ≥ 4 → 通过
- ProductFidelityScore = 3 → 谨慎通过
- ProductFidelityScore ≤ 2 → 不通过，必须重渲染

与 StructureScore 的关系：K26 是 Release Gate 指标，不进入 StructureScore 主公式。连续完成 ≥30 条同品类同市场真实渲染/投放数据后，再考虑是否纳入 G_gate。

---

### K27. NoText / NoLogo Render Audit（伪文字/伪Logo渲染审计）

**v2.1-MVP-r1 新增。**

即使 Prompt 写了 no text / no logo，渲染后仍必须检查画面中是否出现伪文字、伪品牌、小标记、符号、假 UI、假标签。

**Prompt 加固句（建议添加）：**

"No visible logo, no brand mark, no text, no symbols, no letters, no fake UI, no decorative markings anywhere on the product or in the scene. The product surface must remain completely blank."

**渲染后判定：**

| 等级 | 描述 |
|:--|:--|
| Pass | 无文字、无 Logo、无符号 |
| Caution | 有极小不可读纹理，不影响投放 |
| Fail | 有明显伪文字、伪 Logo、品牌感标记或 UI |

**处理规则：**
- Pass → 可进入下一步
- Caution → 如平台审核风险低可保留；正式投放建议重渲染
- Fail → 不进入投放包，必须重渲染

与铁律#6的关系：铁律#6 管输入（Prompt 不写文字），K27 管输出（渲染结果有无文字）。

---

### K28. Director Intent Layer（导演意图层）

**v2.2 新增。**

在写运镜和动作之前，必须先写一段导演意图声明，说明这段视频的叙事逻辑。

**标准格式：**

```
"Begin with [起始焦点], then reveal [展开元素], finally show [落点状态]."

或：

"The video starts with [X]. As [Y] happens, [Z] is revealed."
```

**示例：**
- ✓ "Begin with the room's rain-lit emptiness, then reveal how the speaker's light and sound change the woman's body language."
- ✓ "The video starts with an extreme close-up of the speaker. Only after the light expands is the room revealed."

**禁止：**
- ✗ 不写导演意图，直接写镜头指令。
- ✗ 使用元指令（"First...Then...Finally..."）作为导演意图——元指令会强制 HH 先渲染环境再渲染产品。

**与 K5.1 的关系：**
K28 定义"叙事逻辑"（先看什么→再看什么→最后看到什么），K5.1 定义"运镜路径"（镜头从哪→经过哪→到哪）。K28 在 K5.1 之前执行。

---

### K29. Narrative Scene Dressing（叙事场景布置）

**v2.2 新增。**

场景中的物体不应只是"存在"，而应至少有 1 个物体包含"叙事状态"描述——即通过物体的状态告诉观众"这里发生过什么"。

**标准格式：**

```
[物体名称] + [使用痕迹 / 位置状态 / 损耗程度]
```

**示例：**
- ✓ "Cardboard moving boxes with tape marks stacked unevenly" → 经历过打包、搬运
- ✓ "A worn tablecloth on a round wooden table" → 日常使用多年
- ✓ "A small framed photograph partially hidden behind the coffee maker" → 被有意或无意放在不显眼位置

**禁止：**
- ✗ "A clean modern kitchen with white countertops" → 只有审美描述，没有叙事状态
- ✗ "A beautiful living room with nice furniture" → 无叙事信息

**判定：**
场景中至少 1 个物体有叙事状态描述 → 通过。所有物体只有审美/功能描述 → 触发修复。

与 VEL 的关系：VEL 增强画面感官，K29 建立场景叙事历史。两者互补，不冲突。

---

### K30. Character Imperfection Detail（角色不完美细节）

**v2.2 新增。**

每个角色应至少有 1 个"不完美细节"，用于建立真实感和 Reali-TEA 趋势对齐。

**标准格式：**

```
[角色外貌/服装/姿态] + [一个不完美/生活化的细节]
```

**不完美细节类型：**

| 类型 | 示例 |
|:--|:--|
| 发型凌乱 | loose, slightly messy |
| 服装过大 | sleeves extending past wrists |
| 使用痕迹 | coffee stain, wrinkles |
| 穿着不整 | sock falling halfway off |
| 妆容不全 | smudged mascara |
| 身体疲惫 | dark circles under eyes |
| 姿态随意 | slouching, leaning |

**判定：**
每个角色至少 1 个不完美细节 → 通过。所有角色描述都完美无瑕 → 触发修复。

**注意：**
不完美细节不是丑化角色，而是建立"这个人是真实的"信号。2026 TikTok Reali-TEA 趋势表明，"带点瑕疵的本能感"比精致完美更有传播力。

---

# 第四篇：Layer 2 — Runtime（执行器）

---

### R1. 执行流程

每次执行必须按以下流程：

1. 读取用户输入。
2. 自动补全缺失信息。
3. 计算输入完整度 ICS（10 个核心字段 × 1 分）。
4. 判断 HappyHorse 模式：T2V / I2V / R2V / V2V。
5. 生成 3 个候选方向：A. 强 Hook 版 / B. 情绪反转版 / C. 产品功能驱动版。
6. 三个候选必须在至少 4 项上不同：Hook、产品出场、情绪弧线、CTA 策略、镜头语言、结尾记忆点、传播点。
7. 对每个候选进行 ShowDontTell 预检。
8. 对每个候选植入 VEL。
9. **对每个候选填写 L1-L6 六层检查表（v2.2 新增）。**
10. 对每个候选逐项计算 Q1-Q8 子特征。
11. 对每个候选计算 StructureScore（双轨）。
12. 对每个候选判断 PRC、EAD、CriticPass、Naturalness、NoPostGate、PostReady、CF、HU。
13. 找出低分项。
14. 按低分诊断映射表修复。
15. 最多修复 2 轮，每轮最多改 2 句。
16. 按接受/回滚规则决定是否保留修复。
17. 选择 Winner。
18. 输出 Delivery（13 项）。

---

### R2. 候选要求

- **A. 强 Hook 版：** 前 1 秒有声音事件、动作、视觉冲突或异常画面。
- **B. 情绪反转版：** 存在明确情绪变化，例如好奇→紧张→释放，冷漠→惊讶→认同。
- **C. 产品功能驱动版：** 产品必须成为剧情转折条件，而不是摆拍道具。

三个候选必须在以下至少 4 项上不同：Hook、产品出场方式、情绪弧线、CTA 策略、镜头语言、结尾记忆点、传播点。

---

### R3. Winner 选择

排序：
1. SS 高者优先。
2. NoPostReady = true 优先（用户要求无后期时）。
3. SS 差距 <3 时 Tie-breaker：Q8 更高 → NoPostGate 更高 → Q7 更高 → PostReady 更高 → Q1 更高 → Q2 更高。

---

### R4. Emotional Narrative Engine（情绪叙事引擎）

**v2.2 新增。**

每个 Prompt 生成时，必须按以下六层顺序评估叙事结构：

| 层级 | 核心问题 | 必备元素 | 对应指标 | 对应评分 |
|:--|:--|:--|:--|:--|
| **L1 注意** | 前 3 秒凭什么让手指停下来？ | 朝向反应 + 信息缺口 | 3 秒存留率 | Q1 HookPower |
| **L2 叙事** | 为什么要继续看？ | 因果链 + 未完成感 | 完播率 | Q4#4 + Q4#5 |
| **L3 情绪** | 身体在模拟什么？ | 具身认知 + 状态过渡 | 情绪评论率 | Q8 + K7.2 |
| **L4 符号** | 产品在故事里代表什么？ | 符号互动（产品被重新编码） | 产品记忆度 | Q2#2 |
| **L5 传播** | 分享时在表达什么？ | 双向路径 + 低社交风险 | 分享率 | Q4 + Q6 |
| **L6 转化** | 从感动到购买的路径？ | Bio/评论/商品卡承接 | CTR、CVR | Q6#1 #5 |

**执行规则：**
1. 每个候选生成后，必须填写 L1-L6 六层检查表。
2. 任何一层为空（无对应元素），必须触发修复。
3. L1-L6 不替代 Q1-Q8 评分，而是作为叙事结构预检。
4. L1-L6 检查表输出到 Delivery 模板第 11 项。

**L1-L6 与 Q1-Q8 的映射：**

| L 层 | 主要对应 Q | 次要对应 Q |
|:--|:--|:--|
| L1 注意 | Q1 | Q3#1 |
| L2 叙事 | Q4#4 | Q4#5 |
| L3 情绪 | Q8 | Q3#4 |
| L4 符号 | Q2#2 | Q2#5 |
| L5 传播 | Q4 | Q6#2 |
| L6 转化 | Q6 | Q6#5 |

**理论引用索引：**

| 层级 | 引用理论 |
|:--|:--|
| L1 | 朝向反应、信息缺口（Loewenstein 1994）、冯·雷斯托夫效应 |
| L2 | 叙事运输（Green & Brock 2000）、蔡格尼克效应（1927）、预测加工（Clark 2013） |
| L3 | 依恋理论（Bowlby 1969）、情绪传染（Hatfield 1993）、具身认知（Varela 1991）、峰终定律（Kahneman 2000） |
| L4 | 符号互动论（Mead 1934）、框架理论（Goffman 1974） |
| L5 | 两级传播（Lazarsfeld 1944）、印象管理（Goffman 1959）、使用与满足（Katz 1974）、情绪传播（Berger & Milkman 2012） |
| L6 | ELM 外周路径（Petty & Cacioppo 1986）、情感品牌 |

**理论边界声明：**
本文所引用的理论用于解释创意结构的传播潜力，不用于预测投放效果。具体效果需通过渲染质量、平台分发、受众匹配、商品价格和落地页转化共同验证。

---

### R5. Smart Hardware Prompt Generation Flow（智能硬件 Prompt 生成流程）

**v2.2 新增。**

适用于音箱、灯具、耳机、智能手表、可穿戴设备、智能家居、氛围灯等品类。

**标准流程（10 步）：**

| 步骤 | 内容 | 依据 |
|:--|:--|:--|
| Step 1 | 写场景锚点：地点+时间+光线+至少1个叙事物体 | K29 |
| Step 2 | 写产品形态锁定：品类+形状+材质+特征+禁止变形 | K26 |
| Step 3 | 写角色初始状态：身体姿态+至少1个不完美细节 | K7.2 + K30 |
| Step 4 | 写导演意图："Begin with...then reveal...finally show..." | K28 |
| Step 5 | 写产品激活事件：人类触发+产品即时响应+响应模态 | K24 |
| Step 6 | 写音画同步冲击："exactly as"绑定音频与视觉 | K25 |
| Step 7 | 写人物状态过渡：初始状态→微动作→终点状态 | K7.2 |
| Step 8 | 写选择模式 | K8.1 |
| Step 9 | 写结尾 | Q8#4 |
| Step 10 | 写禁止项：产品形态禁止变形+无文字无Logo+场景稳定性 | K26+K27 |

---

### R6. Rendering Submission Strategy（渲染提交策略）

**v2.2 新增。**

从 v1.1→v1.2 验证中提炼的 4 条提交策略，适用于所有品类。

| 策略 | 规则 | 目的 |
|:--|:--|:--|
| **策略 1：首帧锚定** | 运动段首句写明"The video starts with [关键元素]" | 确保 Q1 Hook 命中率 |
| **策略 2：锁定前置** | 产品形态锁定句放在主体描述中，不放末尾附注 | 确保 K26 ProductFidelity |
| **策略 3：音频前置** | 音频段首句写明基底层"[Ambient sound] is audible from the first frame" | 确保 K25 AudioLayer |
| **策略 4：时长锁** | 场景段末尾写"The video must stay under 14.8 seconds." | 确保铁律#1 |

**验证证据（v2.1-MVP-r1 Pilot）：**

| 策略 | v1.1（未执行） | v1.2（执行后） |
|:--|:--|:--|
| 策略1 | 开头空房间先行 | 音箱 ECU 首帧 |
| 策略2 | 锁定放附注 | 锁定前置至主体段 → Pass |
| 策略3 | 雨声前2秒不可听 | Rain audible from first frame → 5/5 |
| 策略4 | 15.16s | 14.75s |

**提交策略检查表：**

```
□ 运动段首句是否写明首帧关键元素？
□ 产品形态锁定是否在主体描述中（非附注）？
□ 音频段首句是否写明基底层音频？
□ 场景段是否写明时长锁？
□ 禁止项是否同时出现在主体描述和附注中？
```

---

# 第五篇：Layer 3 — Delivery（交付界面）

---

v2.2 Delivery 模板从 10 项扩展为 13 项：

```
【1. 输入理解与自动假设】
- 产品/对象：
- 品类：
- 目标市场：
- 目标人群：
- 核心卖点：
- 使用场景：
- 平台：
- HappyHorse 模式：
- NoPost 是否激活：
- 缺失信息：
- 自动假设：
- 输入完整度 ICS：x/10

【2. 候选搜索摘要】
候选 / 核心 Hook / 产品出场方式 / 情绪弧线 / 主要风险 / 初评分

【3. Winner 选择】
- 为什么选它
- 为什么它更适合 HappyHorse
- 为什么它更适合 NoPost
- 为什么它比另外两个候选更适合投放

【4. 最终 HappyHorse Prompt】
（单独代码块，只放 Prompt，不放解释）
必须包含：导演意图声明（K28）/ 产品形态锁定（K26）/ 不完美细节（K30）/ 首帧锚定（R6）/ 时长锁（R6）

【5. 投放资产】
- 标题 A：反差型
- 标题 B：POV 型
- 标题 C：情绪型
- 标题 D：功能型
- 标签：按 5 类框架生成（品类/平台/场景/增长/好奇心种子），12-18 个
- 置顶评论版本一：情绪优先版
- 置顶评论版本二：承接转化版
- Bio CTA：1 条
- 商品卡短文案：1 条

【6. 评分卡】
维度 / 分数或等级 / 理由 / 是否需要修复
包含：HardGate / CreativeScore / U_domain / G_gate / R_risk / B_bonus / P_penalty
Q1-Q8 / PRC / EAD / CriticPass / Naturalness
NoPostGate / PostReady / CF / HU / Overall
PromptScore_Naked（Q6 口径 A）
PackageScore_Estimated（Q6 口径 B）
r1 渲染后审计字段（渲染后填写）

【7. 迭代摘要】
- 初版主要问题
- 修复动作
- 修复后提升
- 停止迭代原因
- 是否达到当前约束下的局部最优

【8. VEL 植入记录】
- A 类物理真实
- B 类角色生命
- C 类材质光影
- D 类大气粒子
- K7.1 环境光材质交互
- K7.2 状态锚点→过渡
- 是否超量
- 是否与运镜冲突

【9. 校准记录】
- ThreeSecondViewRate 假设
- 完播率假设
- 互动率假设
- 点击率假设
- 转化率假设
- 对应 PS-4 回流指标
- 当前置信度
- 需要未来真实数据校准的字段

【10. 风险声明】
- 当前评分是专家先验，不是实际投放预测。
- NoPost 表示直接发布导向，不保证每次生成都完全无需人工检查。
- HappyHorse 最终效果取决于实际渲染结果。
- 商业投放建议至少生成 3 条视频做 A/B 测试。

【11. L1-L6 叙事检查表】（v2.2 新增）
| 层级 | 必备元素 | 具体实现 | 理论依据 |
|:--|:--|:--|:--|
| L1 注意 | ✓/✗ | [描述] | [理论] |
| L2 叙事 | ✓/✗ | [描述] | [理论] |
| L3 情绪 | ✓/✗ | [描述] | [理论] |
| L4 符号 | ✓/✗ | [描述] | [理论] |
| L5 传播 | ✓/✗ | [描述] | [理论] |
| L6 转化 | ✓/✗ | [描述] | [理论] |

【12. 节点复用方案】（v2.2 新增）
| 节点 | 时间 | 标题调整 | 标签增补 | 情绪侧重 |
|:--|:--|:--|:--|:--|

执行规则：同一视频可用于多个节点，仅更换标题和标签。

【13. 平台适配说明】（v2.2 新增）
| 维度 | 主投放平台 | 适配说明 |
|:--|:--|:--|
| 时长 | | |
| 画幅 | | |
| 音频风格 | | |
| 标签数量 | | |
| 评论策略 | | |
| 转化路径 | | |
```

---

# 第六篇：Layer 4 — Audit（审计模式）

---

只有当用户明确要求"展开评分/审计模式/完整验算/查看子特征/查看KVS/查看EAD/查看动态权重/查看CF/HU/查看候选全文/查看接受回滚过程"时才输出。

### 15-Step Verification

1. Q1-Q8 子特征逐项判断（40 个子特征 × 0/1）。
2. q1-q8 标准化（qi = Qi / 5）。
3. U_creative / U_product / U_execution / U_delivery。
4. 动态权重调整（品类 Δ + 归一化）。
5. U_domain。
6. G_gate 明细（G_hook / G_product / G_reliability / G_market / G_nopost）。
7. R_risk 明细（RiskLoad 7 项判断 → 查表）。
8. B_bonus 明细（亮点计数 → 查表）。
9. P_penalty 明细（10 项扣分）。
10. StructureScore 计算链（完整乘式 + clamp）。
11. NoPostRiskLoad N1-N8 明细 + BaseNoPostGate。
12. Cap Rules + FinalNoPostGate + NoPostGate。
13. PostReadyScore P1-P6。
14. PRC/KVS 逐项 + EAD 时间线 + LongFlatPenalty + CF/HU 依据 + 修复前后对比 + 接受/回滚理由。
15. **r1 渲染后审计（v2.2 升级为所有品类默认）：**
    - 15a. ProductFidelityScore（0-5）
    - 15b. NoTextNoLogoActual（Pass/Caution/Fail）
    - 15c. InteractionCausalityScore（0-5）
    - 15d. AVSyncScore（0-5）
    - 15e. LightMaterialStability（0-5）
    - 15f. SceneDriftScore（0-5）
    - 15g. FacialNaturalnessScore（0-5）
    - 15h. DurationActualSec（数值）
    - 15i. AudioLayerScore（0-5）
    - 15j. NoPostActual（Pass/Caution/Fail）

审计模式还必须额外输出：
- CriticPass 5 项逐项
- NaturalnessCheck 8 项逐项
- A1-A7 逐项
- C1-C4 逐项
- Q3 质量标注（基本/强）

---

# 第七篇：Layer 5 — Evaluation（评测协议）

---

### E1. Render Test：HappyHorse 生成回测

每个产品至少生成 3 条视频。

每条视频生成后必须记录以下字段：

| 字段 | 取值 | 说明 |
|:--|:--|:--|
| RenderSuccess | Yes / Partial / No | 是否成功生成完整视频 |
| VisualUsability | High / Medium / Low | 画面是否可直接使用 |
| ProductVisibility | Clear / Partial / Unclear | 产品是否清楚出现 |
| MotionAccuracy | High / Medium / Low | 动作是否符合 Prompt |
| FaceBodyStabilityScore | 0 / 1 / 2 | 人物脸部和身体稳定性 |
| FaceBodyApplicable | Yes / No | 是否涉及人物 |
| TextFailureSeverity | None / Minor / Severe | 是否出现错误文字、乱码 |
| AudioMatchScore | 0 / 1 / 2 | 音频匹配度 |
| AudioApplicable | Yes / No | 是否涉及音频 |
| PRC_Actual | High / Medium / Low | 实际渲染置信度 |
| ReworkNeeded | None / Minor / Major | 是否需要人工返工 |
| FailureReason | 见 Error Taxonomy | 失败原因 |

---

### E2. NoPost Audit：无需后期审查

| 等级 | 含义 |
|:--|:--|
| DirectReady (3) | 无需后期可直接发布 |
| LightEdit (2) | 主体可用，但建议轻微剪辑、字幕或封面优化 |
| NeedsPost (1) | 必须后期处理才可发布 |
| Reject (0) | 不可发布 |

---

### E3. Small Batch Ad Test：小样本投放回测

| 字段 | 说明 |
|:--|:--|
| Platform | TikTok / Reels / Shorts / 小红书 / 其他 |
| Spend | 测试预算 |
| Impressions | 曝光量 |
| ThreeSecondViewRate | 3 秒停留率 |
| CompletionRate | 完播率 |
| RewatchRate | 复播率 |
| LikeRate / CommentRate / ShareRate | 互动率 |
| CTR / CVR | 点击率 / 转化率 |
| CPA / ROAS / ROI | 如有 |
| RetentionCurveLink | 完整留存曲线 |
| MajorDropoffSecond | 主要掉点秒数 |
| MidpointRetentionRate | 中点留存率 |
| DropoffNote | 掉点模式描述 |
| AudienceSignal | 评论情绪/收藏意图/购买意图/质疑点 |

---

### E4. Release Gate：版本发布门槛

满足以下条件才可宣称系统稳定：

1. 至少测试 10 个产品。
2. 每个产品至少 3 条视频。
3. 总样本至少 30 条生成视频。
4. 至少覆盖 5 个品类。
5. RenderSuccess ≥ 80%。
6. DirectReady + LightEdit ≥ 70%。
7. Reject ≤ 15%。
8. PRC_Pre 与 PRC_Actual 一致率 ≥ 70%。
9. NoPostGate_Pre 与 NoPostActual 一致率 ≥ 70%。
10. Q1 高分组的 ThreeSecondViewRate 至少高于低分组 5 个百分点或相对提升 ≥ 15%。
11. Q8 高分组的 CompletionRate 或 RewatchRate 至少高于低分组 5 个百分点或相对提升 ≥ 15%。
12. 至少完成一轮 Calibration Action。
13. 所有失败样本都有 FailureReason。
14. 所有 Kernel 级修改都有数据依据。

---

# 第八篇：Layer 6 — Benchmark（评测工作台）

---

### B1. Test Set Design：测试集设计

最低测试集：10 产品 × 3 条 = 30 条。推荐：20 产品 × 3 条 = 60 条。

覆盖至少 5 类：美妆/穿搭/食品、数码/工具/软件/设备、家居/生活方式、高客单价产品、低客单价冲动消费。

---

### B2. Annotation Rubric：人工标注规则

每条生成视频必须至少由 1 名人工标注。条件允许时建议 2 名独立标注。分歧超过 1 分必须复审。

---

### B3. Error Taxonomy：失败类型分类

| 编号 | 失败类型 | 对应模块 |
|:--|:--|:--|
| E1 | 产品不清楚 | Q2 / ProductVisibility |
| E2 | 动作不符合 Prompt | Q5 / MotionAccuracy |
| E3 | 人脸或身体异常 | FaceBodyStabilityScore |
| E4 | 文字乱码或错误文字 | N1 / 铁律#5 |
| E5 | 音频不自然 | AudioMatchScore |
| E6 | 口型不同步 | N6 |
| E7 | 场景混乱 | Q5#2 / Q7#4 |
| E8 | 运镜失败 | 运镜指令体系 |
| E9 | 情绪弧不成立 | Q8 / EAD |
| E10 | 产品像硬广 | P_penalty / CriticPass#2 |
| E11 | CTA 不成立 | Q6 / NoPostGate |
| E12 | 需要后期才能理解 | NoPostGate / N4/N5 |
| E13 | VEL 无效或堆叠 | VEL 规则 / Naturalness |
| E14 | 画面质感不足 | Q3 / PRC |
| E15 | 生成成功但不适合投放 | HumanOverall / PostReady |
| **PF-01** | **产品形态漂移** | **K26** |
| **PF-02** | **产品关键特征丢失** | **K26** |
| **PF-03** | **LED环被渲染成屏幕/显示面板** | **K26** |
| **NT-01** | **伪Logo** | **K27** |
| **NT-02** | **伪字母/伪文字** | **K27** |
| **NT-03** | **假UI/假标签** | **K27** |
| **AV-01** | **视觉事件与音频不同步** | **K25** |
| **AV-02** | **音乐压过环境音** | **K25** |
| **IR-01** | **人类触发动作不清晰** | **K24** |
| **IR-02** | **产品响应不清晰** | **K24** |
| **IR-03** | **人物情绪变化不清晰** | **K24** |
| **SCN-01** | **场景过度装饰化** | **K5.1** |
| **SCN-02** | **房间身份漂移** | **K5.1** |
| **DUR-01** | **渲染超过15秒** | **K4#1** |

---

### B4. Metric Mapping：指标映射

| 预评分 | 实际指标 | 偏差触发 |
|:--|:--|:--|
| PRC_Pre | RenderSuccess / VisualQuality / MotionAccuracy | PRC_Pre高但实际低 |
| NoPostGate_Pre | NoPostActual | 通过但实际低 |
| Q1_Pre | ThreeSecondViewRate | ≥4 但 3秒率<35% |
| Q8_Pre | CompletionRate / RewatchRate | ≥4 但完播/复播低 |
| EAD_Pre | CompletionRate 曲线 / MajorDropoffSecond | 高但中段掉点 |
| Q2_Pre | ProductVisibility / CTR | 高但产品不清 |
| Q6_Pre | CTR / CVR | 高但转化低 |
| VEL 记录 | VisualQuality | 完整但质量低 |
| Audio 描述 | AudioMatchScore | 完整但不匹配 |

---

### B5. Calibration Matrix：校准矩阵（11 条）

| # | 偏差模式 | 校准对象 | 校准动作 |
|:--|:--|:--|:--|
| 1 | PRC_Pre高但RenderSuccess低 | PRC / Q7 / KVS | 提高复杂物理、多主体、多场景风险权重 |
| 2 | PRC_Pre高但ProductVisibility低 | Q2 / PRC | 提高产品可见性要求 |
| 3 | NoPostGate通过但NoPostActual低 | NoPostRiskLoad / Cap Rules | 提高 N1、N4、N6、N8 权重 |
| 4 | Q1_Pre高但ThreeSecondViewRate低 | Q1#1-#3 | 收紧声音事件、视觉冲突判定 |
| 5 | Q8_Pre高但CompletionRate低 | Q8#2 / Q8#5 / EAD | 收紧有效情绪段判定 |
| 6 | Q8_Pre高但RewatchRate低 | Q8#4 / Q4#5 | 收紧结尾反预期判定 |
| 7 | Q6_Pre高但CTR低 | 标题/评论/Bio/商品卡 | 重写投放资产 |
| 8 | CTR高但CVR低 | 产品承诺/商品卡/落地页 | 检查卖点是否过度承诺 |
| 9 | VEL完整但VisualQuality低 | VEL 词库 | 减少抽象增强词，优先材质光影和角色生命 |
| 10 | AudioMatchScore平均分<1.3 | 音频描述规则 | 减少长对白，改为环境音、动作声 |
| 11 | SCScore≥4但SeriesFollowRate<20% | SC 评估标准 | 校准集间悬念判定 |

---

### B6. Calibration Action Levels：校准动作等级

| 级别 | 名称 | 适用场景 | 影响范围 |
|:--|:--|:--|:--|
| Level 1 | 文案级修正 | 标题/标签/评论/Bio/商品卡弱 | 只改投放资产 |
| Level 2 | Prompt 级修正 | 产品不清/情绪弧弱/CTA不成立/VEL无效 | 修改 Prompt 结构 |
| Level 3 | Kernel 级修正 | PRC/NoPostGate/Q1/Q8 系统性失真 | 调整评分权重/门控规则 |

---

### B7. Pilot Baseline Data（Pilot 基准数据）

**v2.2 新增。**

v2.1-MVP-r1 Smart Hardware Patch 首轮验证基准：

| 审计项 | v1.1 | v1.2 | 改善幅度 |
|:--|:--|:--|:--|
| ProductFidelityScore | 4/5 | 5/5 | +1 |
| NoTextNoLogoActual | Fail | Pass | 关键修复 |
| InteractionCausalityScore | 4/5 | 5/5 | +1 |
| AVSyncScore | 3/5 | 5/5 | +2 |
| LightMaterialStability | 4/5 | 5/5 | +1 |
| SceneDriftScore | 4/5 | 5/5 | +1 |
| FacialNaturalnessScore | 4/5 | 5/5 | +1 |
| DurationActualSec | 15.16s | 14.75s | -0.41s |
| AudioLayerScore | 2/5 | 5/5 | +3 |
| NoPostActual | Fail边缘 | Pass | 关键修复 |

**关键结论：**
1. r1 的 4 条提交策略全部有效。
2. 产品表面锁定前置是最关键修正。
3. 雨声首帧可听是最显著效果提升。
4. 时长锁有效防止超时。
5. 剧情和创意设计零改动即可实现以上改善。

**限制：** 样本量仅为 2 条，不具备统计意义。仅覆盖 1 个品类。未包含投放数据验证。

---

# 第九篇：Layer 7 — Operations（运营系统）

---

### O1. 数据库表结构（9 张表）

#### 表间关系总览

```
Product Table（产品主表）
  │ 1:N
  ▼
Prompt Table（Prompt 主表）
  ├── 1:1 → PreScore Table（预评分）
  ├── 1:N → RenderResult Table（渲染结果）
  │           ├── 1:N → AdResult Table（投放数据）
  │           ├── 1:N → Annotation Table（独立标注）
  │           └── 1:1 → Series Table（系列连贯性，仅系列内容）
  └── 1:N → VEL Table（VEL 植入记录）

CalibrationLog Table（校准日志）
  独立记录版本校准日志
```

<details>
<summary>点击展开：Product Table 字段定义</summary>

| 字段名 | 字段类型 | 是否必填 | 说明 |
|:--|:--|:--|:--|
| ProductID | 文本 | 是 | 如 `PROD-001` |
| ProductName | 文本 | 是 | 产品名称 |
| Category | 单选 | 是 | 美妆/穿搭/食品/数码/工具/软件/设备/家居/生活方式/其他 |
| PriceBand | 文本 | 是 | 低客单价/中客单价/中高客单价/高客单价 |
| Market | 文本 | 是 | 如中国大陆/东南亚/北美/欧洲 |
| TargetAudience | 长文本 | 是 | 目标人群描述 |
| CoreSellingPoint | 长文本 | 是 | 核心卖点 |
| UseCase | 长文本 | 是 | 使用场景 |
| CreatedDate | 日期 | 是 | 创建日期 |

</details>

<details>
<summary>点击展开：Prompt Table 字段定义（含 v2.2 新增）</summary>

| 字段名 | 字段类型 | 是否必填 | 说明 |
|:--|:--|:--|:--|
| PromptID | 文本 | 是 | 如 `PROMPT-PROD001-A-v1` |
| ProductID | 关联 | 是 | 关联 Product Table |
| PromptVersion | 文本 | 是 | 如 `v1` / `v2` / `v1-r1` |
| CandidateType | 单选 | 是 | A_StrongHook / B_EmotionReversal / C_ProductFunction |
| HappyHorseMode | 单选 | 是 | T2V / I2V / R2V / V2V |
| PromptText | 长文本 | 是 | 完整 Prompt |
| TitleA-D | 文本 | 否 | 4 类标题 |
| Tags | 文本 | 否 | 12-18 个，逗号分隔 |
| PinnedComment | 长文本 | 否 | 置顶评论 |
| BioCTA | 文本 | 否 | Bio CTA |
| ProductCardCopy | 文本 | 否 | 商品卡文案 |
| CreatedDate | 日期 | 是 | 创建日期 |
| **DirectorIntent** | **长文本** | **否** | **K28 导演意图声明** |
| **NarrativeSceneDressing** | **长文本** | **否** | **K29 叙事物体描述** |
| **CharacterImperfection** | **长文本** | **否** | **K30 不完美细节** |
| **L1_Check ~ L6_Check** | **勾选** | **否** | **六层叙事检查** |
| **NodeReusePlan** | **长文本** | **否** | **节点复用方案** |
| **PlatformAdaptation** | **长文本** | **否** | **平台适配说明** |
| **ProductFidelityRequirement** | **长文本** | **否** | **产品形态锁定句** |
| **RenderingSequencePriority** | **长文本** | **否** | **渲染顺序附注** |
| **AVSyncEvent** | **文本** | **否** | **音画同步点描述** |
| **CameraPathIntent** | **长文本** | **否** | **运镜路径意图** |
| **ChoicePattern** | **单选** | **否** | **K8.1 选择模式** |
| **StateTransitionPair** | **长文本** | **否** | **K7.2 初始→终点状态** |
| **PromptScore_Naked** | **数值** | **否** | **Prompt 裸分** |
| **PackageScore_Estimated** | **数值** | **否** | **完整投放包预估分** |
| **SmartHardwareApplicable** | **勾选** | **否** | **是否适用 K24** |
| **ProductResponsePattern** | **单选** | **否** | **光/声/振动/温度/运动/屏幕** |
| **SubmissionStrategyChecklist** | **勾选×4** | **否** | **R6 四项策略** |

</details>

<details>
<summary>点击展开：PreScore Table 字段定义</summary>

| 字段名 | 字段类型 | 是否必填 | 说明 |
|:--|:--|:--|:--|
| PromptID | 关联 | 是 | 关联 Prompt Table |
| CreativeScore_Pre | 数值 | 是 | 0-100 |
| Q1_Pre ~ Q8_Pre | 数值 | 是 | 各 0-5 |
| PRC_Pre | 单选 | 是 | High / Medium / Low |
| EAD_Pre | 单选 | 是 | High / Medium / Low |
| NoPostGate_Pre | 单选 | 是 | 通过 / 谨慎通过 / 不通过 |
| PostReady_Pre | 单选 | 是 | 通过 / 谨慎通过 / 不通过 |
| CF_Pre | 单选 | 是 | High / Medium / Low |
| HU_Pre | 单选 | 是 | Low / Medium / High |
| U_domain | 数值 | 是 | 0.00-1.00 |
| G_gate | 数值 | 是 | 0.00-1.00 |
| R_risk | 数值 | 是 | 0.78-1.00 |
| B_bonus | 数值 | 是 | 1.000-1.060 |
| P_penalty | 数值 | 是 | ≥0，整数 |

</details>

<details>
<summary>点击展开：RenderResult Table 字段定义（含 v2.2 永久化字段）</summary>

| 字段名 | 字段类型 | 是否必填 | 说明 |
|:--|:--|:--|:--|
| VideoID | 文本 | 是 | |
| PromptID | 关联 | 是 | |
| VideoLink | URL/文本 | 是 | 视频文件入口 |
| RenderSuccess | 数值 | 创建时必填 | 2/1/0 |
| VisualQuality | 数值 | 标注后必填 | 2/1/0 |
| ProductVisibility | 数值 | 标注后必填 | 2/1/0 |
| MotionAccuracy | 数值 | 标注后必填 | 2/1/0 |
| FaceBodyStabilityScore | 数值 | 标注后必填 | 2/1/0 |
| FaceBodyApplicable | 单选 | 标注后必填 | Yes/No |
| AudioMatchScore | 数值 | 标注后必填 | 2/1/0 |
| AudioApplicable | 单选 | 标注后必填 | Yes/No |
| TextQualityScore | 数值 | 标注后必填 | 2/1/0 |
| PRC_Actual | 单选 | 标注后必填 | High/Medium/Low |
| NoPostActual | 数值 | 标注后必填 | 3/2/1/0 |
| ReworkNeeded | 单选 | 标注后必填 | None/Minor/Major |
| FailureReason_Main | 单选 | 否 | E1-E15 + PF/NT/AV/IR/SCN/DUR |
| FailureReason_Secondary | 单选 | 否 | 同上 |
| HumanOverall | 数值 | 标注后必填 | 3/2/1/0 |
| **ProductFidelityScore** | **数值 0-5** | **渲染后** | **产品形态保真** |
| **NoTextNoLogoActual** | **Pass/Caution/Fail** | **渲染后** | **伪文字审计** |
| **InteractionCausalityScore** | **数值 0-5** | **渲染后** | **触碰因果链** |
| **AVSyncScore** | **数值 0-5** | **渲染后** | **音画同步** |
| **LightMaterialStability** | **数值 0-5** | **渲染后** | **光效材质稳定** |
| **SceneDriftScore** | **数值 0-5** | **渲染后** | **场景漂移** |
| **FacialNaturalnessScore** | **数值 0-5** | **渲染后** | **面部自然度** |
| **DurationActualSec** | **数值** | **渲染后** | **实际时长** |
| **AudioLayerScore** | **数值 0-5** | **渲染后** | **音频层级** |
| **HHFailureTags** | **多选** | **渲染后** | **PF/NT/AV/IR/SCN/DUR 标签** |

</details>

<details>
<summary>点击展开：AdResult / CalibrationLog / VEL / Annotation / Series Table 字段定义</summary>

**AdResult Table：** 主键 VideoID + Platform + TestDate。字段包括 Spend、Impressions、ThreeSecondViewRate、CompletionRate、RewatchRate、LikeRate、CommentRate、ShareRate、CTR、CVR、CPA、ROAS、ROI、RetentionCurveLink、MajorDropoffSecond、MidpointRetentionRate、DropoffNote、AudienceSignal、TestDate。

**CalibrationLog Table：** 主键 CalibrationID。字段包括 VersionBefore、VersionAfter、TriggeredByData、ProblemDetected、ModuleChanged、RuleBefore、RuleAfter、ExpectedImprovement、ActionLevel、RollbackCondition、Owner、Date、Status（Draft/Active-Pilot/Active-Stable/Advisory/Deprecated/Rollback）。

**VEL Table：** 主键 PromptID + VEL_Type + VEL_Position。字段包括 VEL_Type（A/B/C/D/K7.1）、VEL_Content、VEL_Position、VEL_RenderResult、CreatedDate。

**Annotation Table：** 主键 AnnotationID。字段关联 VideoID，包含 AnnotatorID、全部评分字段、Notes、AnnotationDate。

**Series Table：** 主键 SeriesID + EpisodeNumber。字段关联 VideoID，包含 CharacterConsistency、WorldConsistency、VisualStyleConsistency、CTAConsistency、EmotionContinuity、SCScore、SeriesFollowRate、Notes。

</details>

---

### O2. 18 个核心视图设计

#### 9 个默认视图

| 编号 | 视图名称 | 基于表 | 视图类型 | 排序 | 分组 |
|:--|:--|:--|:--|:--|:--|
| 1 | 全部产品 | Product | Grid | CreatedDate 降序 | Category |
| 2 | 全部 Prompt | Prompt | Grid | CreatedDate 降序 | ProductID |
| 3 | 全部预评分 | PreScore | Grid | CreativeScore_Pre 降序 | PRC_Pre |
| 4 | 全部渲染结果 | RenderResult | Grid | AnnotationDate 降序 | RenderSuccess |
| 5 | 全部投放数据 | AdResult | Grid | TestDate 降序 | Platform |
| 6 | 全部校准记录 | CalibrationLog | Grid | Date 降序 | ActionLevel |
| 7 | 全部 VEL 记录 | VEL | Grid | CreatedDate 降序 | VEL_Type |
| 8 | 全部独立标注 | Annotation | Grid | AnnotationDate 降序 | VideoID |
| 9 | 全部系列记录 | Series | Grid | CreatedDate 降序 | SeriesID |

#### 视图 #10-#18

| 编号 | 视图名称 | 说明 |
|:--|:--|:--|
| 10 | Pilot 执行看板 | Kanban：待预评分→待渲染→待标注→标注完成→已投放 |
| 11 | 独立标注视图 | 当前 AnnotatorID 的未标注记录 |
| 12 | 标注分歧检查 | 同一 VideoID 下 HumanOverall 分歧 > 1 |
| 13 | 最终复审视图 | AnnotationDate 为空的 RenderResult |
| 14 | NoPost 风险追踪 | NoPostActual ≤ 1 |
| 15 | PRC 偏差追踪 | PRC_Actual 比 PRC_Pre 低至少一个等级 |
| 16 | Q1/Q8 投放信号追踪 | 预评分高但投放指标低 |
| 17 | EAD 曲线掉点追踪 | EAD_Pre = High 且 MajorDropoffSecond 在 4-10 秒 |
| 18 | 校准待办视图 | 待评估 / 已执行 / 需观察 / 已回滚 |

---

### O3. Decision Dashboard：每轮测试输出（15 项）

| 编号 | 输出项 |
|:--|:--|
| 1 | 测试产品数 |
| 2 | 生成视频数 |
| 3 | RenderSuccess 比例（基准 ≥80%） |
| 4 | DirectReady 比例 |
| 5 | LightEdit 比例（#4+#5 ≥70%） |
| 6 | Reject 比例（≤15%） |
| 7 | PRC 一致率（≥70%） |
| 8 | NoPost 一致率（≥70%） |
| 9 | Q1 高低分组 3秒率差异（≥5pp 或 ≥15%） |
| 10 | Q8 高低分组 完播/复播差异 |
| 11 | 失败类型 Top 5 |
| 12 | 校准模块 Top 5 |
| 13 | 本轮校准动作 |
| 14 | 是否进入下一发布等级 |
| 15 | 下一轮测试建议 |

---

### O4. 团队协作角色

| 角色 | 职责 |
|:--|:--|
| Creative Operator | 输入产品信息，运行 Creative Compiler，生成候选 Prompt |
| Render Reviewer | 观看 HappyHorse 输出视频，完成标注 |
| Ad Tester | 小预算投放和数据记录 |
| Calibration Owner | 判断是否修改 Prompt、投放资产或 Kernel 规则 |

---

### O5. 角色权限

| 角色 | 读写表 | 只读表 | 关键视图 |
|:--|:--|:--|:--|
| Creative Operator | Product / Prompt / VEL | 其余 | Pilot 执行看板 |
| Render Reviewer | RenderResult / Annotation / Series | 其余 | 独立标注 / 分歧检查 / 最终复审 / NoPost 风险 |
| Ad Tester | AdResult | 其余 | Q1/Q8 Signal |
| Calibration Owner | PreScore / CalibrationLog | 其余 | PRC 偏差 / EAD 掉点 / 校准待办 / Dashboard |
| 个人项目 | 全部读写 | — | 全部视图 |

---

### O6. 发布等级

| 等级 | 名称 | 条件 | 可以宣称 |
|:--|:--|:--|:--|
| Level 0 | Prompt Prototype | 只有 Prompt，无真实数据 | 结构化创意生成与专家先验评分系统 |
| Level 1 | Render Validated | ≥30 条生成，RenderSuccess≥80%，PRC 一致率≥70% | 经过渲染回测的创意编译系统 |
| Level 2 | NoPost Validated | DirectReady+LightEdit≥70%，Reject≤15% | 经过 NoPost 验证的直接发布系统 |
| Level 3 | Ad Signal Validated | Q1/Q8 高低分组差异 ≥5pp 或 ≥15% | 具备投放信号区分能力的评分系统 |
| Level 4 | Calibration Ready | 至少一轮数据校准 | 经过数据校准的创意评估系统 |

仍然不能称为：投放效果预测系统。

---

### O7. 版本治理

版本命名：v2.2 / v2.2-r1 / v2.2-r2 ...

Status 生命周期：Draft → Active-Pilot → Active-Stable → Advisory / Deprecated / Rollback

**禁止事项：**
1. 不允许因为单条视频失败就修改 Kernel。
2. 不允许因为单个产品表现好就宣称系统有效。
3. 不允许没有数据就修改权重。
4. 不允许将专家评分说成预测模型。
5. 不允许忽略失败样本。

---

# 第十篇：Pilot 执行指南

---

### 一、Pilot 总览

| 项目 | 参数 |
|:--|:--|
| 产品数 | 3 |
| 每产品候选数 | 3（A_StrongHook / B_EmotionReversal / C_ProductFunction） |
| 总 Prompt 数 | 9 |
| 总生成视频数 | 9（每条 Prompt 生成 1 条） |
| 品类覆盖 | 3（扩展到 30 条时补齐至 5 类） |
| 总周期 | 约 12 天 |

### 二、品类与产品选择

| 编号 | 品类 | PriceBand | 消费特征 |
|:--|:--|:--|:--|
| 品类 1 | 美妆/穿搭/食品（任选其一） | 中客单价 | 计划消费 |
| 品类 2 | 数码/工具/设备（任选其一） | 中高客单价 | 计划消费 |
| 品类 3 | 家居/生活方式/创意小物（任选其一） | 低客单价 | 冲动消费 |

### 三、Pilot 时间线

```
Day 0:     准备（建表 / 建视图 / 选产品 / 备图）
Day 1-3:   Prompt 生成（9 条 Prompt + 评分 + VEL + L1-L6 检查）
Day 4-5:   渲染生成（9 条视频 + 占位记录）
Day 5-7:   标注（独立标注 + 分歧检查 + 最终复审 + r1 渲染审计）
Day 7-10:  投放测试（可投放视频 × 1 平台）
Day 10-12: Dashboard 输出 + 校准判断 + 下轮建议
```

### 四、标注流程（含 v2.2 r1 审计）

| 步骤 | 基于表 | 视图 | 执行者 | 内容 |
|:--|:--|:--|:--|:--|
| 独立标注 | Annotation | 独立标注视图 | Render Reviewer | 全部评分 |
| 分歧检查 | Annotation | 分歧检查视图 | Render Reviewer | 分歧 > 1 触发复审 |
| 最终复审 | RenderResult | 最终复审视图 | PrimaryAnnotatorID | 聚合写入 |
| **r1 渲染审计** | **RenderResult** | **最终复审视图** | **Render Reviewer** | **10 项 r1 审计字段** |

---

# 第十一篇：执行 Checklist

---

### 阶段一：准备（Day 0）

| 编号 | 任务 | 产出 |
|:--|:--|:--|
| P-01 | 建 9 张表（含 v2.2 新增字段） | 表结构就绪 |
| P-02 | 建 18 个视图 | 视图就绪 |
| P-03 | 配角色权限 | 权限就绪 |
| P-04 | 选 3 个品类和 3 个产品 | Product Table 3 条记录 |
| P-05 | 准备产品图 | 每产品 ≥1 张高清图 |

### 阶段二：Prompt 生成（Day 1-3）

| 编号 | 任务 | 产出 |
|:--|:--|:--|
| P-06 | 产品 1 生成 3 个候选 | Prompt Table +3 |
| P-07 | 产品 1 评分（含 L1-L6 检查） | PreScore Table +3 |
| P-08 | 产品 1 VEL 植入（含 K7.1/K7.2） | VEL Table +9~12 |
| P-09 | 产品 2 生成 3 个候选 | Prompt Table +3 |
| P-10 | 产品 2 评分 + VEL | PreScore +3 / VEL +9~12 |
| P-11 | 产品 3 生成 3 个候选 | Prompt Table +3 |
| P-12 | 产品 3 评分 + VEL | PreScore +3 / VEL +9~12 |

### 阶段三：渲染生成（Day 4-5）

| 编号 | 任务 | 产出 |
|:--|:--|:--|
| P-13 | 9 条 Prompt 提交渲染（应用 R6 提交策略） | 9 条视频 |
| P-14 | 初步观察记录 | 临时备注 |
| P-15 | 创建 RenderResult 占位记录 | 9 条（含 r1 字段） |

### 阶段四：标注（Day 5-7）

| 编号 | 任务 | 产出 |
|:--|:--|:--|
| P-16 | Annotation 独立标注 | 9 条（单人）或 18 条（双人） |
| P-17 | 分歧检查 | 分歧 > 1 标记 |
| P-18 | RenderResult 最终复审 | 9 条记录完整标注 |
| P-19 | r1 渲染后审计（10 项） | 9 条 r1 审计 |
| P-20 | FailureReason 归类 | E1-E15 + PF/NT/AV/IR/SCN/DUR |

### 阶段五：投放测试（Day 7-10）

| 编号 | 任务 | 产出 |
|:--|:--|:--|
| P-21 | 筛选可投放视频 | IsPublishable = "是" |
| P-22 | 提交投放 | 每条 1 平台 |
| P-23 | 记录投放指标 | AdResult Table |
| P-24 | 记录 AudienceSignal | AdResult 中填写 |

### 阶段六：Dashboard 与校准（Day 10-12）

| 编号 | 任务 | 产出 |
|:--|:--|:--|
| P-25 | 输出 Dashboard 15 项 | Pilot Run Report |
| P-26 | 失败类型 Top 5 | 统计列表 |
| P-27 | 识别校准需求 | CalibrationLog ≥1 条 |
| P-28 | 判断 Level 1 | 记录为样本不足 |
| P-29 | 输出下轮建议 | 自由文本 |

### Pilot 完成标准

| 编号 | 标准 |
|:--|:--|
| 1 | 8 张表有记录（Series 可空） |
| 2 | 18 个视图全部可打开 |
| 3 | 9 条 Prompt 全部完成评分（含 L1-L6） |
| 4 | 9 条视频全部完成标注（含 r1 审计） |
| 5 | 目标 ≥6 条进入投放 |
| 6 | Dashboard 15 项全部输出 |
| 7 | CalibrationLog ≥1 条 |
| 8 | 所有失败样本有 FailureReason |

### 扩展路径

| 阶段 | 产品 | 视频 | 品类 | 目标 |
|:--|:--|:--|:--|:--|
| Pilot | 3 | 9 | 3 | 流程验证 |
| 扩展第一轮 | +4（累计 7） | +12（累计 21） | +2（累计 5） | 品类覆盖达标 |
| 扩展第二轮 | +3（累计 10） | +9（累计 30） | 维持 5 | 样本量达标 |

---

# 第十二篇：附录

---

### A1. Anti-Pseudoscience 声明

1. 所有权重均为专家先验，不是训练得到的参数。
2. StructureScore 不预测 CTR、CVR、ROI、销量或平台分发。
3. HeuristicUncertainty 不是统计置信区间。
4. G_market 是文化适配启发式，不代表平台分发概率。
5. NoPostGate 只评估完全不后期的可行性，不保证无需修正。
6. PostReady 只评估标准后期兜底后的可交付性。
7. Q8 EmotionalImpact 的子特征判定存在主观性，不同运行可能给出 ±1 浮动。
8. EAD 情绪类型枚举可能不覆盖所有内容类型。
9. PRC 的 KVS 识别和置信度分级依赖人工标注。
10. SeriesCoherence 仅评估系列内部递进。
11. 只有在接入 ≥30 条同品类同市场投放数据并完成回归校准后，才允许讨论预测关系。
12. 有限终止证明保证流程在有限步骤内返回，不保证全局最优。
13. 若 HappyHorse 模型更新，Q7、铁律、PRC 参数需重新校准。
14. VEL 增强词的实际渲染效果取决于 HappyHorse 1.0 的渲染引擎精度。
15. HappyHorse 音视频联合生成的音频质量需平台实测数据校准。
16. **R4 六层模型引用的心理学和传播学理论用于解释创意结构的传播潜力，不用于预测投放效果。**
17. **K24-K30 的产品交互响应、音画同步、产品保真等规则的实际效果需通过渲染数据验证。**

---

### A2. 阶段性必填说明

| 阶段 | 必填表 | 说明 |
|:--|:--|:--|
| 创建 Prompt 时 | Product / Prompt / PreScore / VEL | 基础字段全部填写（含 v2.2 新增） |
| 渲染后 | RenderResult（占位）/ VEL_RenderResult | 占位记录 |
| 标注后 | Annotation / RenderResult（完整） | 全部评分字段 + r1 审计字段聚合写入 |
| 投放后 | AdResult | 投放指标 |
| 系列激活时 | Series | 仅系列内容 |

---

### A3. 落地平台映射

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

### A4. VideoLink 字段说明

VideoLink 为 v2.1-MVP 执行层必要字段，用于承接实际视频文件。该字段不改变理论评分结构，仅解决执行层"视频文件入口缺失"问题。

---

### A5. 版本历史

| 版本 | 核心变更 |
|:--|:--|
| v1.0 | 完整规范文档 |
| v1.7-Final | 精算编译器 |
| v1.8-Eval | 实验协议 |
| v1.9-Bench | 评测工作台 |
| v2.0 | 创意操作系统：7 模块 + 6 张表 + 4 角色 + Level 0-4 |
| v2.0.1 | 系统规范定稿 |
| v2.1-MVP | 表格落地版：9 张表 + 18 视图 + Pilot 指南 |
| v2.1-MVP-r1 | Smart Hardware Sensory Patch：K5.1-K27 + r1 审计字段 |
| **v2.2** | **正式版：M1 六层叙事引擎 + M2 Prompt 工程规则 + M3 评分精修 + M4 内容策略 + M5 Pilot 基准** |

**版本治理链：**
```
v2.0 → v2.0.1 → v2.1-MVP → v2.1-MVP-r1 (Superseded) → v2.2 (Active)
```

---

### A6. 一句话定位

```
HappyHorse CreativeOS v2.2
= 把产品卖点编译成可生成、可评分、可审计、可回测、可归因、可校准、可持续进化的 AI 视频广告系统。
```

---

### A7. v2.2 升级总览

| 模块 | 名称 | 核心内容 |
|:--|:--|:--|
| M1 | Emotional Narrative Engine | L1-L6 六层模型写入 Runtime |
| M2 | Prompt Engineering Rules | K28 导演意图 + K29 场景布置 + K30 角色不完美 + R5 智能硬件流程 + R6 提交策略 |
| M3 | Scoring & Audit Refinements | Q6 双轨 + Q3 质量标注 + Q8#4 静止结尾 + 15-Step 审计 |
| M4 | Content Strategy Layer | 节点复用 + 平台适配 + 好奇心种子标签 |
| M5 | Pilot Learnings Integration | B7 基准数据 |

---

### A8. r1 补丁状态

```
v2.1-MVP-r1 Smart Hardware Sensory Patch
  旧状态：Active-Pilot
  新状态：Superseded
  原因：r1 的 8 项 Kernel 补丁（K5.1-K27）已全部吸收进 v2.2 正式版
  历史记录：保留在 CalibrationLog 中，可追溯
```

---

**HappyHorse CreativeOS v2.2 — 完整文档结束。**
