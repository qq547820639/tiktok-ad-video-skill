# Seedance Prompt 生成系统 v3.4 (v0.1)

## Creative Quality Layer + Series Coherence + Rendering Confidence

---

## 版本定位

```text
v3.4 = v3.3 全部架构（NoPost Direct Publish / 双门控 / 验算 / 查表）
     + Q8 EmotionalImpact（创意冲击力维度）
     + EmotionalArcDensity（情绪弧密度诊断）
     + ShowDontTell 规则（R10-R12 可视化约束）
     + CharacterChoice（Q2#5 角色选择子特征）
     + SeriesCoherence（系列连贯层 SC1-SC4）
     + Seedance Rendering Confidence（PRC 渲染置信度）
     + IterativeQualityDelta（迭代质量追踪扩展）
     + Camera Direction Integration（运镜指令强制化 R13-R14）

定位: 创意质量审查器 + 结构质量审查器 + 投放交付编译器
核心改变: SS 从"结构满分就停"升级为"创意冲击力区分优劣"
声明: 不是投放效果预测模型。所有权重为专家先验，待数据校准。
```

---

## v3.3 → v3.4 变更清单

| 编号 | 变更 | 类型 | 影响 |
|:--|:--|:--|:--|
| C1 | Q8 EmotionalImpact（5 子特征） | 新增 | 评分/Winner/淘汰 |
| C2 | EAD 情绪弧密度 + LongFlatPenalty | 新增 | 诊断/Enhance |
| C3 | ShowDontTell（R10-R12） | 新增 | 铁律/编译器 |
| C4 | CharacterChoice（Q2#5 修改） | 修改 | Q2 评分 |
| C5 | SeriesCoherence（SC1-SC4） | 新增 | Winner Tie-breaker |
| C6 | Seedance Rendering Confidence（PRC + KVS） | 新增 | 风险评估 |
| C7 | 运镜指令强制化（R13-R14） | 修改 | 铁律/编译器 |
| C8 | IterativeQualityDelta（IQD） | 新增 | 迭代接受/回滚 |
| C9 | 动态权重扩展（含 Q8） | 修改 | 权重体系 |
| C10 | 四域效用扩展（U_creative 三元） | 修改 | U_domain 公式 |
| C11 | CF 扩展（C_emotional + C_series） | 修改 | 置信度 |
| C12 | HU 扩展（σ_emotional + σ_rendering） | 修改 | 不确定性 |
| C13 | 二次搜索规则扩展 | 修改 | Q8/EAD/PRC 替换触发 |
| C14 | 输出模板扩展 | 修改 | 新增快照项 |
| C15 | 硬淘汰扩展（Q8/EAD/PRC） | 修改 | 淘汰条件 |
| C16 | 低分诊断映射扩展 | 修改 | Repair/Enhance |
| C17 | PRC 查表统一（floor to 0.05） | 新增 | 取整规则 |

---

## 一、角色与交付物

与 v3.3 完全相同。追加交付项：

```
12. Q8 EmotionalImpact 快照
13. EAD 情绪弧密度 + 情绪时间线
14. PRC 渲染置信度 + KVS 逐项
15. SeriesCoherence（仅系列内容）
```

---

## 二、输入规则与 InputCompleteness

与 v3.3 完全相同（§二）。

---

## 三、NoPost Direct Publish 核心规则

与 v3.3 完全相同（§三）。

---

## 四、统一查表规则

与 v3.3 相同（§四），追加：

```
PRC 查表: floor to 0.05
  例: 0.789 → 0.75 | 0.843 → 0.80 | 0.862 → 0.85 | 0.794 → 0.75

适用: PRC 几何平均值
```

---

## 五、v3.4 状态机

```
[状态 0] 输入 + 自动假设 + ICS 计算 → 状态 0.5
[状态 0.5] KB 路由 + 动态权重（含 Q8） → 状态 1
[状态 1] 策略锁定 + 候选类型 + NoPost 模式 + 系列模式检测 → 状态 2
[状态 2] 多候选生成 + 互异性检查 + NoPost 约束 + ShowDontTell 预检 → 状态 3
[状态 3] Q1-Q8 特征计分 + N1-N8 + P1-P6 → 状态 3.05
[状态 3.05] ★ EAD 计算 + LongFlatPenalty + SC 评估（如激活） → 状态 3.1
[状态 3.1] 四域效用（含 Q8 三元） + 门控 + 风险折扣 + 奖励 + 惩罚 → 状态 3.2
[状态 3.2] NoPostGate + Cap Rules → 状态 3.25
[状态 3.25] ★ Score Verification v3.4（14 步验算） → 状态 3.3
[状态 3.3] PostReady + PRC（KVS 逐项） → 状态 3.4
[状态 3.4] 硬淘汰（含 Q8/EAD/PRC） → 状态 4
[状态 4] 低分诊断（含 Q8/EAD/PRC/ShowDontTell） → Repair → 状态 5
[状态 5] Enhance（含 Q8/EAD） → 状态 6
[状态 6] Winner（含 Q8/SC Tie-breaker + NoPostReady 优先） → 状态 7
[状态 7] CriticPass + 自然度 + 自检 → 状态 8
[状态 8] 门控（D1/D2/D7） → 状态 9 或补丁→4
[状态 9] 投放资产生成 → 状态 10
[状态 10] 终止证明 + 双版本 CTA + 输出快照（含验算行） → 终态
```

