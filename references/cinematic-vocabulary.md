# 电影级提示词词汇表 (Cinematic Vocabulary for Seedance 2.0) v2.0

> **用途**：构建 Seedance 2.0 的高质量 Prompt。所有词汇均经过筛选，适合 9:16 竖屏、15 秒短视频的视觉表达。
> **更新版本**：v2.0 (2026.04) —— 新增平台定制尾缀、负面提示词避坑表、Seedance 2.0 专属语法。

## 第一部分：基础电影级词汇 (通用)

### 光影与质感
- 柔光箱布光 (Softbox lighting)
- 伦勃朗光 (Rembrandt lighting)
- 通透的高光 (Crisp highlights)
- 微距细节 (Macro detail)
- 4k 超高清 (4k hyper-realistic)
- 商业产品摄影 (Commercial product photography)
- 自然窗光 (Natural window light)
- 侧逆光轮廓 (Rim light contour)
- 高对比度阴影 (High contrast shadows)

### 运镜方式
- 手持呼吸感 (Handheld breathing motion)
- 微距推拉 (Dolly zoom micro)
- 第一人称视角 (POV shot)
- 快速摇摄 (Whip pan)
- 特写聚焦 (Close-up focus pull)
- 跟随运镜 (Tracking shot)
- 升格慢动作 (Slow motion 60fps equivalent)
- 极速变焦 (Snap zoom)

### 风格基调
- 极简主义背景 (Minimalist background)
- 高饱和度色彩 (Vibrant color grading)
- 干净明亮 (Clean and bright)
- 生活化真实感 (Authentic lived-in feel)
- 暖色调温馨感 (Warm cozy tones)
- 冷色调科技感 (Cool tech aesthetic)
- 高光过曝风格 (Bright and airy overexposed look)

---

## 第二部分：爆款专属提示词强化包 (Seedance 2.0 专用)

> **指令**：在生成 Seedance 2.0 视频时，必须将以下词汇组合置于 Prompt 开头或关键位置。

### A. 爆款引流前缀 (Prompt Prefix)
*必须包含至少 2 个以上关键词，用于激活 Seedance 的高 CTR 风格模型。*

| 中文关键词 | 英文对应词 (推荐使用英文获得更好效果) | 作用 |
| :--- | :--- | :--- |
| 视觉冲击 | Visual impact, Eye-catching | 提升首帧吸引力 |
| 高质感广告大片 | High-end commercial look | 提升产品信任度 |
| 电影级微距 | Cinematic macro shot | 强化细节质感 |
| 病毒式美学 | Viral TikTok aesthetic | 对齐算法偏好 |
| 丝滑运镜 | Smooth camera motion | 提升观看流畅度 |
| 快节奏剪辑感 | Fast-paced editing feel | 提升信息密度 |
| 强迫症舒适 | Oddly satisfying | 触发留存与分享 |

**推荐组合范例**：
High CTR style, Viral TikTok ad aesthetic, Cinematic macro shot, Snappy motion, Oddly satisfying visual

### B. 去 AI 味指令 (Anti-AI Artifacts)
*用于消除 AI 视频常见的空镜、慢动作冗余、不自然感。*

| 中文提示词 | 英文提示词 (推荐) |
| :--- | :--- |
| 避免缓慢的空镜移动 | Avoid slow cinematic pans |
| 干脆利落的运镜 | Snappy motion, Quick cuts |
| 手持真实感，拒绝稳定器感 | Handheld POV shot, Organic unscripted feel |
| 动作最后定格 2 秒在完美结果上 | Freeze frame on the perfect result for 2 seconds |
| 画面中心留出文字空间 | Clear space for text overlay |
| 避免人物脸部变形 | No face distortion, Natural facial features |
| 避免手指畸形 | Well-formed hands, No extra fingers |
| 避免物体形变 | Stable object geometry, No warping |
| 自然流畅的转场 | Seamless natural transition, No morphing artifacts |

### C. 平台适配性尾缀 (Platform-Specific Suffix)
*根据目标平台选择性添加，可叠加使用。*

| 平台 | 尾缀提示词 | 目的 |
| :--- | :--- | :--- |
| **通用 (All)** | 9:16 vertical, 15 seconds loop-ready, sharp focus on product | 确保格式正确 |
| **TikTok** | Comment-worthy moment, Shareable ending, Loop transition | 激发评论与分享 |
| **YouTube Shorts** | Search-friendly visual, Clear keyword moment | 适配 SEO 搜索 |
| **Instagram Reels** | Authentic real-life moment, True interest content | 对齐 Meta 真实兴趣 |
| **Facebook Reels** | Value-first visual, Brand trust moment | 建立品牌信任 |
| **Pinterest** | Self-explanatory visual, Bold text overlay space, Muted playback friendly | 强化静音可读性 |
| **Snapchat Spotlight** | Fast-paced no-filler, Pure satisfaction loop | 提升完播率 |

