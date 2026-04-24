# 核心知识库 (Core Knowledge) v3.0

> **用途**：本文件是 `SKILL.md` 的深度扩展库，提供完整的Hook变体库、电影级词汇表、平台算法详细规则、评估校准方法论及多语言本土化策略。
> **与 SKILL.md 的关系**：SKILL.md 包含日常生成所需的全部核心规则和速查表。本文件提供更深入、更详细的知识，供深度学习、系统优化和出海场景使用。
> **合并自**：原 `references/` 目录下 11 个文件的核心内容。
> **版本**：v3.0 (2026.05)


## 一、完整Hook体系（30+ 变体）

### 1.1 认知失调型（7 变体）

| # | 英文模板 | 适用场景 |
| :--- | :--- | :--- |
| 1 | "Stop using that. This is what you need." | 通用，简洁有力 |
| 2 | "Your [旧方法] is lying to you." | 制造不信任，激发好奇 |
| 3 | "There's no way this works... wait." | 自我怀疑 + 反转预留 |
| 4 | "I thought this was a gimmick. I was wrong." | 第一人称真实体验 |
| 5 | "They don't want you to know this hack." | 信息差独占，增强点击欲 |
| 6 | "If you're still [旧行为], you're missing out." | FOMO 驱动 |
| 7 | "This feels illegal to know." | 夸张悬念，高点击率 |

### 1.2 视觉奇观型（7 变体）

| # | 英文模板 | 适用场景 |
| :--- | :--- | :--- |
| 1 | "Watch what happens when I crack this egg." | 引导观众见证奇观 |
| 2 | "No oil. No butter. Just slide." | 极简结果展示 |
| 3 | "I've never seen a pan do this." | 第一人称惊讶反应 |
| 4 | "This is what a $30 pan can do." | 价格+效果双重锚点 |
| 5 | "Sound on for the most satisfying slide." | 引导开启声音，强化 ASMR |
| 6 | "My old pan could never." | 对比型，唤起旧痛点 |
| 7 | "The way this just... glides." | 省略句式，制造悬念 |

### 1.3 故事型 Mystery Object（7 变体）

| # | 英文模板 | 适用场景 |
| :--- | :--- | :--- |
| 1 | "My mom sent me this from [country]. I had no idea what it was." | 进口产品、异域感 |
| 2 | "Found this at a flea market. Changed how I cook." | 小众发现、惊喜感 |
| 3 | "I bought this from a random link. Still don't know the name." | 真实网购体验 |
| 4 | "This came in a box with no instructions." | 天然悬念设置 |
| 5 | "My roommate said this thing is useless. Watch this." | 冲突+反转预留 |
| 6 | "Everyone asks me what this is. Here's the answer." | 社交证明前置 |
| 7 | "I've been gatekeeping this for months." | 信息差独占，高好奇心 |

### 1.4 其他Hook变体简表

| Hook类型 | 变体数 | 示例 |
| :--- | :--- | :--- |
| **极简结果型** | 6 | "3 seconds to organized." / "Watch this mess disappear." |
| **价格锚点型** | 6 | "Don't pay $200 for this." / "I found a $12 version." |
| **情感绑架型** | 5 | "The gift she actually wanted." / "Self-care looks like this." |
| **身份认同型** | 5 | "Renters, this is for you." / "Small apartment life saver." |

### 1.5 Hook组合策略

| 组合类型 | 说明 | 示例 |
| :--- | :--- | :--- |
| **纵向叠加** | 同一视频中先后使用两个Hook | 前3秒视觉奇观 + 第5秒价格锚点 |
| **横向并行** | 不同变体分别测试，数据择优 | 变体1 vs 变体2，48h 后看完播率 |
| **趋势绑定** | Hook文案融入当前热门话题 | "This is how I survive inflation cooking" |


## 二、电影级词汇库

### 2.1 Seedance 2.0 官方 6 步公式

**主体/角色 → 动作/剧情 → 环境/场景 → 镜头/运镜 → 风格/氛围 → 约束/避坑**

### 2.2 最佳长度建议

| 长度范围 | 适用场景 | 说明 |
| :--- | :--- | :--- |
| **30-60 词** | 直给型单镜头（推荐） | 精准落入模型最佳注意力窗口 |
| **60-100 词** | 直给型单镜头（稳妥上限） | 官方推荐区间 |
| **100-150 词** | 复杂场景单镜头 | 需结构化分段 |
| **150+ 词** | 严禁单次输入 | 必须拆分为原子化分段指令 |

