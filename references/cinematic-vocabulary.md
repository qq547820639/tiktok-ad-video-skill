# 电影级提示词词汇表 (Cinematic Vocabulary for Seedance 2.0) v2.3

> **用途**：构建 Seedance 2.0 的高质量 Prompt。本词汇表采用 **“五维提示词架构”**，将提示词升级为结构化的导演指令，确保画面质感、运动自然、控制精准。
> **更新版本**：v2.3 (2026.04) —— 升级为五维提示词架构，引入标准化运镜词库，增加原生感词汇包。

---

## 第一部分：五维提示词架构

> **核心思想**：将提示词从“描述性语言”升级为结构化的“技术脚本”，从五个维度独立控制视频生成。

| 维度 | 英文指令示例 | 中文指令示例 | 作用说明 |
| :--- | :--- | :--- | :--- |
| **1. 技术基底** | `4K UHD, HDR10+, 48fps, macro lens` | `4K超高清, HDR10+, 48帧, 微距镜头` | 确定画质、帧率、镜头类型等技术规格 |
| **2. 镜头运动** | `Slow dolly-in, then slight orbit` | `缓慢推近, 再轻微环绕` | 定义镜头如何运动，让画面“活”起来 |
| **3. 视觉元素** | `Wet ground reflecting neon lights` | `潮湿地面反射霓虹光` | 精确描述画面中的物体、人物、特效 |
| **4. 光影系统** | `Cool cyan key light, high contrast` | `冷青色主光, 高对比度` | 独立控制光源，营造氛围和高级感 |
| **5. 动态设计** | `Visual beats sync with heavy bass drops` | `画面随重低音节奏轻微震动` | 描述动态效果、转场、音画同步 |

**使用模板**：
```
[技术基底] + [镜头运动] + [视觉元素] + [光影系统] + [动态设计]
```

**完整示例（美甲灯·过程微距镜头）**：
```
4K UHD, 48fps, 100mm macro lens. Extreme macro shot, slow orbit around the nail surface. Nail surface transforming from matte wet texture to mirror-like glossy finish. Crisp highlights on the glossy surface, rim light. Visual beats sync with a crisp "ding" sound.
```

---

## 第二部分：标准化运镜词库

> Seedance 2.0 对以下运镜指令识别率极高，可直接用于“镜头运动”维度。

### 2.1 基础运镜

| 运镜类型 | 英文 Prompt | 中文提示词 | 适用场景 |
| :--- | :--- | :--- | :--- |
| **推镜** | `Slow dolly-in` / `Push to close-up` | `缓慢推近` / `推至特写` | 引导观众聚焦产品细节 |
| **拉镜** | `Slow dolly-out` / `Pull back to wide shot` | `缓慢拉远` / `后拉至全景` | 从细节过渡到场景全貌 |
| **横摇** | `Pan left` / `Pan right 90 degrees` | `向左横摇` / `右摇90度` | 展示场景宽度或多物品 |
| **竖摇** | `Tilt up` / `Tilt down` | `向上摇镜` / `向下摇镜` | 展示产品高度或垂直结构 |
| **环绕** | `Slight orbit` / `Half orbit` | `轻微环绕` / `半圈环绕` | 360度展示产品外观 |
| **跟拍** | `Steady tracking shot` / `Side tracking` | `稳定跟拍` / `侧面跟拍` | 跟随人物或物体移动 |
| **升降** | `Pedestal up` / `Pedestal down` | `镜头上升` / `镜头下降` | 改变视角高度 |
| **固定机位** | `Static shot` / `Medium static shot` | `固定镜头` / `中景固定` | 稳定展示，不移动 |

### 2.2 进阶运镜组合

| 组合类型 | 英文 Prompt | 中文提示词 | 效果描述 |
| :--- | :--- | :--- | :--- |
| **推近+环绕** | `Slow dolly-in with slight orbit` | `缓慢推近同时轻微环绕` | 产品展示的经典运镜，高级感十足 |
| **拉远+横摇** | `Dolly-out while panning right` | `拉远同时向右横摇` | 从产品过渡到使用场景 |
| **跟拍+微距** | `Tracking shot into macro close-up` | `跟拍后推至微距特写` | 从人物动作聚焦到产品效果 |
| **快摇转场** | `Quick whip pan transition` | `快速摇摄转场` | 双镜头之间的动感切换 |
| **匹配动作转场** | `Match cut on hand movement` | `匹配手部动作转场` | 无缝衔接两个镜头 |

### 2.3 手持感运镜

| 效果 | 英文 Prompt | 中文提示词 | 适用场景 |
| :--- | :--- | :--- | :--- |
| **轻微呼吸感** | `Subtle handheld breathing motion` | `轻微手持呼吸感` | 增加真实感，不眩晕 |
| **第一人称POV** | `Handheld POV shot` | `手持第一人称视角` | 模拟用户视角，代入感强 |
| **自然晃动** | `Organic unscripted camera movement` | `生活化自然晃动` | 原生感UGC风格 |
| **稳定为主** | `Smooth camera motion, minimal shake` | `运镜丝滑, 几乎无晃动` | 专业产品展示 |

