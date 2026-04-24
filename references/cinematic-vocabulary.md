# 电影级提示词词汇表 (Cinematic Vocabulary for Seedance 2.0) v2.15

> **用途**：构建 Seedance 2.0 的高质量 Prompt。本词汇表基于 Seedance 2.0 **官方指令标准**和社区最佳实践编写，全面对齐官方的镜头语言理解能力。
> **更新版本**：v2.15 (2026.05) —— 全面对齐 Seedance 2.0 官方标准，新增“官方6步公式”专题、最佳长度建议、正/负向词对照表、短视频SEO关键词库，升级运镜词库精度。


## 第一部分：Seedance 2.0 官方指令标准

> **核心原则**：Seedance 2.0 是一个能理解镜头语言、运镜逻辑的“视觉导演”，而非简单的“你描述，它生成”工具。提示词越符合导演指令格式，生成效果越稳定。

### 1.1 官方6步公式

所有提示词必须遵循 Seedance 2.0 的最优公式：

| 步骤 | 维度 | 英文指令示例 | 中文指令示例 | 权重 |
| :--- | :--- | :--- | :--- | :--- |
| **1** | **主体/角色** | `A young woman in her 20s` | `一位20多岁的年轻女性` | 最高 |
| **2** | **动作/剧情** | `Slowly wiping a greasy stove` | `缓慢擦拭油腻的灶台` | 最高 |
| **3** | **环境/场景** | `In a small American studio apartment kitchen` | `在一间小型美式公寓厨房中` | 高 |
| **4** | **镜头/运镜** | `Macro close-up, slow dolly-in` | `微距特写，缓慢推近` | 最高 |
| **5** | **风格/氛围** | `Warm cozy tones, natural window light` | `暖色调温馨感，自然窗光` | 中 |
| **6** | **约束/避坑** | `Well-formed hands, Stable object geometry` | `手部完好，物体几何稳定` | 中 |

> **注意**：Seedance 2.0 对镜头运动指令的优先级最高，对主体和动作的描述次之。风格和氛围有助于统一画面质感，约束项有助于减少 AI 瑕疵。

### 1.2 最佳长度建议

| 长度范围 | 适用场景 | 说明 |
| :--- | :--- | :--- |
| **30-60 词** | **直给型单镜头（推荐）** | 精准落入模型最佳注意力窗口，执行率最高 |
| **60-100 词** | **直给型单镜头（稳妥上限）** | 官方推荐区间，可包含完整六要素 |
| **100-150 词** | 复杂场景单镜头 | 需结构化分段，避免大段混排 |
| **150-200 词** | 多动作/多运镜（不推荐） | 指令之间互相稀释，容易导致执行不稳定 |
| **200+ 词** | **严禁单次输入** | 必须拆分为原子化分段指令，每段独立生成 |

> **核心原则**：**一条指令，一个镜头，一种主导运镜。** 绝对不要试图用一条长指令生成多个镜头的复杂叙事。

### 1.3 约束机制

| 约束方式 | 说明 | 示例 |
| :--- | :--- | :--- |
| ✅ **正向锚点词** | 用正向肯定描述锁定画面质感 | `Crystal-clear`, `Steady motion`, `Sharp focus` |
| ✅ **显式排除法** | 使用 `avoid` 排除不想要的元素（正向表达，非否定式） | `avoid jitter`, `avoid overexposed highlights` |
| ❌ **否定式负向词** | Seedance 2.0 **不支持**。使用 `no/not/don't` 的指令会被忽略，甚至触发反效果 | `~~No warping~~`, `~~No extra fingers~~`, `~~Don't make it blurry~~` |


## 第二部分：原子化分段提示词模板

> **原则**：直给型视频必须输出为独立的镜头段落，每段 30-60 词。叙事型视频每段≤100 词。后期在剪映中拼接。

### 2.1 直给型模板（4镜头示例）