---

## 六、铁律（17 条）

v3.3 铁律 1-15 保留，修改 #5，新增 #16-17：

```
#5 修改: "每句一种运镜词" → "每句必须包含一个 Seedance 运镜指令。
         运镜指令位于句首或嵌入句中。不得在同一句使用两个运镜指令。"

#16 ShowDontTell: 所有冲突、方向、选择必须通过可见画面表达，不得依赖:
    - 否定空间关系（"not at X" / "away from X"）→ R10
    - 抽象形状描述（"shaped like X" / "arrow-shaped"）→ R11
    - 角色内心独白（"she realizes" / "they recognize"）→ R12

#17 运镜指令表（强制使用）:
    Close on / Push in / Pull back / Track / Pan / Tilt
    Hold / Drift / Follow / Rise / Drop / Circle
```

---

## 七、候选搜索

与 v3.3 相同（§七）。

---

## 八、评分体系

### 8.1 FeatureScore 特征计分（8 维 × 5 子特征 × 0/1）

**Q1-Q7 与 v3.3 相同**，仅 Q2#5 和 Q5#4 修改。

**Q2 ProductPower — CharacterChoice 修改**：

```
Q2 ProductPower（0-5）— v3.4:

+1 产品/品牌在前 1/3 出现（不变）
+1 产品功能是剧情转折条件（不变）
+1 ≥1 个可验证材质/结构/认证细节（不变）
+1 ≥1 个可验证使用场景或结果细节（不变）
+1 角色做出影响产品结果的选择（v3.3 为"价格/功能/检测锚点"）

判定: 角色主动决定"用/不用/给/不给/丢/不丢"，且该决定改变了产品在故事中的角色。
  ✅ "举到嘴边停住让出水" — 产品从"她的水"变成"她的牺牲"
  ✅ "指向空山脊" — 望远镜从"观察工具"变成"系统指令接收器"
  ✅ "拽绳索抵抗" — 手环从"装饰"变成"锁链"
  ❌ "过滤泥水喝了" — 产品按设计使用，角色无选择
  ❌ "握紧音箱" — 恐惧反应，非主动决策
  ❌ "灯笼自行亮起" — 物体自行行动，角色无参与
```

**Q5 ExecutionPower — NoPost 适配（与 v3.3 相同）**。

**Q8 EmotionalImpact（新增）**：

```
Q8 EmotionalImpact（0-5）:

+1 Hook 情绪冲击:
   前 0.5 秒画面含物理法则违反、反常识运动、或极端情境。
   判定原则: 事件本身的物理性质必须异常，不仅仅是情境恐怖。
   ✅ "水从嘴唇退开"（液体主动运动=物理违反）
   ✅ "箱子从天砸落"（无来源物体=反常识）
   ✅ "石子逆风弹起"（物体逆风=物理违反）
   ❌ "手电熄灭"（电池耗尽=正常现象）
   ❌ "风卷尘土"（正常环境）
   ❌ "瓶子从箱子滚出"（物体滚动=正常物理）

+1 情绪高点 ≥3:
   15 秒内有效情绪段 ≥3。
   情绪类型枚举: 震惊/恐惧/好奇/希望/温暖/心碎/满足/不安/释然/平静
   注: 此子特征区分度低，由 EAD 连续指标补充。

+1 角色选择:
   角色主动做出"本可以做别的但她选了这个"的决策。
   ✅ "举到嘴边→停住→让出"（放弃=选择）
   ✅ "指向空山脊而非烟"（方向=选择）
   ✅ "拽绳索抵抗"（反抗=选择）
   ❌ "过滤泥水喝了"（唯一选项=非选择）
   ❌ "握紧音箱"（恐惧反应=非选择）
   ❌ "站着不动"（冻结=非选择）

+1 结尾悬念:
   最后一句含"观众不预期的行为"或"无法解释的画面元素"。
   ✅ "她不喝水""箱盖掀起""影子已走人没动""第二女人已在看左"
   ❌ "风声消失""画面静止"

+1 情绪弧非单调:
   前 1/3 和后 1/3 主导情绪不同。
   ✅ "恐惧→好奇→恐惧"（有起伏）
   ❌ "恐惧→不安→恐惧"（不安≈恐惧变体，无实质起伏）
```

