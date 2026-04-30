# Seedance Prompt 生成系统 v3.2

## Verified Dual-Gate Growth Delivery Compiler

---

## 版本定位

```text
v3.2 = v3.1 全部 + 三处 spec 修正:
  1. RiskLoad 权重统一（与 N 维度权重一致，或明确独立声明）
  2. NoPostRiskLoad 权重归一到 1.00
  3. Q7 子特征边界澄清（只评估画面生成可靠性，不扣 CTA/品牌后期依赖）
  + Score Verification 增加 NoPostRiskLoad 分项加总
  + 修正后数值校准（SS≈84, CF≈0.91, HU≈±8）

定位: Seedance Prompt 结构质量审查器 + TikTok 投放交付编译器
声明: 不是投放效果预测模型。所有权重为专家先验，待数据校准。
```

---

## 一、v3.2 变更日志（相对 v3.1）

```
[FIX] Q7 子特征边界: 明确只评估"Seedance 生成视频画面的可靠性"
      "CTA/品牌/价格需要后期"→ 影响 NoPostGate，不影响 Q7
[FIX] RiskLoad 权重统一:
      旧: 0.30×Text + 0.20×Edit + 0.20×Claim + 0.15×ProdFid + 0.15×CTA
      新: 与 N 维度权重一致的五项子集
[FIX] NoPostRiskLoad 权重归一:
      旧: 权重和=1.05（N1=0.20, N2=0.15, N3=0.15, N4=0.15, N5=0.10, N6=0.10, N7=0.10, N8=0.05）
      新: 权重和=1.00（N1=0.20, N2=0.15, N3=0.10, N4=0.15, N5=0.10, N6=0.10, N7=0.10, N8=0.10）
[FIX] Score Verification: 增加 NoPostRiskLoad 分项加总验算
[FIX] 数值校准: SS≈84, CF≈0.91, HU≈±8（基于 Q7=5 修正后的级联效应）
[KEEP] v3.1 全部: 验算层/查表/ICS警告/双门控/Score-Guided/StructureScore v2
```

---

## 二、Q7 子特征边界澄清

### 2.1 Q7 评估范围（v3.2 修正）

```
Q7 GenerationReliability 评估的是:
"Seedance 生成视频画面本身的可靠性"

不评估:
- 投放资产是否完整（→ Q6）
- 品牌/价格/CTA 是否需要后期（→ NoPostGate）
- 视频不后期能否直接发布（→ NoPostGate）
```

### 2.2 Q7 子特征（明确边界版）

```
Q7 GenerationReliability（0-5）:

+1 画面主体简单（单人/物体/手部）
   → 评估: 角色数量、肢体复杂度、背景复杂度
   → 不评估: 品牌标识是否清晰

+1 文字生成依赖低
   → 评估: Prompt 是否要求画面内出现精准文字
   → 不评估: 后期是否需要叠加文字

+1 动作不需精确控制
   → 评估: 动作是否需要精确数量、时长、节奏、微表情
   → 不评估: CTA 动作是否自然

+1 光线空间关系简单
   → 评估: 光源是否稳定、空间是否复杂、是否有精确透视要求
   → 不评估: 场景是否适合投放

+1 产品外观稳定可渲染
   → 评估: 产品形态是否简单、材质是否可渲染、是否有复杂反光/透明件
   → 不评估: Logo 是否精准、价格是否准确
```

### 2.3 边界判定规则

```
"CTA/品牌/价格需要后期" → 影响:
  - NoPostGate（N1-N4 风险上升）
  - PostReady（P4 CTARecoverability）
  - D7 CTA 门控
  - P_penalty（CommercialPenalty）

不影响:
  - Q7 GenerationReliability
  - U_execution
  - G_reliability
```

**示例**：
```
Prompt 要求黑底卡 reserved for post-production text:
  → Q7 不扣分（Seedance 只需生成黑色画面，无精准文字需求）
  → N1=10（视频内需要精准文字→高风险）
  → N4=6（CTA 需要后期）
  → NoPostGate ≤ 0.60
  → D7 = 🟡（CTA 依赖后期）
```

---

## 三、RiskLoad 权重统一（v3.2 修正）

### 3.1 问题

