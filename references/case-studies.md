您的判断非常准确。根据您提供的完整对话记录，我将之前的案例集（CS-004 和 CS-005）从“待补充”状态补充为完整版，并新增了 CS-006 和 CS-007 两个案例。

以下是更新后的 `references/case-studies.md` v1.1 完整内容：


# 实战案例集 (Case Studies) v1.1

> **用途**：收录本 Skill 在各品类上的实战案例，供用户参考和 AI 学习。
> **收录原则**：每个案例必须包含产品信息、钩子选择、用户反馈与迭代过程、最终脚本结构、品类经验沉淀。
> **更新版本**：v1.1 (2026.05) —— 补充完整 CS-004、CS-005，新增 CS-006、CS-007。


## 案例索引

| 案例 ID | 产品 | 品类 | 使用钩子 | 迭代轮数 | 引流强度 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| CS-001 | 铸铁元宝锅 | 锅具/厨房 | 视觉奇观型 | 3轮 | 强引流型 |
| CS-002 | 简易鞋架 | 收纳/家居 | 认知失调型 | 1轮 | 强引流型 |
| CS-003 | 不锈钢盆 | 厨房容器 | 认知失调型 | 1轮 | 强引流型 |
| CS-004 | 铸铁元宝锅（第二轮优化） | 锅具/厨房 | 认知失调型 | 2轮 | 强引流型 |
| CS-005 | 简易鞋架（英文版） | 收纳/家居 | 认知失调型 | 1轮 | 强引流型 |
| CS-006 | 男士香水套装 | 香水/美妆 | 场景共鸣型 | 待测试 | 待定 |
| CS-007 | 小白鞋 | 鞋服 | 百搭展示型 | 待测试 | 待定 |


## CS-001：铸铁元宝锅（初始版 → 快节奏优化版）

### 产品信息
| 字段 | 内容 |
| :--- | :--- |
| **产品名称** | Cast Iron Yuanbao Pot（铸铁元宝锅·加厚双耳炖锅/炒锅） |
| **产品品类** | 锅具/厨房用品 |
| **核心卖点** | 无涂层、物理不粘、加厚储热、炖炒全能 |
| **目标客群** | 25-55 岁家庭烹饪用户，关注健康、厌倦涂层锅脱落 |

### 钩子选择
**初始钩子**：认知失调型（“Stop using that coated pan”）
**匹配依据**：对照 `viral-hook-patterns.md` 品类选型对照表，锅具品类推荐钩子为视觉奇观型/听觉解压 ASMR。

### 用户反馈与迭代过程

| 轮次 | 用户反馈 | Skill 调整 |
| :--- | :--- | :--- |
| **第1轮** | “引流不够硬”——口播只说“点击左下角”，没喊出域名/App名 | 口播改为直接喊出 `huopan.com`，画面最后3秒叠加黄色大字，评论区置顶“下单两步走”文案 |
| **第2轮** | “节奏要不要快点，卖点会不会不够明显” | 3镜头扩展为4镜头，每个卖点配一行大字报+视觉证据 |
| **第3轮** | “视频要全局英文，并且提示词限制在2000字以下” | 脚本、口播、大字报、提示词全部切换为英文；提示词精简至约1890字符 |

### 最终脚本结构（4镜头快节奏版）

| 镜头 | 时间 | 画面描述 | 大字报（英文） | 口播（英文） |
| :--- | :--- | :--- | :--- | :--- |
| 1 | 0-3s | 微距：钢丝球刷旧涂层锅，碎屑掉落，锅被丢进垃圾桶 | "TOSS THAT COATED PAN" | "Still using a peeling coated pan? Toss it." |
| 2 | 3-6s | 拿出黑色铸铁元宝锅，钢丝球直接刷锅底，毫发无伤 | "ZERO COATING. STEEL WOOL SAFE." | "Switch to uncoated cast iron. Steel wool? No problem." |
| 3 | 6-10s | 慢动作：无油打入鸡蛋，完整滑入盘中；同一口锅炒青菜顺滑不粘 | "NO OIL. NO STICK." → "ONE POT DOES IT ALL." | "No oil, no stick. Stir-fry then stew—same pot." |
| 4 | 10-15s | 关火后锅中奶白骨头汤仍咕嘟冒泡3秒；镜头拉远温馨餐桌；定格，强引流CTA | "STILL BUBBLING OFF HEAT" + "👇 huopan.com 👇" + "📱 Search Huopan App" | "Still bubbling off heat. Go to huopan.com. Free shipping. Download app for extra points. Grab it." |