---

### 8.2 动态权重（v3.4 扩展）

```
基础权重（v3.4）:
  Q1=0.15  Q2=0.15  Q3=0.10  Q4=0.10  Q5=0.12  Q6=0.08  Q7=0.08  Q8=0.22

说明: Q8 权重 0.22 = 最高权重。
     Q1/Q2 从 0.20 降至 0.15（准入门槛，非质量区分）。
     Q6/Q7 从 0.10 降至 0.08（腾出空间给 Q8）。
```

**调整表**：与 v3.3 相同（品类/市场/价格/模式），Δ 作用于新的基础权重。

**计算**：与 v3.3 相同（归一化，约束 0.08-0.30）。

---

### 8.3 四域效用（v3.4 扩展）

```
q_i = Q_i / 5

U_creative  = (q1 × q4 × q8)^(1/3)    ← v3.3 为 sqrt(q1×q4)
U_product   = sqrt(q2 × q3)             ← 不变
U_execution = sqrt(q5 × q7)             ← 不变
U_delivery  = q6                         ← 不变

U_domain = 0.35 × U_creative
         + 0.25 × U_product
         + 0.25 × U_execution
         + 0.15 × U_delivery
```

**Q8 对 U_creative 的影响**：

```
Q8=1 (q8=0.2): U_creative = 0.2^(1/3) = 0.585
Q8=2 (q8=0.4): U_creative = 0.4^(1/3) = 0.737
Q8=3 (q8=0.6): U_creative = 0.6^(1/3) = 0.843
Q8=4 (q8=0.8): U_creative = 0.8^(1/3) = 0.928
Q8=5 (q8=1.0): U_creative = 1.0^(1/3) = 1.000

几何均值三元意味着: Q1、Q4、Q8 中任何一个短板都会拉低 U_creative。
```

---

### 8.4-8.8 门控/MarketFit/风险折扣/Bonus/Penalty

与 v3.3 完全相同。

---

### 8.9 StructureScore

```
StructureScore = clamp(100 × U_domain × G_gate × R_risk × B_bonus − P_penalty, 0, 100)

其中 v3.4 变更:
  U_creative = (q1 × q4 × q8)^(1/3)   ← 含 Q8
  其余不变
```

---

### 8.10 ConfidenceFactor（v3.4 扩展）

```
CF = C_exec^0.15 × C_map^0.10 × C_score^0.10 × C_coh^0.10
   × C_gen^0.15 × C_input^0.10 × C_emotional^0.15 × C_series^0.15

新增:
  C_emotional: Q8=5→1.00 | 4→0.90 | 3→0.80 | ≤2→0.70
  C_series:    未激活→1.00 | SC=4→1.00 | 3→0.90 | 2→0.80 | ≤1→0.70

幂函数查表（与 v3.3 相同）。
```

---

### 8.11 HeuristicUncertainty（v3.4 扩展）

```
HU = ± sqrt(σ_feature² + σ_generation² + σ_market²
          + σ_delivery² + σ_nopost² + σ_input²
          + σ_emotional² + σ_rendering²)

新增:
  σ_emotional: Q8=5→±1 | 4→±2 | 3→±3 | ≤2→±4
  σ_rendering: PRC≥0.85→±1 | 0.70-0.84→±2 | 0.50-0.69→±3 | <0.50→±4

σ 合成查表: 与 v3.3 相同。
```

---

## 九、EmotionalArcDensity（新增）

### 9.1 定义

```
EAD = 有效情绪段数量 / 15

有效情绪段: 每当主导情绪类型发生切换，新段开始。
  同一情绪类型重复出现（被其他情绪打断后）算作新段。
  同一情绪类型连续出现不计为新段。

情绪类型枚举（10 种）:
  震惊 | 恐惧 | 好奇 | 希望 | 温暖 | 心碎 | 满足 | 不安 | 释然 | 平静
```

### 9.2 分级

| EAD | 段数/15s | 等级 | 动作 |
|:--|:--|:--|:--|
| ≥0.33 | ≥5 | 极强 | 无 |
| 0.27 | 4 | 强 | 可选增强 |
| 0.20 | 3 | 中等 | 触发增强 |
| 0.13 | 2 | 弱 | 触发重写 |
| ≤0.07 | ≤1 | 极弱 | 强制重写 |

### 9.3 LongFlatPenalty

```
若存在 ≥6 秒连续同一情绪段 → EAD 等级下调一级
若存在 ≥8 秒连续同一情绪段 → 强制触发 Enhance
```

### 9.4 诊断映射

```
当 EAD < 0.33 时:
  Step 1: 标记最长连续同情绪段落（≥4 秒）
  Step 2: 该段落主导情绪
  Step 3: 插入什么情绪切换

  长段=满足/平静 → 插入"心碎"或"恐惧"
  长段=恐惧      → 插入"希望"或"温暖"
  长段=好奇      → 插入"震惊"或"恐惧"
  长段=希望      → 插入"心碎"
```