### D. 负面提示词避坑表 (Negative Prompts)
*在生成 Seedance 2.0 视频时，若平台支持负面词输入，请参考以下词汇。即使平台不支持显式负向词，也应避免在正向 Prompt 中出现这些概念。*

| 要避免的效果 | 负面提示词 (避免使用) |
| :--- | :--- |
| 画面抖动变形 | Warping, Morphing, Jittery animation, Unstable footage |
| 人物面部崩坏 | Deformed face, Disfigured hands, Extra limbs, Blurry face |
| 过多文字乱入 | Text overlays, Watermarks, Logos in frame, UI elements |
| 慢动作拖沓 | Slow motion, Time-lapse, Long empty pauses, Boring static shot |
| 低质画面 | Low resolution, Grainy, Pixelated, Blurry background |
| 不自然光照 | Harsh shadows, Overexposed, Underexposed, Unnatural lighting |
| 恐怖谷效应 | Uncanny valley, Creepy expression, Dead eyes |

---

## 第三部分：Seedance 2.0 完整提示词生成器 (模板)

### 模板结构
[爆款前缀] + [主体描述] + [去 AI 味指令] + [视觉风格] + [平台尾缀]

### 英文示例 (清洁产品 - TikTok)
High CTR style, Viral TikTok ad aesthetic, Cinematic macro shot, Snappy motion, A dirty greasy kitchen stove being wiped with a white microfiber cleaning sponge, grease and stains instantly dissolve revealing shiny stainless steel surface, Handheld POV shot, Organic unscripted feel, Freeze frame on the perfectly clean stove for 2 seconds with clear space for text, Clean bright lighting, 4k hyper-realistic, 9:16 vertical, 15 seconds loop-ready, sharp focus on product, Comment-worthy moment, Shareable ending

### 英文示例 (食品 - YouTube Shorts)
Oddly satisfying visual, Cinematic macro shot, Snappy motion, A golden crispy fried chicken sandwich being cut in half, hot steam rising, melted cheese stretching slowly, crunchy breading visible, Fast-paced editing feel, No slow cinematic pans, Freeze frame on the perfect cross-section for 2 seconds, Warm cozy tones, 4k hyper-realistic, 9:16 vertical, 15 seconds loop-ready, Search-friendly visual, Clear keyword moment

### 英文示例 (美妆 - Meta Reels)
Authentic real-life moment, True interest content, Softbox lighting, A woman in her 30s applying a hydrating lip mask before bed, natural no-makeup look, genuine tired but content expression, Handheld POV shot, Organic unscripted feel, Avoid slow pans, Clean bright lighting, 4k hyper-realistic, 9:16 vertical, 15 seconds loop-ready, Value-first visual, Brand trust moment

### 中文提示词参考 (如模型支持中文输入)
高品质广告大片，电影级微距镜头，干脆利落的运镜，一只手用蓝色清洁海绵擦拭油腻的厨房灶台，污渍瞬间消失露出反光的不锈钢表面，手持第一人称视角，生活化真实感，动作最后定格在完美干净的灶台2秒，画面中心留出文字空间，干净明亮的布光，4k超高清，9:16竖屏，15秒无缝循环，产品清晰对焦

---

## 第四部分：品类专属词汇包 (按需选用)

### 清洁用品
- 污渍瞬间消失 (Stains instantly vanish)
- 一抹即净 (One wipe clean)
- 反光镜面效果 (Mirror-like reflective surface)
- 陈年油垢脱落 (Old grease peeling off)

### 美妆护肤
- 水润光泽感 (Dewy hydrated glow)
- 丝滑推开 (Silky smooth application)
- 瞬间吸收 (Instantly absorbed)
- 自然清透妆效 (Natural sheer finish)

### 食品饮料
- 热气腾腾 (Steaming hot)
- 酥脆掉渣 (Crunchy flaky crust)
- 爆浆流淌 (Oozing molten filling)
- 晶莹剔透 (Crystal clear translucent)

### 3C数码
- 金属拉丝质感 (Brushed metal texture)
- 无缝一体成型 (Seamless unibody design)
- 极简工业美学 (Minimalist industrial aesthetic)
- 纤薄轻盈 (Ultra-thin lightweight)

### 服饰配饰
- 面料垂坠感 (Fabric drape and flow)
- 精致车线细节 (Precise stitching detail)
- 上身立体剪裁 (Tailored fitted silhouette)
- 高级质感 (Luxurious texture)

---

## 第五部分：提示词迭代优化记录表 (内部使用)

| 日期 | 产品品类 | 使用的核心提示词组 | 生成效果评估 | 优化建议 |
| :--- | :--- | :--- | :--- | :--- |
| 2026.04.15 | 清洁用品 | High CTR + Cinematic macro + Handheld POV | 画面冲击力强，完播率高 | 维持 |
| (示例) | 食品 | Oddly satisfying + 慢动作切割 | 画面略拖沓，前3秒信息密度不足 | 减少慢动作，增加快切 |
| | | | | |