```
[镜头1: 0-3s | 痛点快切 + 手持POV]
4K UHD, 48fps, 35mm lens. Quick whip pan across a greasy messy stove, thick yellow stains visible. Handheld POV shot with subtle breathing motion. Clean bright lighting. Snappy motion.

[镜头2: 3-4s | 微距特写 + 声音同步]
4K UHD, 120fps, 100mm macro lens. Extreme macro close-up of blue sponge touching the grease. Grease instantly dissolves on contact revealing mirror-like stainless steel. Visual sync with crisp "ding" sound. Well-formed hands, Stable object geometry.

[镜头3: 4-7s | 多角度快切]
4K UHD, 48fps, 50mm lens. Multi-angle quick cuts of wiping process, each wipe reveals more clean surface. Natural window light, crisp highlights. Steady motion, sharp focus on product.

[镜头4: 7-15s | 结果定格 + CTA引导]
4K UHD, 50mm lens. Slow dolly-out to wide shot of perfectly clean stove. Hand wipes across the reflective surface. Freeze frame on mirror-like finish for 2 seconds. Clear space for text overlay. Softbox lighting.
```

### 2.2 叙事型模板（单段示例）

```
[段落1: 0-12s | 困境建立]
4K UHD, 48fps, 35mm lens. Young woman in her mid-20s, tired expression, opens an almost empty fridge in a small studio apartment. Natural window light from city windows. Warm but exhausted lighting. Handheld POV shot. Authentic unscripted feel.
```

### 2.3 段落间一致性控制

Seedance 2.0 每次生成是独立的，需要在提示词中锁定一致性：

**锁定要素**（每段提示词必须包含）：
```
Subject: [角色外貌描述，每段保持一致]
Location: [场景描述，每段保持一致]
Lighting: [光影风格，每段保持一致]
Color grade: [色调风格，每段保持一致]
```

**变化要素**（每段不同）：
- 镜头角度（wide → close-up → overhead → medium）
- 主角动作和情绪
- 焦点对象


## 第三部分：正/负向词对照表（新增）

> **核心原则**：用正向锚点词替代否定式负向词。Seedance 2.0 对正向描述的响应准确率远高于否定式指令。

| 想要的效果 | ✅ 使用（正向锚点词） | ❌ 禁止（否定式负向词） |
| :--- | :--- | :--- |
| **手部完好** | `Well-formed hands`, `Natural hand pose`, `Five fingers` | `No extra fingers`, `No deformed hands` |
| **面部自然** | `Natural facial features`, `Soft expressions`, `Lifelike face` | `No face distortion`, `No creepy face` |
| **物体几何稳定** | `Stable object geometry`, `Solid shape`, `Consistent form` | `No warping`, `No morphing` |
| **画面清晰锐利** | `Crystal-clear`, `Tack-sharp`, `4K hyper-realistic` | `No blur`, `Don't make it blurry` |
| **运动稳定** | `Steady motion`, `Smooth camera movement`, `Minimal shake` | `No jitter`, `No shaky cam` |
| **光照自然** | `Natural window light`, `Softbox lighting`, `Even exposure` | `No harsh shadows`, `Don't overexpose` |
| **产品对焦清晰** | `Sharp focus on product`, `Product in crisp detail` | `Don't make the product blurry` |
| **无AI感** | `Organic unscripted feel`, `Authentic lived-in look` | `No AI artifacts`, `Don't look fake` |


## 第四部分：标准化运镜词库（v2.15 精度升级）

> Seedance 2.0 对以下运镜指令识别率极高。推荐使用混写格式（中文意境 + 英文精准指令）。**每段只指定一种主导运镜**。

### 4.1 基础运镜

| 运镜类型 | 混写推荐格式 | 适用场景 | 识别精度 |
| :--- | :--- | :--- | :--- |
| **推镜** | `缓慢推近 (Slow dolly-in)` / `推至特写 (Push to close-up)` | 聚焦产品细节 | ⭐⭐⭐⭐⭐ |
| **拉镜** | `缓慢拉远 (Slow dolly-out)` / `后拉至全景 (Pull back to wide shot)` | 从细节过渡到全貌 | ⭐⭐⭐⭐⭐ |
| **横摇** | `向左横摇 (Pan left)` / `右摇90度 (Pan right 90°)` | 展示场景宽度 | ⭐⭐⭐⭐ |
| **竖摇** | `向上摇镜 (Tilt up)` / `向下摇镜 (Tilt down)` | 展示高度或垂直结构 | ⭐⭐⭐⭐ |
| **环绕** | `轻微环绕 (Slight orbit)` / `半圈环绕 (Half orbit)` | 360度展示产品 | ⭐⭐⭐⭐⭐ |
| **跟拍** | `稳定跟拍 (Steady tracking shot)` / `侧面跟拍 (Side tracking)` | 跟随人物或物体 | ⭐⭐⭐⭐ |
| **升降** | `镜头上升 (Pedestal up)` / `镜头下降 (Pedestal down)` | 改变视角高度 | ⭐⭐⭐ |
| **固定机位** | `固定镜头 (Static shot)` / `中景固定 (Medium static shot)` | 稳定展示 | ⭐⭐⭐⭐⭐ |