v3.1 的 RiskLoad 使用独立权重（0.30/0.20/0.20/0.15/0.15），与 N 维度权重（0.20/0.15/0.15/0.15/0.10/0.10/0.10/0.05）不对应。

### 3.2 修正方案

**方案：RiskLoad 使用 N 维度权重的对应子集**

```
RiskLoad 用于 StructureScore 的 R_risk 折扣。
它应该反映与"投放效果风险"最相关的 N 维度。

选取标准: 直接影响视频投放效果的维度。

RiskLoad = (
  w_N1 × N1_TextAccuracy
+ w_N4 × N4_CTACompleteness
+ w_N5 × N5_EditDependency
+ w_N6 × N6_ClaimCompliance
+ w_N7 × N7_ProductFidelity
) / 10

其中 w 取自 N 维度权重:
  w_N1 = 0.20
  w_N4 = 0.15
  w_N5 = 0.10
  w_N6 = 0.10
  w_N7 = 0.10

权重和 = 0.65（仅使用 5/8 维度，不归一化，因为 RiskLoad 是折扣因子而非概率）
```

**查表不变**：
```
RiskLoad 查表:
  0.00 → R_risk = 1.000
  0.10 → 0.975
  0.20 → 0.951
  0.30 → 0.928
  0.40 → 0.905
  0.50 → 0.882
  0.60 → 0.861
  0.70 → 0.839
  0.80 → 0.819
  0.90 → 0.799
  1.00 → 0.779
```

**示例（SnapStand 案例）**：
```
RiskLoad = (0.20×10 + 0.15×6 + 0.10×6 + 0.10×3 + 0.10×3) / 10
         = (2.00 + 0.90 + 0.60 + 0.30 + 0.30) / 10
         = 4.10 / 10
         = 0.41
→ R_risk 查表 0.40 → 0.905
```

**影响**：SS 从 84.3 变为：
```
SS = 100 × 1.000 × 1.000 × 0.905 × 1.060 - 7 = 88.9
```

修正后 SS ≈ 88.9，等级从"可用（触发增强）"升为**"强候选"**。

---

## 四、NoPostRiskLoad 权重归一（v3.2 修正）

### 4.1 问题

v3.1 的 NoPostRiskLoad 权重和 = 1.05（N3=0.15 导致超 1.0）。

### 4.2 修正

```
NoPostRiskLoad = (
  0.20 × N1_TextAccuracy
+ 0.15 × N2_PriceAccuracy
+ 0.10 × N3_LogoBrand        ← 从 0.15 降到 0.10
+ 0.15 × N4_CTACompleteness
+ 0.10 × N5_EditDependency
+ 0.10 × N6_ClaimCompliance
+ 0.10 × N7_ProductFidelity
+ 0.10 × N8_NarrativeDependency  ← 从 0.05 升到 0.10
) / 10

权重和 = 0.20+0.15+0.10+0.15+0.10+0.10+0.10+0.10 = 1.00 ✓
```

**修正理由**：
- N3 LogoBrand 从 0.15→0.10：Logo 风险可以通过后期叠加相对容易解决
- N8 NarrativeDependency 从 0.05→0.10：叙事对文字/Logo 的依赖是更隐蔽的风险，应给予更高权重

**示例（SnapStand 案例）**：
```
NoPostRiskLoad = (0.20×10 + 0.15×3 + 0.10×3 + 0.15×6 + 0.10×6 + 0.10×3 + 0.10×3 + 0.10×3) / 10
               = (2.00 + 0.45 + 0.30 + 0.90 + 0.60 + 0.30 + 0.30 + 0.30) / 10
               = 5.15 / 10
               = 0.515
→ 查表 0.50 → BaseNoPostGate = 0.69
→ Cap Rule: reserved for post-production text → ≤ 0.60
→ FinalNoPostGate = 0.60
```

NoPostGate 最终值不变（被 Cap Rule 压住），但中间计算更准确。

---

## 五、Score Verification 更新（v3.2）

### 5.1 新增 NoPostRiskLoad 分项加总