### 2.3 标准化运镜词库

**基础运镜（识别精度 ⭐⭐⭐⭐⭐）**：

| 运镜类型 | 混写推荐格式 | 适用场景 |
| :--- | :--- | :--- |
| **推镜** | `缓慢推近 (Slow dolly-in)` / `推至特写 (Push to close-up)` | 聚焦产品细节 |
| **拉镜** | `缓慢拉远 (Slow dolly-out)` / `后拉至全景 (Pull back to wide shot)` | 从细节过渡到全貌 |
| **环绕** | `轻微环绕 (Slight orbit)` / `半圈环绕 (Half orbit)` | 360度展示产品 |
| **跟拍** | `稳定跟拍 (Steady tracking shot)` | 跟随人物或物体 |
| **固定机位** | `固定镜头 (Static shot)` | 稳定展示 |

**进阶运镜组合（仅推荐 Standard 模式）**：

| 组合类型 | 混写推荐格式 | 效果 |
| :--- | :--- | :--- |
| **推近+环绕** | `缓慢推近同时轻微环绕 (Slow dolly-in with slight orbit)` | 产品展示经典运镜 |
| **快摇转场** | `快速摇摄转场 (Quick whip pan transition)` | 镜头间动感切换 |
| **匹配动作转场** | `匹配手部动作转场 (Match cut on hand movement)` | 无缝衔接 |

**手持感运镜（原生感核心）**：

| 效果 | 混写推荐格式 | 适用场景 |
| :--- | :--- | :--- |
| **第一人称POV** | `手持第一人称视角 (Handheld POV shot)` | 模拟用户视角 |
| **自然晃动** | `生活化自然晃动 (Organic unscripted camera movement)` | 原生感UGC风格（默认） |
| **稳定为主** | `运镜丝滑几乎无晃动 (Smooth camera motion, minimal shake)` | 专业产品展示 |

### 2.4 光影系统词汇

| 光源类型 | 混写推荐格式 | 视觉效果 |
| :--- | :--- | :--- |
| **柔光箱** | `柔光箱布光 (Softbox lighting)` | 均匀柔和，无硬阴影 |
| **自然窗光** | `自然窗光 (Natural window light)` | 生活化，温暖真实（原生感默认） |
| **侧逆光** | `侧逆光轮廓 (Rim light contour)` | 主体边缘发光，立体感 |

### 2.5 正/负向词完整对照表

| 想要的效果 | ✅ 使用（正向锚点词） | ❌ 禁止（否定式负向词·严格禁用） |
| :--- | :--- | :--- |
| **手部完好** | `Well-formed hands`, `Natural hand pose` | ~~`No extra fingers`~~ |
| **面部自然** | `Natural facial features`, `Lifelike face` | ~~`No face distortion`~~ |
| **物体几何稳定** | `Stable object geometry`, `Solid shape` | ~~`No warping`~~ |
| **画面清晰锐利** | `Crystal-clear`, `Tack-sharp` | ~~`No blur`~~ |
| **运动稳定** | `Steady motion`, `Smooth camera movement` | ~~`No jitter`~~ |
| **无AI感** | `Organic unscripted feel`, `Authentic lived-in look` | ~~`No AI artifacts`~~ |


## 三、平台算法与分发策略

### 3.1 各平台算法核心信号

| 平台 | 2026 核心信号 | 权重排序 |
| :--- | :--- | :--- |
| **TikTok** | 完播率 > 收藏 = 分享 > 评论 > 点赞 | 小批量测试200-500人，垂直领域强化 |
| **YouTube Shorts** | 划走率（负向）+ 重播率 + 关键词搜索 | 划走率是最关键负向指标 |
| **IG/FB Reels** | 有效完播 + 真实兴趣 (UTIS) + 当日发布优先 | 当日发布占50%+推荐 |
| **Threads** | Reps互通加权 + 文本互动（回复/引用） | 纯视频无文案会被限流 |
| **Lemon8** | 种草意图匹配 + 收藏权重极高 | 标题关键词优化至关重要 |
| **Pinterest** | 视觉自解释力 + 保存率 + 多格式加权 | 静音浏览占90% |
| **Snapchat** | 完播率 + 重播率 + 分享 | 年轻化快节奏 |

### 3.2 最佳发布时间窗口（美东时间）