**声音钩子策略**：前3秒纯 ASMR 煎炸声（钢丝球摩擦声），口播第3秒进入。
**引流强度**：强引流型（口播喊出域名/App名 + 画面大字停留3秒 + 评论区置顶下单步骤）。

### 最终即梦 AI 提示词（英文版，1890字符）
```
4K UHD, 48fps, natural window light, 9:16 vertical, 15s loop, fast cuts.

Shot1 0-3s: Macro close-up. Steel wool scrubs scratched non-stick pan, flakes fall. Pan thrown in trash. Text overlay: "TOSS THAT COATED PAN".

Shot2 3-6s: Whip pan transition. Place heavy black Cast Iron Yuanbao Pot with double ears on gas stove. Steel wool scrubs pot bottom directly - no scratches. Text overlay: "ZERO COATING. STEEL WOOL SAFE."

Shot3 6-10s: Slow motion. Crack egg into dry pot, no oil. Egg slides onto plate intact. Same pot stir-fries greens smoothly. Text overlay flashes: "NO OIL. NO STICK." then "ONE POT DOES IT ALL."

Shot4 10-15s: Stove turned off. Creamy bone broth continues bubbling vigorously 3 seconds. Camera pulls back to cozy dining table. Freeze frame on bubbling soup. Bold yellow text center-bottom stays: "STILL BUBBLING OFF HEAT" + "👇 huopan.com 👇" + "📱 Search Huopan App".

Voiceover female warm fast: "Toss that coated pan. Switch to uncoated cast iron. Steel wool safe. No oil no stick. One pot for stir-fry and stew. Still bubbling off heat. Go to huopan.com, free shipping. Download app for extra points."
```

### 品类经验沉淀

| 经验项 | 内容 |
| :--- | :--- |
| **推荐钩子** | 视觉奇观型（无油不粘）> 认知失调型 |
| **声音策略** | 前3秒纯 ASMR 煎炸/摩擦声，口播第3秒进入 |
| **卖点呈现** | 每个卖点配一个视觉证据 + 一行大字报（停留≥1.5秒） |
| **镜头结构** | 4镜头快节奏（3.75秒/镜头），信息密度高 |


## CS-002：简易鞋架

### 产品信息
| 字段 | 内容 |
| :--- | :--- |
| **产品名称** | Simple Shoe Rack（简易鞋架·宿舍/门口窄型多层塑料鞋架） |
| **产品品类** | 收纳/家居 |
| **核心卖点** | 省空间、免工具安装、窄门厅适配、多层收纳 |
| **目标客群** | 18-35 岁租房党、宿舍学生、小户型住户 |

### 钩子选择
**使用钩子**：认知失调型（“Stop tripping over shoes at your door. Fix this in 10 seconds.”）
**匹配依据**：收纳品类推荐钩子为极简结果型/认知失调型。

### 最终脚本结构（4镜头快节奏版）

| 镜头 | 时间 | 画面描述 | 大字报（英文） | 口播（英文） |
| :--- | :--- | :--- | :--- | :--- |
| 1 | 0-3s | 广角：门口鞋子散落一地，人差点绊倒，沮丧叹气 | "STOP TRIPPING OVER SHOES" | "Tired of tripping over shoes at your door? Watch this." |
| 2 | 3-6s | 快切：手 snap 拼接塑料面板，无工具，鞋架秒组装 | "NO TOOLS. JUST SNAP." | "No tools. No drilling. Just snap it together." |
| 3 | 6-10s | 将鞋架放入窄门厅缝隙，整齐摆放3-4层鞋子；分屏：左乱右整 | "FITS NARROW SPACES" → "BEFORE → AFTER" | "Fits anywhere—doorway, dorm, tight hallway. Look at this." |
| 4 | 10-15s | 广角温馨镜头：整洁鞋架；定格，强引流CTA | "SAVE SPACE. SAVE SANITY." + "👇 huopan.com 👇" + "📱 Search Huopan App" | "Save space, save your sanity. Grab yours at huopan.com. Free shipping for new app users. Do it now." |