---

## 十、ShowDontTell 规则（新增）

### R10：否定空间关系

```
触发: "not at X" / "not toward X" / "away from X" / "opposite to X" / "instead of X"（空间方向时）
不触发: "empty" / "bare" / "still"（状态描述）/ "already looking left"（正向方向）
类型: RepairableRed
优先级: 高

替换模板:
  "not at X, but at Y" → "pointing toward Y — X visible in the other direction"
  "away from X" → 删除，用正向目标 + "X rising behind her shoulder"
  "instead of X" → 用动作对比（"she steps left — the right path stays empty"）
```

### R11：抽象形状描述

```
触发: "shaped like X" / "X-shaped" / "resembling X"（抽象概念时）
不触发: 具象物体/材质/简单几何/可见状态
类型: StyleRed（扣分不阻断）
优先级: 中

替换模板:
  "shaped like X" → 光线/运动/材质替代形状
  "X-shaped crack" → "a crack with light at one end"
```

### R12：角色内心独白

```
触发: "she realizes" / "she understands" / "they recognize" / "she feels X" / 解释性后缀
不触发: 可见身体反应/可见动作/可见状态
类型: RepairableRed
优先级: 中

替换模板:
  "she realizes X" → 身体反应（"she looks at... then... then..."）
  "they recognize X" → 同步动作（"both women turn toward each other"）
  "she feels X" → 可见状态（"her hands tremble"）
  解释性后缀 → 删除后缀，保留画面
```

---

## 十一、运镜指令强制化（R13-R14）

```
R13: 同一句 ≥2 个运镜指令 → StyleRed
R14: 连续两句使用相同运镜指令 → StyleRed（扣分不阻断）

运镜指令表:
  Close on / Push in / Pull back / Track / Pan / Tilt
  Hold / Drift / Follow / Rise / Drop / Circle

规则: 每句必须包含至少一个。位于句首或嵌入句中。
```

---

## 十二、Seedance Rendering Confidence（新增）

### 12.1 KVS 识别规则

```
每个满足以下任一条件的画面元素必须标记为 KVS:
  1. 物理法则违反
  2. 物体自行运动
  3. 双人协调动作
  4. 空间异常
  5. 声音触发画面
  6. 结尾彩蛋画面
  7. 产品首次出现的特写
```

### 12.2 KVS 渲染置信度分级

```
🟢 高置信 (0.9):
  物体运动 | 光源变化 | 手部交互 | 材质特写 | 机械运动
  简单空间 | 静态对比

🟡 中置信 (0.7):
  液体动力学 | 双人协调动作 | 绳索运动 | 影子长度/方向
  复杂空间 | 面部微表情

🔴 低置信 (0.5):
  POV 画面 | 影子精确转角/行走 | 文字/数字/二维码
  微表情精确控制 | 精确数量物体 | 变形/融化/消失 | 声音可视化
```

### 12.3 PRC 计算

```
PRC = (∏ KVS_confidence_i)^(1/n)

PRC 查表: floor to 0.05

分级:
  PRC ≥ 0.85: 高置信 — 可直接生成
  PRC 0.70-0.84: 中置信 — 建议准备兜底画面
  PRC 0.50-0.69: 低置信 — 建议替换低置信 KVS
  PRC < 0.50: 极低置信 — 强制替换或标注风险
```

### 12.4 PRC 与 Q7 的关系

```
Q7 = 通用评估（画面主体/文字/动作/光线/产品）
PRC = 具体视觉元素渲染置信度

两者独立评估，不互相替代。
PRC 不参与 StructureScore。
PRC 用于: 快照标注 / 诊断定位 / Enhance 优先替换。
```

---

## 十三、SeriesCoherence（新增）

### 13.1 激活条件

```
当输入包含"系列"或"EP"标记时激活。
仅加载前 3 集摘要（非全文），节省 context。
```

### 13.2 SC1-SC4

```
SC1 系统能力递进（0/1）:
  本集的"物件自行运动"类型是否与前集不同？
  与任意前集重复=0 | 全新类型=1

SC2 视觉谜题差异（0/1）:
  本集的彩蛋视觉是否与前集不同？
  与前集同类型=0 | 全新视觉=1

SC3 角色关系发展（0/1）:
  本集的双人关系是否有新动态？
  与前集相同=0 | 新互动类型=1

SC4 彩蛋→总线索连接（0/1）:
  本集彩蛋是否推进了系列总悬念？
  无关=0 | 推进=1

SeriesCoherenceScore = SC1 + SC2 + SC3 + SC4 (0-4)
```

### 13.3 SC 用途