| 平台 | 最佳发布时间 | 次优时段 | 避免时段 |
| :--- | :--- | :--- | :--- |
| TikTok | 晚 7:00-10:00 | 午 12:00-2:00 | 凌晨 1:00-6:00 |
| YouTube Shorts | 早 8:00-10:00 / 晚 6:00-9:00 | 午 11:00-1:00 | 凌晨 2:00-5:00 |
| IG/FB Reels | 晚 8:00-10:00 | 午 11:00-1:00 | 凌晨 1:00-5:00 |
| Pinterest | 晚 8:00-11:00 | 周六日上午 | 工作日早 6:00-9:00 |
| Lemon8 | 午 12:00-2:00 / 晚 7:00-9:00 | 下午 4:00-6:00 | 凌晨 1:00-6:00 |
| Snapchat | 下午 3:00-5:00 | 晚 8:00-10:00 | 早 6:00-10:00 |

### 3.3 AIGC 标签合规汇总

| 平台 | 标签名称 | 是否强制 | 违规后果 |
| :--- | :--- | :--- | :--- |
| TikTok | AI-generated content | ✅ 强制 | 限流或下架 |
| Meta (IG/FB/Threads) | Made with AI | ✅ 强制 | 限流或拒审 |
| YouTube | Altered content | ✅ 强制 | 视频移除 |
| Lemon8 | AI-assisted content | ⚠️ 建议 | 用户举报风险 |
| Pinterest | — | ⚠️ 建议 | 暂无处罚 |
| Snapchat | — | ⚠️ 建议 | 暂无处罚 |

### 3.4 短视频 SEO 策略

**关键词权重排序**：
| 优先级 | 关键词位置 | 权重 |
| :--- | :--- | :--- |
| 🥇 | **语音关键词**（视频前5秒口述） | 最高 |
| 🥈 | **屏幕文字**（视频内嵌字幕/大字报） | 高 |
| 🥉 | **标题关键词** | 中 |
| 4 | **话题标签** | 中低 |
| 5 | **描述区关键词** | 低（补充） |

**关键词研究流程**：
1. **搜索框联想**：在 TikTok/YouTube 搜索框输入品类词，观察自动补全建议。
2. **热门标签分析**：在 TikTok Creative Center 查看同类目高频标签。
3. **评论区高频词提炼**：分析竞品视频评论区用户反复提到的词汇。
4. **长尾关键词组合**：核心词 + 场景词 + 效果词（如 "cast iron pan no oil cooking hack"）。


## 四、评估与校准体系

### 4.1 Prompt 文本质量评分表（五维度 100 分制）

| 维度 | 分值 | 评估重点 |
| :--- | :--- | :--- |
| **前 3 秒 Hook强度** | 30 分 | 视觉冲突、声音Hook、口播时机 |
| **声音策略明确度** | 25 分 | 声音标注明确度、音频同步指令、口播时机 |
| **垂直领域信号** | 20 分 | 前5秒口述+字幕双出现、大字报空间预留 |
| **原生感设计** | 15 分 | 原生感关键词、避免精修广告词汇 |
| **去 AI 味指令完整性** | 10 分 | 正向锚点词使用、防畸变指令、无否定式负向词 |

**分档阈值**：
| 总分区间 | 评级 | 执行动作 |
| :--- | :--- | :--- |
| ≥ 85 分 | ✅ 优秀 | 直接提交 |
| 80-84 分 | ⚠️ 合格 | 允许提交，建议微调 |
| 70-79 分 | 🔄 需小修 | 退回优化 |
| < 70 分 | ❌ 需大修 | 重新选择Hook方向 |

> **非线性惩罚**：若Hook强度(H)或声音策略(A)得分低于 50 分，评级自动降一档。

### 4.2 视频成片评估（直给型 100 分 + 叙事型 145 分）

**直给型五维度**：
| 维度 | 分值 | 核心指标 |
| :--- | :--- | :--- |
| 技术质量 | 20 分 | 清晰度、运镜、AI瑕疵 |
| 爆款Hook | 30 分 | 前3秒留存、完播潜力、复播引导 |
| 平台适配 | 20 分 | 收藏/分享引导、垂直信号、SEO |
| 导演执行 | 15 分 | 五维架构、原生感、声音Hook、多镜头 |
| 算法信号 | 15 分 | 复播率、收藏率、分享率预估 |

发布阈值：≥75 发布，60-74 优化，<60 废弃。