```
[状态 3.25] Score Verification（v3.2 更新）

Step 1-9: 与 v3.1 相同

Step 10: NoPostRiskLoad（新增）
  写出: NoPostRiskLoad = (
    0.20×N1 + 0.15×N2 + 0.10×N3 + 0.15×N4
  + 0.10×N5 + 0.10×N6 + 0.10×N7 + 0.10×N8
  ) / 10
  写出: = (?? + ?? + ?? + ?? + ?? + ?? + ?? + ??) / 10
  写出: = ?? / 10
  写出: = ??
  验证: 权重和 = 0.20+0.15+0.10+0.15+0.10+0.10+0.10+0.10 = 1.00 ✓

Step 11: BaseNoPostGate
  写出: 查表 NoPostRiskLoad=?? → BaseNoPostGate=??

Step 12: Cap Rules
  写出: 触发的 Cap Rules 列表
  写出: FinalNoPostGate = min(??, ??, ...) = ??
```

### 5.2 完整验算模板（v3.2）

```
## 【验算行 — Score Verification v3.2】

U_creative  = sqrt(q1 × q4) = sqrt(?? × ??) = ??
U_product   = sqrt(q2 × q3) = sqrt(?? × ??) = ??
U_execution = sqrt(q5 × q7) = sqrt(?? × ??) = ??
U_delivery  = q6 = ??
U_domain    = 0.35×?? + 0.25×?? + 0.25×?? + 0.15×?? = ??

G_hook=?? G_product=?? G_reliability=?? G_market=?? G_nopost=??
G_gate = ?? × ?? × ?? × ?? × ?? = ??

RiskLoad = (0.20×N1 + 0.15×N4 + 0.10×N5 + 0.10×N6 + 0.10×N7) / 10
         = (0.20×?? + 0.15×?? + 0.10×?? + 0.10×?? + 0.10×??) / 10
         = ?? / 10 = ??
R_risk = [查表] = ??

BonusPts = ?? → B_bonus = [查表] = ??

P_penalty = 5×?? + 3×?? + 2×?? + 2×?? + 3×?? = ??

SS = 100 × ?? × ?? × ?? × ?? - ?? = ??

CF = ??^0.20 × ??^0.15 × ??^0.15 × ??^0.15 × ??^0.20 × ??^0.15
  = ?? × ?? × ?? × ?? × ?? × ?? = ??

σ = ±??, ±??, ±??, ±??, ±??, ±??
sum_of_squares = ??+??+??+??+??+?? = ?? → HU = ±?? [查表]

NoPostRiskLoad = (
  0.20×N1 + 0.15×N2 + 0.10×N3 + 0.15×N4
+ 0.10×N5 + 0.10×N6 + 0.10×N7 + 0.10×N8
) / 10
= (0.20×?? + 0.15×?? + 0.10×?? + 0.15×?? + 0.10×?? + 0.10×?? + 0.10×?? + 0.10×??) / 10
= ?? / 10 = ??
权重和 = 0.20+0.15+0.10+0.15+0.10+0.10+0.10+0.10 = 1.00 ✓
BaseNoPostGate = [查表] = ??
Cap Rules: [列出] → FinalNoPostGate = ??

PostReadyScore = (0.20×?? + 0.20×?? + 0.15×?? + 0.15×?? + 0.15×?? + 0.15×??) / 5 × 100 = ??
```

---

## 六、修正后的 SnapStand 案例完整验算

### 6.1 输入假设

```
产品: SnapStand MagSafe Phone Grip Stand
品牌: SnapStand
价格: $15-50
市场: US
品类: B 3C
模式: 标准
ICS: 0/10（全部假设）
```

### 6.2 Q1-Q7

```
Q1=5 Q2=5 Q3=5 Q4=5 Q5=5 Q6=5 Q7=5
（Q7=5: 主体简单✓ 文字依赖低✓ 动作不需精准✓ 光线空间简单✓ 产品外观稳定✓）
```

### 6.3 动态权重

```
基础: Q1=0.20 Q2=0.20 Q3=0.12 Q4=0.13 Q5=0.15 Q6=0.10 Q7=0.10
Δ B3C: Q2+0.05 Q7+0.03 Q4-0.03
Δ US:  Q1+0.03 Q4+0.02 Q3-0.02
Δ $15-50: 无
Δ 标准: 无

原始: Q1=0.23 Q2=0.25 Q3=0.10 Q4=0.12 Q5=0.15 Q6=0.10 Q7=0.13
总和: 1.08
归一化: Q1=0.213 Q2=0.231 Q3=0.093 Q4=0.111 Q5=0.139 Q6=0.093 Q7=0.120
```

