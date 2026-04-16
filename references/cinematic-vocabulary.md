# 电影级提示词词汇表 (Cinematic Vocabulary for Seedance 2.0) v2.5

> **用途**：构建 Seedance 2.0 的高质量 Prompt。本词汇表采用 **“五维提示词架构”**，将提示词升级为结构化的导演指令，确保画面质感、运动自然、控制精准。
> **更新版本**：v2.5 (2026.04) —— 新增中英文混写示例、多模态参考素材准备指南，原生感升级为默认推荐风格。


## 第一部分：五维提示词架构

> **核心思想**：将提示词从“描述性语言”升级为结构化的“技术脚本”，从五个维度独立控制视频生成。

| 维度 | 英文指令示例 | 中文指令示例 | 混写推荐格式 |
| :--- | :--- | :--- | :--- |
| **1. 技术基底** | `4K UHD, HDR10+, 48fps, macro lens` | `4K超高清, HDR10+, 48帧, 微距镜头` | `4K UHD (超高清), 48fps (高帧率), 100mm macro lens (微距镜头)` |
| **2. 镜头运动** | `Slow dolly-in, then slight orbit` | `缓慢推近, 再轻微环绕` | `缓慢推近 (Slow dolly-in), 轻微环绕 (Slight orbit)` |
| **3. 视觉元素** | `Wet ground reflecting neon lights` | `潮湿地面反射霓虹光` | `潮湿地面 (Wet ground) 反射霓虹光 (reflecting neon lights)` |
| **4. 光影系统** | `Cool cyan key light, high contrast` | `冷青色主光, 高对比度` | `冷青色主光 (Cool cyan key light), 高对比度 (High contrast)` |
| **5. 动态设计** | `Visual beats sync with heavy bass drops` | `画面随重低音节奏轻微震动` | `画面随重低音节奏震动 (Visual beats sync with heavy bass drops)` |

> **混写优势**：Seedance 2.0 对中英文混写提示词理解效果最佳——既能捕捉中文意境，又能精准执行英文专业术语。**推荐日常使用混写格式**。


## 第二部分：多模态参考素材准备指南（新增）

> Seedance 2.0 支持上传最多 **12 个多模态参考文件**（图片/视频/音频），可大幅提升生成画面的风格一致性和动作精准度。

### 2.1 参考素材类型与用途

| 素材类型 | 用途 | 准备建议 |
| :--- | :--- | :--- |
| **风格参考图** | 锁定视频的色调、光影、质感风格 | 选择 2-3 张高质量图片，覆盖不同角度 |
| **动作参考视频** | 控制人物手势、运镜轨迹、物体运动方式 | 5-10 秒短视频，突出核心动作 |
| **产品特写图** | 确保产品外观、材质、颜色准确 | 多角度产品图，背景简洁 |
| **场景参考图** | 设定使用场景的氛围和布局 | 与产品使用场景匹配的实景图 |

### 2.2 多模态提示词模板

**使用参考图时的提示词结构**：
```
[参考图1: 风格参考] + [参考图2: 产品特写] + [五维架构文本指令]
```

**示例（美甲灯）**：
```
[Reference image 1: Clean bright product photography style, softbox lighting, minimalist aesthetic]
[Reference image 2: Rosalind nail lamp product shot, white casing, 15 LED beads visible]

4K UHD, 48fps, 100mm macro lens.
缓慢推近 (Slow dolly-in) 至甲面特写.
Nail surface transforming from matte to mirror-like gloss under the lamp.
冷青色主光 (Cool cyan key light), 高对比度 (High contrast).
Visual beats sync with crisp "ding" sound.
```

### 2.3 参考素材最佳实践

| 建议 | 说明 |
| :--- | :--- |
| **图片质量** | 分辨率 ≥1080p，清晰无噪点 |
| **风格一致性** | 多张参考图的色调、光影风格应尽量统一 |
| **动作视频时长** | 5-10 秒为宜，过长可能稀释关键动作 |
| **文件格式** | 图片：JPG/PNG；视频：MP4/MOV |


## 第三部分：标准化运镜词库