```
1. Winner Tie-breaker: SS 差距 <3 时，SC 更高优先
2. 修复触发: SC1=0 → "彩蛋类型替换" | SC3=0 → "角色互动类型替换"
3. CF 分项: C_series（见 §8.10）
```

---

## 十四、IterativeQualityDelta（新增）

```
每次迭代后记录:
  ΔQ8: Q8 变化
  ΔEAD: EAD 段数变化
  ΔPRC: PRC 变化
  ΔWordCount: 词数变化

接受条件扩展（v3.4 新增）:
  6. ΔQ8 ≥ +1 且其他核心 Q 不降
  7. ΔEAD ≥ +1 且 SS 不降超 1
  8. ΔPRC ≥ +0.05 且 Q8 不降

回滚条件扩展（v3.4 新增）:
  10. ΔQ8 < 0（情绪冲击力下降）
  11. ΔEAD < 0 且无其他维度改善
```

---

## 十五、NoPostGate / PostReady

与 v3.3 完全相同（§九/§十一）。

---

## 十六、Score-Guided 候选搜索与收敛

### 16.1-16.3 与 v3.3 相同

### 16.4 低分诊断映射（v3.4 扩展）

v3.3 映射保留，新增：

```
| 触发条件 | 可编辑区域 | 修改动作 | 接受标准 |
|:--|:--|:--|:--|
| Q8≤3 | Hook+结尾+情绪低谷 | Hook改为"不可能"事件；结尾改为不做预期动作；低谷插入切换 | Q8+1 |
| Q8#1=0 | 第1句 | 将"正常现象"改为"物理违反" | #1→1 |
| Q8#3=0 | 中段 | 加入角色选择 | #3→1 |
| Q8#4=0 | 最后1-2句 | 结尾改为不做预期动作 | #4→1 |
| EAD<0.33 | 最长同情绪段 | 在该段插入情绪切换 | EAD→≥0.20 |
| EAD LongFlat ≥8s | 该段落 | 必须插入至少一个情绪切换 | LongFlat<8s |
| PRC<0.70 | 低置信KVS | 替换为同等创意但更高渲染置信度的视觉 | PRC→≥0.70 |
| R10 触发 | 否定空间句 | "not at X" → "toward Y — X behind" | R10=0 |
| R12 触发 | 内心独白句 | "she realizes" → 身体反应 | R12=0 |
```

### 16.5-16.8 与 v3.3 相同，修改 Winner Tie-breaker：

```
排序:
1. StructureScore 高者优先
2. NoPostReady=true 优先（用户要求无后期时）
3. SS 差距 <3 时 Tie-breaker:
   - SC 更高
   - Q8 更高
   - NoPostGate 更高
   - Q7 更高
   - PostReadyScore 更高
   - Q1 更高
   - Q2 更高
   - D7 更高
   - 品牌植入更自然
   - 广告腔更低
```

### 16.9 终止条件（v3.4 扩展）

v3.3 条件保留，新增：
```
7. Q8 < 3 且修复后仍 < 3 → 输出最高 Q8 候选 + ⚠️
8. EAD ≤ 0.07 且增强后仍 ≤ 0.07 → 输出最高 EAD 候选 + ⚠️
```

---

## 十七、编译器规则集

### 17.1 阻断项

v3.3 保留，新增：

```
RepairableRed:
  R10: 否定空间关系
  R12: 角色内心独白

StyleRed:
  R11: 抽象形状描述
  R13: 同一句 ≥2 个运镜指令
  R14: 连续两句相同运镜指令
```

### 17.2 风险项

与 v3.3 相同。

---

## 十八、硬淘汰（v3.4 扩展）

v3.3 条件保留，新增：
```
10. Q8 < 3
11. EAD ≤ 0.07（LongFlatPenalty 后）
12. PRC < 0.50 且无兜底方案
```

---

## 十九、Score Verification v3.4（14 步）

```
Step 1:  U_domain（含 Q8 三元几何均值）
         U_creative = (q1 × q4 × q8)^(1/3)
         写出 q1, q4, q8 和 U_creative 值

Step 2:  G_gate（注明 G_nopost 激活/不激活）

Step 3:  RiskLoad + R_risk（RiskLoadWeights 五项，权重和=0.65）

Step 4:  B_bonus（查表）

Step 5:  P_penalty（五项 + 重叠检查）

Step 6:  StructureScore（完整乘式 + clamp）

Step 7:  CF（含 C_emotional + C_series，幂函数查表）

Step 8:  HU（含 σ_emotional + σ_rendering，σ 合成查表）

Step 9:  PostReadyScore

Step 10: NoPostRiskLoad（NoPostRiskWeights 八项，权重和=1.00）

Step 11: Cap Rules + FinalNoPostGate

Step 12: Q8 EmotionalImpact 明细（5 子特征逐项）

Step 13: EAD + LongFlatPenalty + 情绪时间线

Step 14: PRC + KVS 逐项（🟢/🟡/🔴 + 置信度值）
```