**叙事型专项加分（45 分）**：
| 指标 | 分值 | 评估标准 |
| :--- | :--- | :--- |
| 悬念维持度 | 10 分 | 前12秒困境？12-22秒悬念增强？ |
| 情绪弧线完整度 | 10 分 | 清晰情绪变化轨迹？转折自然？ |
| 产品植入自然度 | 10 分 | 故事道具而非广告主角？ |
| 评论区引导力 | 10 分 | 自然激发 "WHAT IS THIS?" 评论？ |
| 零提及纪律 | 5 分 | 严格避免品牌/价格/购买引导？ |

叙事型总分 = 五维分 + 专项分，≥110 发布。

### 4.3 评分权重校准方法

**数据收集**：每条视频记录预评估各维度得分(H/A/V/U/D)和实际完播率、收藏率。

**手动校准（Google Sheets）**：
1. 使用 `=CORREL()` 计算各维度与实际表现的相关系数。
2. 只保留正相关系数，归一化为新权重。
3. 样本量 ≥30 条后首次校准，之后每新增 20 条重复一次。

**自动化校准（Python）**：
```python
import pandas as pd
df = pd.read_csv('calibration_data.csv')
dimensions = ['H_score', 'A_score', 'V_score', 'U_score', 'D_score']
target = 'completion_rate'

correlations = {}
for dim in dimensions:
    r = df[dim].corr(df[target])
    correlations[dim] = r if r > 0 else 0

total = sum(correlations.values())
new_weights = {dim: round(corr / total, 3) for dim, corr in correlations.items()} if total > 0 else {}
print("新权重:", new_weights)
```


## 五、多语言本土化策略

### 5.1 各市场本土化速查

| 市场 | 语言 | 话术风格 | 音乐偏好 | 转化路径 |
| :--- | :--- | :--- | :--- | :--- |
| 🇺🇸 美国 | 英语 | 直接、夸张、第一人称 | Trending audio、快节奏 pop | TikTok Shop 直链 |
| 🇪🇸 西班牙语 | 西语 | 热情、家庭感、夸张但真诚 | Reggaeton、Latin pop | 评论区引导 |
| 🇫🇷 法国 | 法语 | 优雅、含蓄、强调品味 | Indie pop、Acoustic、Jazz | 官网导流 |
| 🇩🇪 德国 | 德语 | 务实、强调性价比和技术 | Minimal techno、Pop | 亚马逊导流 |
| 🇯🇵 日本 | 日语 | 含蓄、细腻、强调生活美学 | 治愈系钢琴、City pop | 楽天、Amazon |
| 🇰🇷 韩国 | 韩语 | 潮流、犀利、强调“必备” | K-pop trending、Lo-fi | Coupang、Naver |
| 🇹🇭 泰国 | 泰语 | 热情、幽默、强调性价比 | Thai pop、本土 trending | Shopee、Lazada |

### 5.2 各市场常用情绪词

| 市场 | 常用情绪词 |
| :--- | :--- |
| 美国 | insane / crazy / wild / illegal to know / game changer |
| 西班牙语 | ¡Increíble! / ¡Esto es brujería! / No puedo creerlo |
| 日语 | これ知らなかった / 戻れない / これ最高 / 便利すぎる |
| 韩语 | 이거 진짜 대박 / 이거 없으면 후회 / 완전 필수템 / 미쳤다 |

### 5.3 本土化自检清单

- [ ] Hook类型是否保留？
- [ ] 话术风格是否符合目标市场审美？
- [ ] 音节数是否与原版匹配（±2 音节）？
- [ ] 音乐建议是否符合目标市场偏好？
- [ ] 转化路径是否符合目标市场电商生态？
- [ ] 是否有文化禁忌词汇？

### 5.4 色彩文化差异速查

| 颜色 | 正面含义 | 慎用市场（负面含义） |
| :--- | :--- | :--- |
| **红色** | 喜庆、好运 | 中东部分地区 |
| **白色** | 纯洁、简约 | 中日韩（丧事） |
| **紫色** | 高贵、神秘 | 泰国、巴西（丧事） |
| **黄色** | 快乐、温暖 | 法国（背叛）、埃及（丧事） |


**版本更新记录**：
- v3.0 (2026.05)：合并原 references/ 目录下 11 个文件的核心内容，按知识模块组织为五大章节。新增Hook组合策略、色彩文化差异速查。与 SKILL.md v3.0 内容互补。