> Seedance 2.0 对以下运镜指令识别率极高，推荐使用混写格式。

### 3.1 基础运镜（混写推荐格式）

| 运镜类型 | 混写推荐格式 | 适用场景 |
| :--- | :--- | :--- |
| **推镜** | `缓慢推近 (Slow dolly-in) / 推至特写 (Push to close-up)` | 引导观众聚焦产品细节 |
| **拉镜** | `缓慢拉远 (Slow dolly-out) / 后拉至全景 (Pull back to wide shot)` | 从细节过渡到场景全貌 |
| **横摇** | `向左横摇 (Pan left) / 右摇90度 (Pan right 90°)` | 展示场景宽度或多物品 |
| **竖摇** | `向上摇镜 (Tilt up) / 向下摇镜 (Tilt down)` | 展示产品高度或垂直结构 |
| **环绕** | `轻微环绕 (Slight orbit) / 半圈环绕 (Half orbit)` | 360度展示产品外观 |
| **跟拍** | `稳定跟拍 (Steady tracking) / 侧面跟拍 (Side tracking)` | 跟随人物或物体移动 |
| **升降** | `镜头上升 (Pedestal up) / 镜头下降 (Pedestal down)` | 改变视角高度 |
| **固定机位** | `固定镜头 (Static shot) / 中景固定 (Medium static shot)` | 稳定展示，不移动 |

### 3.2 进阶运镜组合（混写推荐格式）

| 组合类型 | 混写推荐格式 | 效果描述 |
| :--- | :--- | :--- |
| **推近+环绕** | `缓慢推近同时轻微环绕 (Slow dolly-in with slight orbit)` | 产品展示经典运镜，高级感十足 |
| **拉远+横摇** | `拉远同时向右横摇 (Dolly-out while panning right)` | 从产品过渡到使用场景 |
| **跟拍+微距** | `跟拍后推至微距特写 (Tracking shot into macro close-up)` | 从人物动作聚焦到产品效果 |
| **快摇转场** | `快速摇摄转场 (Quick whip pan transition)` | 双镜头之间的动感切换 |
| **匹配动作转场** | `匹配手部动作转场 (Match cut on hand movement)` | 无缝衔接两个镜头 |

### 3.3 手持感运镜（混写推荐格式）

| 效果 | 混写推荐格式 | 适用场景 |
| :--- | :--- | :--- |
| **轻微呼吸感** | `轻微手持呼吸感 (Subtle handheld breathing)` | 增加真实感，不眩晕 |
| **第一人称POV** | `手持第一人称视角 (Handheld POV shot)` | 模拟用户视角，代入感强 |
| **自然晃动** | `生活化自然晃动 (Organic unscripted camera movement)` | **原生感UGC风格（默认推荐）** |
| **稳定为主** | `运镜丝滑几乎无晃动 (Smooth camera motion, minimal shake)` | 专业产品展示 |


## 第四部分：光影系统词汇（混写推荐格式）

### 4.1 光源类型

| 光源类型 | 混写推荐格式 | 视觉效果 |
| :--- | :--- | :--- |
| **柔光箱** | `柔光箱布光 (Softbox lighting)` | 均匀柔和，无硬阴影 |
| **自然窗光** | `自然窗光 (Natural window light)` | 生活化，温暖真实（**原生感默认推荐**） |
| **侧逆光** | `侧逆光轮廓 (Rim light contour)` | 主体边缘发光，突出立体感 |
| **伦勃朗光** | `伦勃朗光 (Rembrandt lighting)` | 戏剧感，一侧脸颊有三角形光斑 |
| **顶光** | `顶光 (Top-down lighting)` | 聚焦产品，简洁高级 |

### 4.2 光质与色调

| 效果 | 混写推荐格式 | 适用场景 |
| :--- | :--- | :--- |
| **高对比度** | `高对比度阴影 (High contrast shadows)` | 情绪张力，男性/科技产品 |
| **通透高光** | `通透的高光 (Crisp highlights)` | 反光材质（玻璃、金属、甲面） |
| **暖色调** | `暖色调温馨感 (Warm cozy tones)` | 礼品、家居、女性护理 |
| **冷色调** | `冷色调科技感 (Cool tech aesthetic)` | 3C数码、黑科技 |
| **清新明亮** | `干净明亮 (Clean and bright)` | 清洁用品、美妆、收纳 |