### 4.2 进阶运镜组合（仅推荐 Standard 模式使用）

| 组合类型 | 混写推荐格式 | 效果描述 | 适用模式 |
| :--- | :--- | :--- | :--- |
| **推近+环绕** | `缓慢推近同时轻微环绕 (Slow dolly-in with slight orbit)` | 产品展示经典运镜 | 仅 Standard |
| **跟拍+微距** | `跟拍后推至微距特写 (Tracking shot into macro close-up)` | 从动作聚焦到效果 | 仅 Standard |
| **快摇转场** | `快速摇摄转场 (Quick whip pan transition)` | 镜头间动感切换 | 通用 |
| **匹配动作转场** | `匹配手部动作转场 (Match cut on hand movement)` | 无缝衔接 | 通用 |

### 4.3 手持感运镜（原生感核心）

| 效果 | 混写推荐格式 | 适用场景 |
| :--- | :--- | :--- |
| **轻微呼吸感** | `轻微手持呼吸感 (Subtle handheld breathing)` | 增加真实感，不眩晕 |
| **第一人称POV** | `手持第一人称视角 (Handheld POV shot)` | 模拟用户视角 |
| **自然晃动** | `生活化自然晃动 (Organic unscripted camera movement)` | **原生感UGC风格（默认）** |
| **稳定为主** | `运镜丝滑几乎无晃动 (Smooth camera motion, minimal shake)` | 专业产品展示 |


## 第五部分：光影系统词汇

### 5.1 光源类型

| 光源类型 | 混写推荐格式 | 视觉效果 |
| :--- | :--- | :--- |
| **柔光箱** | `柔光箱布光 (Softbox lighting)` | 均匀柔和，无硬阴影 |
| **自然窗光** | `自然窗光 (Natural window light)` | 生活化，温暖真实（**原生感默认**） |
| **侧逆光** | `侧逆光轮廓 (Rim light contour)` | 主体边缘发光，立体感 |
| **顶光** | `顶光 (Top-down lighting)` | 聚焦产品，简洁高级 |

### 5.2 光质与色调

| 效果 | 混写推荐格式 | 适用场景 |
| :--- | :--- | :--- |
| **高对比度** | `高对比度阴影 (High contrast shadows)` | 情绪张力，科技产品 |
| **通透高光** | `通透的高光 (Crisp highlights)` | 反光材质 |
| **暖色调** | `暖色调温馨感 (Warm cozy tones)` | 礼品、家居、护理 |
| **冷色调** | `冷色调科技感 (Cool tech aesthetic)` | 3C数码、黑科技 |
| **清新明亮** | `干净明亮 (Clean and bright)` | 清洁、美妆、收纳 |


## 第六部分：短视频SEO关键词库（新增）

> **2026趋势**：短视频平台已成为Z世代首选搜索引擎。在提示词中植入可被搜索索引的关键词元素，可显著提升搜索流量。

### 6.1 关键词权重排序

| 优先级 | 关键词位置 | 权重 | 说明 |
| :--- | :--- | :--- | :--- |
| 🥇 | **语音关键词**（视频前5秒口述） | 最高 | TikTok 语音识别索引 |
| 🥈 | **屏幕文字**（视频内嵌字幕/大字报） | 高 | YouTube Shorts OCR索引 |
| 🥉 | **标题关键词** | 中 | 全平台通用搜索索引 |
| 4 | **话题标签** | 中低 | TikTok/IG/Lemon8 标签索引 |
| 5 | **描述区关键词** | 低（补充） | YouTube SEO |

### 6.2 品类关键词库

| 品类 | 核心关键词（高搜索量） | 长尾关键词（低竞争） |
| :--- | :--- | :--- |
| **锅具** | cast iron pan, non stick pan, cooking hack | uncoated cast iron, yuanbao pot, no oil cooking |
| **清洁** | cleaning hack, cleaning motivation | magic sponge, grease remover, stove cleaning |
| **收纳** | home organization, space saving | small apartment hack, renter friendly, doorway storage |
| **美妆** | beauty hack, nail tutorial | at home manicure, gel nail lamp, DIY nails |
| **3C** | tech review, gadget review | budget tech, affordable gadget, desk setup |
| **食品** | food hack, cooking tok, recipe | one pot meal, lazy recipe, budget meal prep |