---

## 二十、输出模板

### 投放版（v3.4）

在 v3.3 投放版基础上追加：

```
## 【情绪冲击力】
Q8: N/5
  #1 Hook冲击: ✓/✗ [描述]
  #2 情绪高点: N个 [等级]
  #3 角色选择: ✓/✗ [描述]
  #4 结尾悬念: ✓/✗ [描述]
  #5 弧线非单调: ✓/✗ [描述]

## 【情绪弧密度】
EAD: N.NN (N段/15s) [极强/强/中等/弱/极弱]
LongFlatPenalty: [无/触发]
情绪时间线: [震惊→恐惧→好奇→希望→心碎→温暖→恐惧]

## 【渲染置信度】
PRC: N.NN [高/中/低/极低]
KVS1: [描述] → 🟢/🟡/🔴 (N.N)
KVS2: [描述] → 🟢/🟡/🔴 (N.N)
...

## 【系列连贯性】（仅系列内容）
SC: N/4
SC1 系统能力递进: ✓/✗
SC2 视觉谜题差异: ✓/✗
SC3 角色关系发展: ✓/✗
SC4 彩蛋→总线索: ✓/✗
```

### 完整版追加

v3.3 完整版内容保留，追加：

```
## 【验算行 — Score Verification v3.4】
[14 步完整验算]

## 【迭代摘要 — 含 IQD】
V1: 初评SS=N.N Q8=N EAD=N PRC=N.NN
    | 弱项:?? | 修复:?? | 增强:??
    | ΔSS=N ΔQ8=N ΔEAD=N ΔPRC=N.NN
    | 结果:[接受/回滚] | 接受原因:??
```

---

## 二十一、二次搜索规则（v3.4 扩展）

```
替换规则:
  新 SS ≥ 当前 + 5 → 替换
  或 新 SS ≥ 当前 + 3 且 NoPostGate ≥ 当前 → 替换
  或 新 Q8 ≥ 当前 + 2 且 SS 不降超 2 → 替换        ← 新增
  或 新 EAD 段数 ≥ 当前 + 2 且 SS 不降超 1 → 替换   ← 新增
  或 新 PRC ≥ 当前 + 0.10 且 Q8 不降 → 替换          ← 新增

硬上限: 最多 2 次二次搜索。
```

---

## 二十二、回测附录

### EP.6 v1-v4 Q8 判例

| EP | 版本 | #1 | #2 | #3 | #4 | #5 | Q8 |
|:--|:--|:--:|:--:|:--:|:--:|:--:|:--:|
| 6 v1 | 产品版 | 0 | 1 | 0 | 0 | 0 | **1** |
| 6 v2 | 恐惧版 | 1 | 1 | 0 | 0 | 1 | **3** |
| 6 v3 | 牺牲版 | 1 | 1 | 1 | 1 | 1 | **5** |
| 6 v4 | 审判版 | 1 | 1 | 1 | 1 | 1 | **5** |

### EP.6-10 EAD 回测

| EP | 版本 | 段数 | EAD | 等级 | LongFlat |
|:--|:--|:--:|:--:|:--|:--|
| 6 v1 | 产品版 | 4 | 0.27 | 强→中等(LongFlat) | 8s 满足段 |
| 6 v2 | 恐惧版 | 6 | 0.40 | 极强 | 无 |
| 6 v3 | 牺牲版 | 9 | 0.60 | 极强 | 无 |
| 6 v4 | 审判版 | 11 | 0.73 | 极强 | 无 |
| 7 v1.2 | 引导版 | 8 | 0.53 | 极强 | 无 |
| 8 v1.1 | 影子版 | 6 | 0.40 | 极强 | 无 |
| 9 v1.1 | 绑定版 | 8 | 0.53 | 极强 | 无 |
| 10 v1.1 | 终章版 | 8 | 0.53 | 极强 | 无 |

### EP.6-10 PRC 回测

| EP | 版本 | KVS 数 | 🟢 | 🟡 | 🔴 | PRC | 等级 |
|:--|:--|:--:|:--:|:--:|:--:|:--:|:--|
| 6 v4 | 审判版 | 9 | 4 | 5 | 0 | 0.75 | 中置信 |
| 7 v1.2 | 引导版 | 7 | 6 | 1 | 0 | 0.85 | 高置信 |
| 8 v1.1 | 影子版 | 6 | 3 | 3 | 0 | 0.75 | 中置信 |
| 9 v1.1 | 绑定版 | 8 | 6 | 2 | 0 | 0.80 | 中置信 |
| 10 v1.1 | 终章版 | 6 | 3 | 3 | 0 | 0.75 | 中置信 |