### 6.4 验算

```
U_creative  = sqrt(1.00 × 1.00) = 1.000
U_product   = sqrt(1.00 × 1.00) = 1.000
U_execution = sqrt(1.00 × 1.00) = 1.000
U_delivery  = 1.000
U_domain    = 0.35×1.000 + 0.25×1.000 + 0.25×1.000 + 0.15×1.000 = 1.000

G_hook=1.00 G_product=1.00 G_reliability=1.00 G_market=1.00 G_nopost=1.00(不激活)
G_gate = 1.000

RiskLoad = (0.20×10 + 0.15×6 + 0.10×6 + 0.10×3 + 0.10×3) / 10
         = (2.00 + 0.90 + 0.60 + 0.30 + 0.30) / 10
         = 4.10 / 10 = 0.41
R_risk = 查表 0.40 → 0.905

BonusPts = 8 → B_bonus = 查表 6+ → 1.060

P_penalty = 5×1 + 3×0 + 2×0 + 2×1 + 3×0 = 7

SS = 100 × 1.000 × 1.000 × 0.905 × 1.060 - 7
   = 100 × 0.959 - 7
   = 95.9 - 7
   = 88.9
clamp(88.9, 0, 100) = 88.9

CF = 0.986 × 0.976 × 0.989 × 1.000 × 1.000 × 0.958
   = 0.986 × 0.976 = 0.962
   × 0.989 = 0.952
   × 1.000 = 0.952
   × 1.000 = 0.952
   × 0.958 = 0.912

σ = ±3, ±1, ±1, ±1, ±5, ±5
sum = 9+1+1+1+25+25 = 62 → 查表 50-64 → ±8

NoPostRiskLoad = (
  0.20×10 + 0.15×3 + 0.10×3 + 0.15×6
+ 0.10×6 + 0.10×3 + 0.10×3 + 0.10×3
) / 10
= (2.00 + 0.45 + 0.30 + 0.90 + 0.60 + 0.30 + 0.30 + 0.30) / 10
= 5.15 / 10 = 0.515
权重和 = 1.00 ✓
BaseNoPostGate = 查表 0.50 → 0.69
Cap: reserved for post-production text → ≤ 0.60
FinalNoPostGate = 0.60

PostReadyScore = (0.20×5 + 0.20×5 + 0.15×4 + 0.15×5 + 0.15×5 + 0.15×4) / 5 × 100
               = (1.0+1.0+0.6+0.75+0.75+0.6) / 5 × 100
               = 4.70 / 5 × 100 = 94.0
```

### 6.5 修正后核心快照

```
StructureScore: 88.9 ± 8 / 100
等级: 强候选
CF: 0.91（评分可靠性，不参与SS）
Q1-Q7: 5/5, 5/5, 5/5, 5/5, 5/5, 5/5, 5/5
NoPostGate: 0.60 | NoPostReady: false | ClaimLevel: C
PostReadyScore: 94.0 | PostReady: true | ClaimLevel: A
四象限: NoPostReady=false / PostReady=true
```

### 6.6 与 v3.0/v3.1 的数值对比

| 项目 | v3.0 | v3.1 | v3.2 | 变化原因 |
|:--|:--|:--|:--|:--|
| Q7 | 4/5 | 4/5 | **5/5** | 边界澄清：CTA后期不影响Q7 |
| U_execution | 0.894 | 0.894 | **1.000** | Q7=5级联 |
| U_domain | 0.963 | 0.974 | **1.000** | Q7=5级联 |
| RiskLoad | 1.90 | 0.615 | **0.41** | 权重统一 |
| R_risk | 0.954 | 0.861 | **0.905** | RiskLoad修正 |
| SS | 86.4 | 81.9 | **88.9** | 全部修正级联 |
| CF | 0.82 | 0.89 | **0.91** | Q7=5级联 |
| HU | ±4 | ±9 | **±8** | Q7=5→σ_gen=±1 |
| PostReadyScore | 91.0 | 94.0 | **94.0** | 不变 |
| 等级 | 强候选 | 可用 | **强候选** | SS回到85+ |

---

## 七、v3.2 状态机（与 v3.1 相同，Score Verification 更新）