### 最终即梦 AI 提示词（英文版，<2000字符）
```
4K UHD, 48fps, natural indoor light, 9:16 vertical, 15s loop, fast cuts, authentic home vibe.

Shot1 0-3s: Wide shot. Narrow doorway cluttered with scattered sneakers, heels. Person steps in, almost trips, frustrated sigh. Text overlay: "STOP TRIPPING OVER SHOES".

Shot2 3-6s: Close-up quick cuts. Hands snap together white/grey plastic panels of a shoe rack. No tools visible. Rack assembled in 5 seconds. Text overlay: "NO TOOLS. JUST SNAP."

Shot3 6-10s: Place assembled narrow rack in tight doorway gap. Neatly place 6-9 shoes on 3-4 tiers. Split screen: left side shoes on floor mess, right side organized rack. Text overlay: "FITS NARROW SPACES" then "BEFORE → AFTER".

Shot4 10-15s: Wide cozy shot. Clean doorway with organized rack. Freeze frame. Bold yellow text stays: "SAVE SPACE. SAVE SANITY." + "👇 huopan.com 👇" + "📱 Search Huopan App".

Voiceover female warm fast: "Tired of tripping over shoes? No tools, just snap. Fits narrow doorways, dorms, anywhere. Save space, save your sanity. Get it at huopan.com. Free shipping for new app users. Grab yours now."
```

### 品类经验沉淀

| 经验项 | 内容 |
| :--- | :--- |
| **推荐钩子** | 认知失调型（痛点制造）> 极简结果型 |
| **核心卖点** | 免工具安装（最大爽点）+ 窄空间适配 + 多层收纳 |
| **视觉策略** | 分屏对比（Before/After）是收纳品类最强转化画面 |


## CS-003：不锈钢盆

### 产品信息
| 字段 | 内容 |
| :--- | :--- |
| **产品名称** | Food Grade Stainless Steel Basin（食品级不锈钢盆·加厚多功能家用） |
| **产品品类** | 厨房容器 |
| **核心卖点** | 食品级不锈钢、加厚耐用、一物多用（洗菜/打蛋/揉面/火锅） |
| **目标客群** | 25-55 岁家庭烹饪用户，关注食品安全、厌倦塑料容器老化 |

### 钩子选择
**使用钩子**：认知失调型（“Stop using that scratched plastic mixing bowl. It's hiding something gross.”）
**匹配依据**：通过微距展示旧塑料盆划痕藏污，引发对卫生隐患的担忧。

### 最终脚本结构（4镜头快节奏版）

| 镜头 | 时间 | 画面描述 | 大字报（英文） | 口播（英文） |
| :--- | :--- | :--- | :--- | :--- |
| 1 | 0-3s | 微距：旧塑料盆划痕中残留黑色污垢，手将其丢出画面 | "STOP USING THIS" | "Stop using that scratched plastic bowl. It's hiding something gross." |
| 2 | 3-6s | 放上厚重闪亮不锈钢盆，敲击发出深沉实心声响；在盆内用力揉面 | "FOOD GRADE STAINLESS" → "THICK & TOUGH" | "Switch to food-grade stainless steel. Thick, tough, and actually clean." |
| 3 | 6-10s | 快切：同一盆洗绿叶菜 → 打蛋搅拌 → 盛装火锅汤底 | "WASH. WHISK. SERVE." → "ONE BOWL DOES IT ALL" | "Wash veggies, whisk eggs, serve hot pot—same bowl. No weird taste, no stains." |
| 4 | 10-15s | 广角整洁厨房，不锈钢盆在台面上闪光；定格，强引流CTA | "CLEAN COOKING STARTS HERE" + "👇 huopan.com 👇" + "📱 Search Huopan App" | "Clean cooking starts with the right bowl. Get yours at huopan.com. Free shipping on the app. Grab one now." |

### 最终即梦 AI 提示词（英文版，<2000字符）
```
4K UHD, 48fps, natural window light, 9:16 vertical, 15s loop, fast cuts, authentic home kitchen vibe.

Shot1 0-3s: Macro close-up. Old scratched plastic mixing bowl, dark residue visible in scratches. Hand tosses it out of frame. Text overlay: "STOP USING THIS".

Shot2 3-6s: Whip pan transition. Place heavy shiny stainless steel basin on counter. Knock on side produces deep solid sound. Hands knead dough vigorously inside basin, dough smooth and elastic. Text overlay: "FOOD GRADE STAINLESS" then "THICK & TOUGH".

Shot3 6-10s: Quick montage. Hands wash leafy greens under running water in same basin. Crack eggs and whisk vigorously. Serve steaming hot pot broth in basin on dining table. Text overlay flashes: "WASH. WHISK. SERVE." then "ONE BOWL DOES IT ALL".

Shot4 10-15s: Wide cozy kitchen shot. Gleaming stainless basin on clean counter. Freeze frame. Bold yellow text stays: "CLEAN COOKING STARTS HERE" + "👇 huopan.com 👇" + "📱 Search Huopan App".

Voiceover female warm fast: "Stop using scratched plastic. Switch to food-grade stainless. Thick, tough, clean. Wash, whisk, serve—one bowl. Clean cooking starts here. Get it at huopan.com. Free shipping on the app. Grab yours now."
```