### EP.6-10 SC 回测

| EP | SC1 | SC2 | SC3 | SC4 | SC |
|:--|:--:|:--:|:--:|:--:|:--:|
| 6 | ✓ | ✓ | ✓ | ✓ | 4/4 |
| 7 | ✓ | ✓ | ✓ | ✓ | 4/4 |
| 8 | ✓ | ✓ | ✓ | ✓ | 4/4 |
| 9 | ✓ | ✓ | ✓ | ✓ | 4/4 |
| 10 | ✓ | ✓ | ✓ | ✓ | 4/4 |

### EP.6-10 Q2#5 CharacterChoice 回测

| EP | 版本 | 选择行为 | Q2#5 | Q2 |
|:--|:--|:--|:--:|:--:|
| 6 v1 | 产品版 | 过滤→喝（被动） | 0 | 4 |
| 6 v4 | 审判版 | 让出+回报（主动） | 1 | 5 |
| 7 v1.2 | 引导版 | 指向空山脊（主动） | 1 | 5 |
| 8 v1.1 | 影子版 | 站着不动（冻结） | 0 | 4 |
| 9 v1.1 | 绑定版 | 拽绳索抵抗（主动） | 1 | 5 |
| 10 v1.1 | 终章版 | 握紧音箱（恐惧反应） | 0 | 4 |

### EP.6-10 v3.4 SS 全景

| EP | 版本 | Q1 | Q2 | Q3 | Q4 | Q5 | Q6 | Q7 | Q8 | v3.4 SS |
|:--|:--|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| 6 v1 | 产品版 | 5 | 4 | 5 | 5 | 5 | 5 | 5 | 1 | **80.6** |
| 6 v2 | 恐惧版 | 5 | 4 | 5 | 5 | 5 | 5 | 5 | 3 | **91.1** |
| 6 v3 | 牺牲版 | 5 | 5 | 5 | 5 | 5 | 5 | 5 | 5 | **98.4** |
| 6 v4 | 审判版 | 5 | 5 | 5 | 5 | 5 | 5 | 4 | 5 | **100.0** |
| 7 v1.2 | 引导版 | 5 | 5 | 5 | 5 | 5 | 5 | 4 | 5 | **100.0** |
| 8 v1.1 | 影子版 | 5 | 4 | 5 | 5 | 5 | 5 | 4 | 2 | **88.3** |
| 9 v1.1 | 绑定版 | 5 | 5 | 5 | 5 | 5 | 5 | 4 | 5 | **100.0** |
| 10 v1.1 | 终章版 | 5 | 4 | 5 | 5 | 5 | 5 | 4 | 3 | ⚠️ 需 Phase 7 重算 |

**⚠️ EP.10 v3.4 SS 待 Phase 7 统一重算**：
```
v3.4 输入: Q2=4, Q7=4, Q8=3, FinalNoPostGate=0.80
U_creative = (1.0 × 1.0 × 0.6)^(1/3) = 0.843
U_product = sqrt(0.8 × 1.0) = 0.894
U_execution = sqrt(1.0 × 0.8) = 0.894
U_delivery = 1.00
U_domain = 0.35(0.843) + 0.25(0.894) + 0.25(0.894) + 0.15(1.00) = 0.892
G_nopost: 0.80 → 0.70-0.84 → G_nopost=0.90
G_gate = 1.00 × 1.00 × 1.00 × 1.00 × 0.90 = 0.900
SS = clamp(100 × 0.892 × 0.900 × 0.975 × 1.060, 0, 100)
   = clamp(82.8, 0, 100) = 82.8

v3.4 SS ≈ 82.8（待 Phase 7 确认）
```

---

## 二十三、降级总表

v3.3 降级表保留，新增：

| 场景 | 行为 |
|:--|:--|
| Q8 < 3 且修复后仍 < 3 | 输出最高 Q8 候选 + ⚠️ |
| EAD ≤ 0.07 且增强后仍 ≤ 0.07 | 输出最高 EAD 候选 + ⚠️ |
| PRC < 0.50 | 标注渲染风险 + 建议替换低置信 KVS |
| R10 触发且修复失败 | 输出当前 + ⚠️ + 标注 Seedance 可能无法渲染 |
| SC < 2（系列模式） | 标注系列连贯性不足 + ⚠️ |

---

## 二十四、Anti-Pseudoscience 声明

v3.3 声明保留，新增：

```
10. Q8 EmotionalImpact 的子特征判定存在主观性，
    不同运行可能给出 ±1 浮动。回测判例表提供参考基准。
11. EAD 情绪类型枚举可能不覆盖所有内容类型，
    当前主要基于末日/悬疑/生存类样本校准。
12. PRC 的 KVS 识别和置信度分级依赖人工标注，
    未来需要 Seedance 实际渲染数据校准。
13. SeriesCoherence 仅评估系列内部递进，
    不评估与外部内容的竞争差异化。
```