## 第五部分：动态设计词汇（混写推荐格式）

### 5.1 转场方式

| 转场类型 | 混写推荐格式 | 效果 |
| :--- | :--- | :--- |
| **快速摇摄** | `快速摇摄转场 (Quick whip pan transition)` | 动感快切，适合节奏型视频 |
| **匹配动作** | `匹配手部动作转场 (Match cut on hand movement)` | 无缝衔接，专业感 |
| **手部遮挡** | `手部遮挡镜头 (Hand wipes across lens)` | 自然转场，**原生感强（默认推荐）** |
| **延时摄影** | `延时摄影转场 (Timelapse transition)` | 收纳、清洁、过程展示 |

### 5.2 画面节奏

| 效果 | 混写推荐格式 | 适用场景 |
| :--- | :--- | :--- |
| **干脆利落** | `干脆利落的运镜 (Snappy motion, Quick cuts)` | 快节奏爆款视频 |
| **慢动作升格** | `慢动作升格 (Slow motion, 120fps equivalent)` | 过程微距、视觉奇观 |
| **定格** | `定格2秒 (Freeze frame for 2 seconds)` | 结尾CTA、强调结果 |

### 5.3 音频同步

| 音频类型 | 混写推荐格式 |
| :--- | :--- |
| **重低音** | `画面随重低音节奏轻微震动 (Visual beats sync with heavy bass drops)` |
| **轻快旋律** | `运镜与轻快节奏同步 (Smooth camera movement flowing with upbeat tempo)` |
| **ASMR触发** | `微距特写强调清脆音效 (Macro close-up emphasizing crisp sound)` |
| **提示音** | `画面与清脆提示音同步 (Visual sync with crisp "ding" sound)` |


## 第六部分：原生感（UGC风格）词汇包——默认推荐

> **2026 趋势**：AI 生成的 UGC 风格视频已成为广告转化率最高的形式之一。Meta 已在测试 AI 生成的 UGC 风格视频用于广告投放。**本词汇包已升级为默认推荐风格**，除非产品需要高端精修广告质感，否则优先使用以下词汇。

| 效果 | 混写推荐格式 | 作用 |
| :--- | :--- | :--- |
| **素人演员** | `真实素人反应，非专业演员 (Authentic unscripted reaction, real person not actor)` | 降低广告防备心 |
| **生活化场景** | `生活化杂乱背景，真实家庭非影棚 (Lived-in messy background, real home not studio)` | 增强代入感 |
| **手持自拍感** | `自拍视角，轻微手持晃动 (Selfie POV, slightly shaky handheld)` | 模拟真实用户拍摄 |
| **自然光线** | `仅自然窗光，无影棚布光 (Natural window light only, no studio lighting)` | 去除广告精致感 |
| **轻微瑕疵** | `可见轻微瑕疵，无后期修饰感 (Slight imperfections visible, unretouched look)` | 增强可信度 |
| **真实音效** | `相机原生收音，环境音 (In-camera audio, ambient room sound)` | 避免过度配音 |
| **生活化运镜** | `生活化自然晃动 (Organic unscripted camera movement)` | 模拟手持拍摄 |
| **手部遮挡转场** | `手部遮挡镜头转场 (Hand wipes across lens transition)` | 原生感最强的转场方式 |


## 第七部分：去AI味指令（必加，混写推荐格式）

| 中文提示词 | 混写推荐格式 |
| :--- | :--- |
| 避免缓慢的空镜移动 | `避免缓慢空镜移动 (Avoid slow cinematic pans)` |
| 手持真实感 | `手持真实感，拒绝稳定器感 (Handheld POV, Organic unscripted feel)` |
| 动作最后定格2秒 | `定格2秒 (Freeze frame for 2 seconds)` |
| 画面中心留出文字空间 | `留出文字叠加空间 (Clear space for text overlay)` |
| 避免人物脸部变形 | `无脸部变形 (No face distortion, Natural facial features)` |
| 避免手指畸形 | `手部完好无多余手指 (Well-formed hands, No extra fingers)` |
| 避免物体形变 | `物体几何稳定无形变 (Stable object geometry, No warping)` |