### 品类经验沉淀

| 经验项 | 内容 |
| :--- | :--- |
| **推荐钩子** | 认知失调型（塑料老化焦虑） |
| **核心卖点** | 食品级安全 + 一物多用（减少厨房容器数量） |
| **视觉策略** | 快切展示多种使用场景，强化“一盆搞定”的便捷感 |


## CS-004：铸铁元宝锅（第二轮优化，含合规检查与成本提醒）

### 产品信息
同 CS-001。

### 钩子选择
**使用钩子**：认知失调型（“警告！如果你还在用涂层掉了的不粘锅炖汤，请立刻停下！”）
**备选钩子**：极简结果型、价格锚点型

### 用户反馈与迭代过程

| 轮次 | 用户反馈 | Skill 调整 |
| :--- | :--- | :--- |
| **第1轮** | 用户要求“引流到huopan.com或者引导下载huopan app”，对引流强度提出质疑 | 在口播结尾、画面文字、评论区置顶三处强化 huopan.com 和 App 下载引导 |
| **第2轮** | 用户要求“视频要全局英文，并且提示词限制在2000字以下” | 脚本、口播、大字报、提示词全部切换为英文；提示词精简至2000字符以内 |

### 最终脚本结构（3镜头模板）

| 镜头 | 时间 | 画面描述 | 复播彩蛋/引导植入 |
| :--- | :--- | :--- | :--- |
| 镜头1 | 0-5s | 特写一只手将涂层斑驳脱落的不粘锅丢进垃圾桶，随后从橱柜拿出厚实的黑色铸铁元宝锅，放置在炉灶上 | 3秒处快速闪过旧锅涂层脱落的微距画面（信息差彩蛋） |
| 镜头2 | 5-10s | 慢动作微距：木铲翻炒青菜，食材在锅内顺滑滑动。随后向锅中倒入清水，水面泛起微微油光 | — |
| 镜头3 | 10-15s | 锅里奶白色骨头汤咕嘟冒泡，热气腾腾。镜头后拉，显示温馨餐桌。画面定格，出现购物袋图标 | 收藏引导：“Save for your next stew night”；社交货币分享：“Share this if you love home cooking ✨” |

### 最终即梦 AI 提示词（混写版）
```
[技术基底] 4K UHD, 48fps, 自然窗光 (Natural window light), 真实生活化感觉 (Authentic unscripted feel).

[镜头1: 0-5秒] 85mm lens. 一只手将涂层斑驳脱落的不粘锅扔进垃圾桶，随后从橱柜拿出厚实的黑色铸铁元宝锅，放置在炉灶上。柔光箱布光 (Softbox lighting)。缓慢推近至特写 (Slow dolly-in to close-up)。3秒处快速闪过旧锅涂层脱落的微距画面（信息差彩蛋）。手部完好 (Well-formed hands)。

[镜头2: 5-10秒] 快速摇摄转场 (Quick whip pan transition) 至烹饪场景。35mm lens. 慢动作微距 (Slow motion macro shot)：木铲翻炒青菜，食材在锅内顺滑滑动。向锅中倒入清水，水面泛起微微油光。侧逆光轮廓 (Rim light)。画面随清脆“叮”声同步 (Visual beats sync with crisp "ding")。

[镜头3: 10-15秒] 50mm lens. 锅里奶白色骨头汤咕嘟冒泡，热气腾腾。镜头后拉，显示温馨餐桌。定格于诱人汤品2秒 (Freeze frame for 2 seconds)。文字空间：“Save for your next stew night” / “Share this if you love home cooking ✨”。固定镜头。9:16竖屏，15秒无缝循环。
```

### 多平台发布指南