---

## 第三部分：光影系统词汇

> 独立控制光源是营造氛围和高级感的核心。比“明亮的灯光”更精确。

### 3.1 光源类型

| 光源类型 | 英文 Prompt | 中文提示词 | 视觉效果 |
| :--- | :--- | :--- | :--- |
| **柔光箱** | `Softbox lighting` | `柔光箱布光` | 均匀柔和，无硬阴影 |
| **自然窗光** | `Natural window light` | `自然窗光` | 生活化，温暖真实 |
| **侧逆光** | `Rim light contour` | `侧逆光轮廓` | 主体边缘发光，突出立体感 |
| **伦勃朗光** | `Rembrandt lighting` | `伦勃朗光` | 一侧脸颊有三角形光斑，戏剧感 |
| **顶光** | `Top-down lighting` | `顶光` | 聚焦产品，简洁高级 |
| **底光** | `Bottom-up lighting` | `底光` | 神秘感、科技感 |

### 3.2 光质与色调

| 效果 | 英文 Prompt | 中文提示词 | 适用场景 |
| :--- | :--- | :--- | :--- |
| **高对比度** | `High contrast shadows` | `高对比度阴影` | 情绪张力，男性/科技产品 |
| **通透高光** | `Crisp highlights` | `通透的高光` | 反光材质（玻璃、金属、甲面） |
| **暖色调** | `Warm cozy tones` | `暖色调温馨感` | 礼品、家居、女性护理 |
| **冷色调** | `Cool tech aesthetic` | `冷色调科技感` | 3C数码、黑科技 |
| **清新明亮** | `Clean and bright` | `干净明亮` | 清洁用品、美妆、收纳 |
| **暗调高级** | `Moody cinematic dark` | `暗调高级感` | 奢侈品、高端产品 |
| **高光过曝** | `Bright and airy overexposed look` | `高光过曝风格` | 清新、女性化产品 |

---

## 第四部分：动态设计词汇

> 描述画面的动态效果、转场和音画同步。

### 4.1 转场方式

| 转场类型 | 英文 Prompt | 中文提示词 | 效果 |
| :--- | :--- | :--- | :--- |
| **快速摇摄** | `Quick whip pan transition` | `快速摇摄转场` | 动感快切，适合节奏型视频 |
| **匹配动作** | `Match cut on hand movement` | `匹配手部动作转场` | 无缝衔接，专业感 |
| **手部遮挡** | `Hand wipes across lens` | `手部遮挡镜头` | 自然转场，原生感强 |
| **延时摄影** | `Timelapse transition` | `延时摄影转场` | 收纳、清洁、过程展示 |
| **模糊转场** | `Blur transition` | `模糊转场` | 柔和过渡 |

### 4.2 画面节奏

| 效果 | 英文 Prompt | 中文提示词 | 适用场景 |
| :--- | :--- | :--- | :--- |
| **干脆利落** | `Snappy motion, Quick cuts` | `干脆利落的运镜, 快速剪辑` | 快节奏爆款视频 |
| **慢动作升格** | `Slow motion, 120fps equivalent` | `慢动作升格` | 过程微距、视觉奇观 |
| **定格** | `Freeze frame on [画面] for 2 seconds` | `定格在[画面]2秒` | 结尾CTA、强调结果 |
| **无缝循环** | `Seamless loop transition` | `无缝循环转场` | 提升复播率 |

### 4.3 音频同步

| 音频类型 | 英文 Prompt | 中文提示词 |
| :--- | :--- | :--- |
| **重低音** | `Visual beats sync with heavy bass drops` | `画面随重低音节奏轻微震动` |
| **轻快旋律** | `Smooth camera movement flowing with upbeat tempo` | `运镜与轻快节奏同步` |
| **ASMR触发** | `Macro close-up emphasizing the crisp sound` | `微距特写强调清脆音效` |
| **提示音** | `Visual sync with a crisp "ding" sound` | `画面与清脆提示音同步` |
| **氛围音乐** | `Slow atmospheric pans matching ambient sound` | `缓慢运镜配合氛围音` |

---

## 第五部分：原生感（UGC风格）词汇包

> **2026趋势**：看起来像真实用户分享的视频，转化率远高于精修广告。

| 效果 | 英文 Prompt | 中文提示词 | 作用 |
| :--- | :--- | :--- | :--- |
| **素人演员** | `Authentic unscripted reaction, real person not actor` | `真实素人反应, 非专业演员` | 降低广告防备心 |
| **生活化场景** | `Lived-in messy background, real home not studio` | `生活化杂乱背景, 真实家庭非影棚` | 增强代入感 |
| **手持自拍感** | `Selfie POV, slightly shaky handheld` | `自拍视角, 轻微手持晃动` | 模拟真实用户拍摄 |
| **自然光线** | `Natural window light only, no studio lighting` | `仅自然窗光, 无影棚布光` | 去除广告精致感 |
| **轻微瑕疵** | `Slight imperfections visible, unretouched look` | `可见轻微瑕疵, 无后期修饰感` | 增强可信度 |
| **真实音效** | `In-camera audio, ambient room sound` | `相机原生收音, 环境音` | 避免过度配音 |