```
[状态 3.25] Score Verification（v3.2 更新版）

Step 1:  U_domain（四域效用）
Step 2:  G_gate（门控乘数）
Step 3:  RiskLoad + R_risk（风险折扣，使用 N 权重一致的五项子集）
Step 4:  B_bonus（饱和奖励）
Step 5:  P_penalty（线性惩罚）
Step 6:  StructureScore
Step 7:  CF（置信度）
Step 8:  HeuristicUncertainty（σ 合成查表）
Step 9:  PostReadyScore
Step 10: NoPostRiskLoad（分项加总，权重和=1.00验证）← v3.2 新增
Step 11: BaseNoPostGate（查表）← v3.2 新增
Step 12: Cap Rules + FinalNoPostGate ← v3.2 新增

规则:
  - 每步必须写出完整算式和中间结果
  - 若任何值与状态 3.1 初始计算偏差 > 0.02，以验算值为准
  - Step 10 必须验证权重和 = 1.00
```

---

## 八、完整系统规则

以下部分与 v3.1 完全相同，仅列出编号和标题，完整内容参见 v3.1：

```
§一   角色与交付物（+v3.2 Q7 边界澄清引用）
§二   铁律 15 条
§三   输入要求与 InputCompleteness（+ICS≤4 强制警告）
§四   状态机（+Step 10-12 更新）
§五   候选搜索（类型 + 互异性约束）
§六   评分体系
  6.1  FeatureScore Q1-Q7（+Q7 边界澄清）
  6.2  动态权重
  6.3  四域效用
  6.4  门控乘数
  6.5  MarketFit
  6.6  风险折扣（+v3.2 权重统一）
  6.7  Bonus 查表
  6.8  OutcomePenalty
  6.9  StructureScore 公式
  6.10 CF（+幂函数查表）
  6.11 HeuristicUncertainty（+σ合成查表）
  6.12 分数范围
§七   NoPostGate v3（+v3.2 权重归一）
§八   PostReady v3
§九   NoPostGate 与 PostReady 关系（四象限）
§十   Score-Guided 搜索收敛（诊断/映射/Repair/Enhance/接受回滚/Winner/终止）
§十一 编译器规则集（FatalRed/RepairableRed/StyleRed/Y1-Y9）
§十二 门控系统（D1/D2/D7 标尺）
§十三 CriticPass + 自然度检查
§十四 辅助 A1-A6 + 创意 C1-C4 + 自检钩子
§十五 投放资产生成
§十六 知识库 KB-1~18
§十七 输出模板（投放版 + 完整版 + v3.2 验算行）
§十八 "还能更好吗"二次搜索
§十九 降级总表
§二十 数学结构 7 层
§二十一 生产说明 PS-1~6
§二十二 Anti-Pseudoscience 声明
```

---

## 九、版本历史

| 版本 | 核心变更 |
|:--|:--|
| v4.1-v8.2 | 评估体系演进 |
| v9.0-v1.0 | 范式转换→编译器+KB18+PS6 |
| v1.1-v1.5 | 行为规则+OVS+强搜索+FeatureScore+Growth Delivery |
| v1.6-v1.6.1 | StructureScore+四域+门控+CF+Red分级+HU+终止证明 |
| v2.0 | StructureScore v2 + Score-Guided + NoPostGate v2 + ICS |
| v3.0 | 双门控分离 + NoPostGate v3 + PostReady v3 + 四象限 |
| v3.1 | Score Verification + 验算行 + ICS警告 + 查表替代 + 数值校准 |
| **v3.2** | **Q7边界澄清 + RiskLoad权重统一 + NoPostRiskLoad归一1.00 + 验算行增加NoPost分项 + 数值再校准(SS≈89/CF≈0.91/HU≈±8)** |

---

## 十、一句话定位

```
Seedance 2.0 TikTok Growth Prompt Compiler v3.2
= 结构质量审查器 + 投放交付编译器 + Score-Guided 搜索收敛 + 双门控 + 验算层

v3.2 的核心改进:
  1. Q7 只评估画面生成可靠性，不再与 NoPostGate 混淆
  2. RiskLoad 权重与 N 维度权重一致
  3. NoPostRiskLoad 权重归一到 1.00
  4. 验算行覆盖全部计算链，包括 NoPostRiskLoad 分项加总
  5. 修正后 SnapStand 案例: SS≈89, CF≈0.91, HU≈±8, PostReady=94
```