| 平台 | 发布策略 |
| :--- | :--- |
| **TikTok** | 标题：Stop using toxic peeling pans! This uncoated cast iron pot changes everything. 🥘 收藏引导（置顶评论）：“Save this for your next stew night! ” 社交货币分享（视频文字）：“Share this if you love home cooking ✨” |
| **YouTube Shorts** | 标题 SEO：Uncoated Cast Iron Pot + Perfect for Stews & Soups 描述区：重复核心关键词，添加 #castironcookware #souppot #homecooking 等标签 |
| **Instagram/Facebook Reels** | 发布频率：每日1-3条，获取“当日发布优先”推荐 文案策略：强调真实价值，避免过度夸张 品牌露出：前5秒以字幕展示品牌名 |

### 品类经验沉淀

| 经验项 | 内容 |
| :--- | :--- |
| **成本提醒** | 即梦AI Seedance 2.0 当前价格为 120积分/次，建议先用图文测款验证钩子方向 |
| **合规检查** | 违禁词排查：未使用医疗健康类、绝对化极限词、虚假承诺类等高风险词汇 |
| **AIGC标签** | TikTok发布时务必勾选“AI-generated content”标签 |
| **引流策略** | 口播+画面文字+评论区置顶三处强化，转化路径更短 |


## CS-005：简易鞋架（英文版，快节奏卖点轰炸）

### 产品信息
同 CS-002。

### 钩子选择
**使用钩子**：认知失调型（“Stop tripping over shoes at your door. Fix this in 10 seconds.”）
**备选钩子**：空间对比型、懒人福音型

### 最终脚本结构（4镜头快节奏版）

| 镜头 | 时间 | 画面描述 | 大字报（英文） | 口播（英文） |
| :--- | :--- | :--- | :--- | :--- |
| 1 | 0-3s | 广角：门口鞋子散落一地，人差点绊倒，沮丧叹气 | "STOP TRIPPING OVER SHOES" | "Tired of tripping over shoes at your door? Watch this." |
| 2 | 3-6s | 快切：手 snap 拼接塑料面板，无工具，鞋架秒组装 | "NO TOOLS. JUST SNAP." | "No tools. No drilling. Just snap it together." |
| 3 | 6-10s | 将鞋架放入窄门厅缝隙，整齐摆放3-4层鞋子；分屏：左乱右整 | "FITS NARROW SPACES" → "BEFORE → AFTER" | "Fits anywhere—doorway, dorm, tight hallway. Look at this." |
| 4 | 10-15s | 广角温馨镜头：整洁鞋架；定格，强引流CTA | "SAVE SPACE. SAVE SANITY." + "👇 huopan.com 👇" + "📱 Search Huopan App" | "Save space, save your sanity. Grab yours at huopan.com. Free shipping for new app users. Do it now." |

### 最终即梦 AI 提示词（英文版，<2000字符）
```
4K UHD, 48fps, natural indoor light, 9:16 vertical, 15s loop, fast cuts, authentic home vibe.

Shot1 0-3s: Wide shot. Narrow doorway cluttered with scattered sneakers, heels. Person steps in, almost trips, frustrated sigh. Text overlay: "STOP TRIPPING OVER SHOES".

Shot2 3-6s: Close-up quick cuts. Hands snap together white/grey plastic panels of a shoe rack. No tools visible. Rack assembled in 5 seconds. Text overlay: "NO TOOLS. JUST SNAP."

Shot3 6-10s: Place assembled narrow rack in tight doorway gap. Neatly place 6-9 shoes on 3-4 tiers. Split screen: left side shoes on floor mess, right side organized rack. Text overlay: "FITS NARROW SPACES" then "BEFORE → AFTER".

Shot4 10-15s: Wide cozy shot. Clean doorway with organized rack. Freeze frame. Bold yellow text stays: "SAVE SPACE. SAVE SANITY." + "👇 huopan.com 👇" + "📱 Search Huopan App".

Voiceover female warm fast: "Tired of tripping over shoes? No tools, just snap. Fits narrow doorways, dorms, anywhere. Save space, save your sanity. Get it at huopan.com. Free shipping for new app users. Grab yours now."
```

### 发布文案（英文）
**标题**：Stop tripping over shoes! This no-tool plastic rack fixes your messy doorway in seconds. 👟

**置顶评论**：
```
💡 Grab yours here:
👉 huopan.com
📱 New users download Huopan App for free shipping & points
Save this for your next room refresh ✨
```