---

## 第六部分：去AI味指令（必加）

> 用于消除AI视频常见的空镜、慢动作冗余、不自然感。

| 中文提示词 | 英文提示词（推荐） |
| :--- | :--- |
| 避免缓慢的空镜移动 | `Avoid slow cinematic pans` |
| 手持真实感，拒绝稳定器感 | `Handheld POV shot, Organic unscripted feel` |
| 动作最后定格2秒在完美结果上 | `Freeze frame on the perfect result for 2 seconds` |
| 画面中心留出文字空间 | `Clear space for text overlay` |
| 避免人物脸部变形 | `No face distortion, Natural facial features` |
| 避免手指畸形 | `Well-formed hands, No extra fingers` |
| 避免物体形变 | `Stable object geometry, No warping` |
| 自然流畅的转场 | `Seamless natural transition, No morphing artifacts` |
| 避免画面闪烁 | `No flickering, Stable lighting` |
| 避免恐怖谷效应 | `Avoid uncanny valley, Natural expressions` |

---

## 第七部分：平台尾缀速查

| 平台 | 英文尾缀 | 中文提示 |
| :--- | :--- | :--- |
| **通用** | `9:16 vertical, 15 seconds loop-ready, sharp focus on product` | 9:16竖屏, 15秒循环, 产品对焦清晰 |
| **TikTok** | `Comment-worthy moment, Shareable ending, Loop transition` | 评论引导, 分享结尾, 无缝循环 |
| **YouTube Shorts** | `Search-friendly visual, Clear keyword moment` | 搜索友好视觉, 关键词可见 |
| **Meta Reels** | `Authentic real-life moment, True interest content, Value-first visual` | 真实生活瞬间, 真实兴趣内容, 价值优先 |
| **Pinterest** | `Self-explanatory visual, Bold text overlay space, Muted playback friendly` | 自解释视觉, 大号文字空间, 静音友好 |

---

## 第八部分：负面提示词避坑表

| 要避免的效果 | 负面提示词（避免使用） |
| :--- | :--- |
| 画面抖动变形 | `Warping, Morphing, Jittery animation` |
| 人物面部崩坏 | `Deformed face, Disfigured hands, Extra limbs` |
| 过多文字乱入 | `Text overlays, Watermarks, Logos in frame` |
| 慢动作拖沓 | `Slow motion, Long empty pauses, Boring static shot` |
| 低质画面 | `Low resolution, Grainy, Pixelated` |
| 不自然光照 | `Harsh shadows, Overexposed, Underexposed` |
| 恐怖谷效应 | `Uncanny valley, Creepy expression, Dead eyes` |
| 画面割裂 | `Inconsistent style, Jarring cuts` |

---

## 第九部分：品类专属五维提示词速查

### 功能效果型（清洁、美甲灯、美容仪）

| 维度 | 推荐指令 |
| :--- | :--- |
| **技术基底** | `4K UHD, 48fps, 100mm macro lens` |
| **镜头运动** | `Extreme macro shot, slow orbit` / `Slow dolly-in to close-up` |
| **视觉元素** | `[产品] transforming [效果], before-and-after visible` |
| **光影系统** | `Crisp highlights on glossy surface, rim light` |
| **动态设计** | `Visual beats sync with crisp "ding" sound` |

### 高性价比型（日用百货、服饰）

| 维度 | 推荐指令 |
| :--- | :--- |
| **技术基底** | `4K UHD, 50mm lens` |
| **镜头运动** | `Slow dolly-in to product detail` / `Match cut on hand movement` |
| **视觉元素** | `Split screen price comparison, [产品] stack of 10 items` |
| **光影系统** | `Softbox lighting, clean and bright` |
| **动态设计** | `Price pulsing large, cash register "ding" sync` |

### 情感共鸣型（礼品、护理）

| 维度 | 推荐指令 |
| :--- | :--- |
| **技术基底** | `4K UHD, 48fps, 85mm lens` |
| **镜头运动** | `Soft focus, subtle handheld breathing` |
| **视觉元素** | `Genuine tired expression shifting to content smile` |
| **光影系统** | `Warm cozy tones, natural window light` |
| **动态设计** | `Freeze frame on peaceful happy face` |

### 极简结果型（收纳、厨房工具）

| 维度 | 推荐指令 |
| :--- | :--- |
| **技术基底** | `4K UHD, 35mm wide lens` |
| **镜头运动** | `Whip pan across messy scene` / `Timelapse transition` |
| **视觉元素** | `Items magically snapping into [收纳产品], perfectly aligned` |
| **光影系统** | `Clean bright minimal lighting` |
| **动态设计** | `Smooth camera movement flowing with upbeat tempo` |