---

## 二十五、版本历史

| 版本 | 核心变更 |
|:--|:--|
| v1.0-v1.6.1 | 评估体系演进 |
| v2.0 | StructureScore v2 + Score-Guided + NoPostGate v2 |
| v3.0-v3.2 | 双门控 + PostReady + 验算 + 查表 |
| v3.3 | NoPost Direct Publish + 动作型 CTA + 视频内文字限制 |
| **v3.4** | **Q8 EmotionalImpact + EAD 情绪弧密度 + ShowDontTell(R10-R12) + CharacterChoice(Q2#5) + SeriesCoherence(SC1-SC4) + RenderingConfidence(PRC+KVS) + R13-R14 运镜强制 + IQD 迭代追踪 + U_creative 三元 + CF/HU 扩展 + 14步验算** |

```
v3.4 变更（相对 v3.3）:
  [PARADIGM] 评分: 从"结构有没有错误"升级到"创意够不够好"
  [PARADIGM] U_creative: 二元 sqrt(q1×q4) → 三元 (q1×q4×q8)^(1/3)
  [PARADIGM] Hook: 从"有没有声音+动作"到"情绪冲击类型"
  [PARADIGM] Q2: 从"产品有没有功能锚点"到"产品是否融入角色选择"
  [PARADIGM] Winner: SC/Q8 加入 Tie-breaker 序列
  [NEW] Q8 EmotionalImpact (5子特征, 权重0.22)
  [NEW] EAD 情绪弧密度 + LongFlatPenalty
  [NEW] ShowDontTell: R10 否定空间 / R11 抽象形状 / R12 内心独白
  [NEW] CharacterChoice: Q2#5 角色选择影响产品结果
  [NEW] SeriesCoherence: SC1-SC4 (递进/差异/关系/总线索)
  [NEW] PRC + KVS 三级置信度 (🟢0.9/🟡0.7/🔴0.5)
  [NEW] R13-R14 运镜指令强制化
  [NEW] IQD 迭代质量追踪 (ΔQ8/ΔEAD/ΔPRC)
  [NEW] C_emotional + C_series (CF 扩展)
  [NEW] σ_emotional + σ_rendering (HU 扩展)
  [NEW] 硬淘汰: Q8<3 / EAD≤0.07 / PRC<0.50
  [NEW] 低分映射: Q8/EAD/PRC/R10/R12 诊断行
  [NEW] 二次搜索: Q8/EAD/PRC 替换触发
  [NEW] Score Verification 14步 (含 Q8/EAD/PRC)
  [NEW] PRC 查表: floor to 0.05
  [FIX] Q2#5: "价格锚点" → "角色选择"
  [FIX] 动态权重: Q8=0.22 最高权重
  [KEEP] v3.3 全部: NoPost Direct Publish / 双门控 / 查表取整
         / 铁律1-15 / 编译器 / D门控 / CriticPass / 辅助+创意+自检
         / 投放资产 / KB-1~18 / PS-1~6 / 二次搜索 / 降级
```

---

## 二十六、待 Phase 7-10 完成项

```
Phase 7: 动态权重 + U_domain + CF + HU 统一重算
  → EP.10 v3.4 SS 确认
  → EP.6 v3 SS 确认（D7=🟡 时的 P_penalty）
  → 全景表最终版

Phase 8: 状态机 + Score Verification 更新
  → 14 步验算标准化
  → 验算模板

Phase 9: 迭代追踪 + 诊断映射 + 二次搜索
  → IQD 记录格式
  → 低分映射完整表

Phase 10: 输出模板 + 降级 + PS 更新
  → 投放版/完整版最终模板
  → 降级总表更新
  → PS-4 数据回流扩展（Q8/EAD/PRC 校准）
```

---

## 二十七、一句话定位

```
Seedance 2.0 TikTok Growth Prompt Compiler v3.4
= 创意质量审查器 + 结构质量审查器 + 投放交付编译器
  + Score-Guided 搜索收敛 + NoPost 主动优化 + 系列连贯层 + 渲染置信度

v3.4 核心升级:
  Q8 EmotionalImpact 成为最高权重维度 (0.22)，
  用三元几何均值 (q1×q4×q8)^(1/3) 将创意冲击力注入 U_creative。
  EAD 衡量 15 秒内的情绪节奏密度，LongFlatPenalty 标记长时间情绪单调。
  ShowDontTell 确保冲突可视觉化（R10-R12）。
  CharacterChoice 确保产品融入角色决策（Q2#5）。
  SeriesCoherence 确保系列递进不重复（SC1-SC4）。
  PRC 标记每个关键视觉瞬间的 Seedance 渲染置信度。
  所有参数在投放数据校准前均为专家先验。
```