## 第八部分：平台尾缀速查

| 平台 | 混写推荐格式 |
| :--- | :--- |
| **通用** | `9:16竖屏 (9:16 vertical), 15秒循环 (15 seconds loop-ready), 产品对焦清晰 (sharp focus on product)` |
| **TikTok** | `评论引导时刻 (Comment-worthy moment), 分享结尾 (Shareable ending)` |
| **YouTube Shorts** | `搜索友好视觉 (Search-friendly visual), 关键词可见 (Clear keyword moment)` |
| **Meta Reels** | `真实生活瞬间 (Authentic real-life moment), 真实兴趣内容 (True interest content)` |
| **Pinterest** | `自解释视觉 (Self-explanatory visual), 大号文字空间 (Bold text overlay space), 静音友好 (Muted playback friendly)` |


## 第九部分：负面提示词避坑表

| 要避免的效果 | 负面提示词（避免使用） |
| :--- | :--- |
| 画面抖动变形 | `Warping, Morphing, Jittery animation` |
| 人物面部崩坏 | `Deformed face, Disfigured hands, Extra limbs` |
| 过多文字乱入 | `Text overlays, Watermarks, Logos in frame` |
| 慢动作拖沓 | `Slow motion, Long empty pauses` |
| 低质画面 | `Low resolution, Grainy, Pixelated` |
| 不自然光照 | `Harsh shadows, Overexposed, Underexposed` |
| 恐怖谷效应 | `Uncanny valley, Creepy expression, Dead eyes` |


## 第十部分：品类专属五维提示词速查（混写版）

### 功能效果型（清洁、美甲灯、美容仪）

| 维度 | 混写推荐指令 |
| :--- | :--- |
| **技术基底** | `4K UHD (超高清), 48fps (高帧率), 100mm macro lens (微距镜头)` |
| **镜头运动** | `极近微距环绕 (Extreme macro shot, slow orbit)` |
| **视觉元素** | `[产品] 效果转变过程，前后对比可见` |
| **光影系统** | `通透高光 (Crisp highlights), 侧逆光轮廓 (Rim light)` |
| **动态设计** | `画面与清脆提示音同步 (Visual sync with crisp "ding")` |

### 高性价比型（日用百货、服饰）

| 维度 | 混写推荐指令 |
| :--- | :--- |
| **技术基底** | `4K UHD, 50mm lens` |
| **镜头运动** | `缓慢推近至产品细节 (Slow dolly-in to product detail)` |
| **视觉元素** | `分屏价格对比 (Split screen price comparison)` |
| **光影系统** | `柔光箱布光 (Softbox lighting), 干净明亮` |
| **动态设计** | `价格跳动动画 + 收银机叮声同步` |

### 情感共鸣型（礼品、护理）

| 维度 | 混写推荐指令 |
| :--- | :--- |
| **技术基底** | `4K UHD, 85mm lens` |
| **镜头运动** | `柔焦 (Soft focus), 轻微手持呼吸感 (Subtle handheld breathing)` |
| **视觉元素** | `真实疲惫转为满足微笑 (Genuine tired to content smile)` |
| **光影系统** | `暖色调温馨感 (Warm cozy tones), 自然窗光 (Natural window light)` |
| **动态设计** | `定格于幸福面容 (Freeze frame on peaceful happy face)` |

### 极简结果型（收纳、厨房工具）

| 维度 | 混写推荐指令 |
| :--- | :--- |
| **技术基底** | `4K UHD, 35mm wide lens` |
| **镜头运动** | `快速摇摄杂乱场景 (Whip pan across messy scene)` |
| **视觉元素** | `物品自动归位至收纳产品中` |
| **光影系统** | `干净明亮极简布光 (Clean bright minimal lighting)` |
| **动态设计** | `运镜与轻快节奏同步 (Smooth camera movement flowing with upbeat tempo)` |