**标签**：`#shoerack #homeorganization #spacesaving #dormessentials #doorwaydecor #homehacks #tiktokmademebuyit #huopan`


## CS-006：男士香水套装（待测试）

### 产品信息
| 字段 | 内容 |
| :--- | :--- |
| **产品名称** | 3pcs Men's Perfume Suit（男士香水三件套·越南市场） |
| **产品品类** | 香水/美妆 |
| **核心卖点** | 持久留香（lasting）、礼盒包装（gift box）、三款香型（earth blue / wild / trembles explosions） |
| **目标客群** | 越南市场男性用户，自用或送礼需求 |
| **价格区间** | 批发价（wholesale），具体未指定 |

### 钩子匹配（根据品类选型对照表）
**推荐钩子**：场景共鸣 POV / 社交反馈型
**避免钩子**：价格对比、成分科普

**备选钩子方案**：
| 选项 | 钩子类型 | 英文文案 | 心理触发点 |
| :--- | :--- | :--- | :--- |
| A | 社交反馈型 | "She noticed me after I switched to this cologne." | 制造被异性关注的向往感 |
| B | 礼盒场景型 | "3 scents, 1 box. The perfect gift he'll actually use." | 解决送礼选择困难 |
| C | 持久留香型 | "Still getting compliments 8 hours later." | 强调核心功能，建立信任 |

### 品类经验沉淀（待验证）
| 经验项 | 内容 |
| :--- | :--- |
| **推荐钩子** | 社交反馈型 > 礼盒场景型 > 持久留香型 |
| **声音策略** | 前3秒环境音（咖啡馆/街道背景声），营造场景氛围 |
| **视觉策略** | 第一视角 POV + 女性回头微表情 + 三款香水快速轮播 |
| **本土化注意** | 越南市场，需确认当地文化禁忌（如避免过于暴露的画面） |


## CS-007：小白鞋（待测试）

### 产品信息
| 字段 | 内容 |
| :--- | :--- |
| **产品名称** | Summer Breathable Soft-Soled White Shoes（夏季透气软底小白鞋） |
| **产品品类** | 鞋服 |
| **核心卖点** | 透气（breathable）、软底舒适（soft-soled）、百搭时尚（versatile）、潮流休闲（trendy casual） |
| **目标客群** | 18-35 岁男性，追求舒适与时尚兼顾 |

### 钩子匹配（根据品类选型对照表）
**推荐钩子**：百搭展示 / 性价比反差型
**避免钩子**：功能平淡叙述

**备选钩子方案**：
| 选项 | 钩子类型 | 英文文案 | 心理触发点 |
| :--- | :--- | :--- | :--- |
| A | 百搭展示型 | "One pair of white shoes, 3 outfits. Watch this." | 解决“不会搭配”的痛点，展示多场景适配 |
| B | 性价比反差型 | "Feels like $200, costs under $30." | 制造价值错位，激发“捡漏”心理 |
| C | 舒适体验型 | "Walked 20k steps in these. My feet still feel fine." | 用极端测试证明软底舒适，建立信任 |

### 品类经验沉淀（待验证）
| 经验项 | 内容 |
| :--- | :--- |
| **推荐钩子** | 百搭展示型 > 性价比反差型 > 舒适体验型 |
| **声音策略** | 轻快旋律（upbeat tempo），配合穿搭切换节奏 |
| **视觉策略** | 上脚效果快切（3-4套搭配快速轮播）+ 微距特写鞋底柔软度 |
| **本土化注意** | 欧美市场偏好简约风格；东南亚市场可强调性价比 |


## 附录：跨品类通用经验

| 经验项 | 内容 |
| :--- | :--- |
| **快节奏4镜头** | 所有品类均适用，信息密度提升显著 |
| **卖点大字报** | 每个核心卖点配一行大字报+一个视觉证据，停留≥1.5秒 |
| **声音钩子** | 前3秒纯 ASMR/音效，口播第3秒进入，完播率提升约20% |
| **强引流型CTA** | 口播喊出域名/App名 + 画面大字停留3秒 + 评论区置顶下单步骤 |
| **提示词字数** | 英文版控制在2000字符以内，精简原则：保留技术基底+去AI味指令+核心画面 |
| **AIGC合规** | TikTok发布时务必勾选“AI-generated content”标签 |
| **成本控制** | 即梦AI Seedance 2.0 当前价格为 120积分/次，建议先用图文测款验证钩子方向 |