### 6.3 提示词中的SEO植入指令

在提示词中加入以下元素，可同时优化视频画面和搜索可见性：

```
Clear space for bold text overlay at bottom third（画面底部留出大字报空间）
Text overlay space for "[核心关键词]"（预留关键词大字报位置）
Voiceover mentions "[核心关键词]" in first 5 seconds（前5秒口述核心关键词）
Search-friendly visual with clear keyword moment（搜索友好视觉）
```


## 第七部分：原生感（UGC风格）词汇包

> **2026 趋势**：原生感是最高转化率的形式，应作为**核心创作原则**。

| 效果 | 混写推荐格式 | 作用 |
| :--- | :--- | :--- |
| **素人演员** | `真实素人反应 (Authentic unscripted reaction)` | 降低广告防备心 |
| **生活化场景** | `生活化杂乱背景 (Lived-in messy background)` | 增强代入感 |
| **手持自拍感** | `自拍视角，轻微手持晃动 (Selfie POV, slightly shaky handheld)` | 模拟真实用户拍摄 |
| **自然光线** | `仅自然窗光 (Natural window light only)` | 去除广告精致感 |
| **轻微瑕疵** | `可见轻微瑕疵 (Slight imperfections visible)` | 增强可信度 |
| **真实音效** | `相机原生收音 (In-camera audio, ambient room sound)` | 避免过度配音 |


## 第八部分：平台尾缀速查

| 平台 | 混写推荐格式 |
| :--- | :--- |
| **通用** | `9:16竖向格式 (9:16 vertical), 15秒循环 (15 seconds loop-ready), 产品清晰对焦 (sharp focus on product)` |
| **TikTok** | `评论引导时刻 (Comment-worthy moment), 分享结尾 (Shareable ending)` |
| **YouTube Shorts** | `搜索友好视觉 (Search-friendly visual)` |
| **Meta Reels** | `真实生活瞬间 (Authentic real-life moment), 真实兴趣内容 (True interest content)` |
| **Pinterest** | `自解释视觉 (Self-explanatory visual), 静音友好 (Muted playback friendly)` |


## 第九部分：Fast 模式提示词技巧

| 技巧 | 说明 | 示例 |
| :--- | :--- | :--- |
| **简化运镜** | 用单层运镜替代复杂组合 | `Slow dolly-in` 替代 `Slow dolly-in with orbit` |
| **降低帧率** | Fast 模式用 24/30fps | `24fps` 或 `30fps` |
| **精简光影** | 1-2 个核心光源词 | `Natural window light` |
| **保留核心约束** | 技术基底和正向锚点词必须保留 | `4K UHD`, `Well-formed hands` |


## 第十部分：品类专属五维提示词速查

### 功能效果型（清洁、美甲灯、美容仪）

| 维度 | 混写推荐指令 | Fast模式精简版 |
| :--- | :--- | :--- |
| **技术基底** | `4K UHD, 48fps, 100mm macro lens` | `4K UHD, 30fps, macro lens` |
| **镜头运动** | `极近微距环绕 (Extreme macro shot, slow orbit)` | `Macro shot, slight orbit` |
| **视觉元素** | `[产品]效果转变过程，前后对比可见` | 同上 |
| **光影系统** | `通透的高光 (Crisp highlights), 侧逆光轮廓 (Rim light)` | `Natural window light, crisp highlights` |
| **动态设计** | `画面与清脆提示音同步 (Visual sync with crisp "ding")` | `Visual sync with ding` |

### 高性价比型（日用百货、服饰）

| 维度 | 混写推荐指令 | Fast模式精简版 |
| :--- | :--- | :--- |
| **技术基底** | `4K UHD, 50mm lens` | `4K UHD, 30fps` |
| **镜头运动** | `缓慢推近至产品细节 (Slow dolly-in to product detail)` | `Slow dolly-in` |
| **视觉元素** | `分屏价格对比 (Split screen price comparison)` | 同上 |
| **光影系统** | `柔光箱布光 (Softbox lighting), 干净明亮` | `Clean bright lighting` |
| **动态设计** | `价格跳动动画+收银机叮声同步` | `Price pulse with ding` |
