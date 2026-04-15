# Viral Hook Pattern Library (爆款钩子特征库)

> **Purpose**: Before writing a Seedance 2.0 prompt, match the product to 1-2 high-potential hook types from this library. The selected hook determines the video's opening 0-3 seconds — the single most important factor for paid ad performance.
>
> **Iteration rule**: When a hook type gets 3+ consecutive positive outcomes (user selects it, or ad data shows high CTR), increase its Viral Index weight in internal tracking.
>
> **Automation note**: In cron/automated mode, the AI selects the best hook autonomously based on product category match. No user interaction required.

---

## Hook Type Quick Reference

| Hook Type | Core Psychological Trigger | Key Visual Elements for Prompt | Viral Index | Best Product Categories |
| :--- | :--- | :--- | :--- | :--- |
| **Cognitive Dissonance** (认知失调型) | Defies expectations, breaks common sense | Anti-physics phenomena, unexpected contrasts, microscopic zoom | ⭐⭐⭐⭐⭐ | Smart home gadgets, cleaning devices, stress toys |
| **Instant Result** (极简结果型) | Laziness dividend, one-step solution | Before/After rapid cut, single-hand operation, zero-step demo | ⭐⭐⭐⭐⭐ | Storage, kitchen tools, beauty shortcuts |
| **Price Anchoring** (价格锚点型) | Bargain psychology, value mismatch | Crossed-out high price animation, product quantity stacking, premium scene contrast | ⭐⭐⭐⭐ | Daily goods, fashion accessories, factory-direct items |
| **Emotional Bond** (情感绑架型) | Guilt, love, self-care | Gift-giving scene, family warmth, solo self-care moment | ⭐⭐⭐⭐ | Holiday gifts, women's care, pet products |
| **Visual Spectacle** (视觉奇观型) | ASMR satisfaction, OCD fulfillment | Slow-motion liquid pour, perfect cuts, extreme alignment | ⭐⭐⭐⭐ | Food/beverage, stationery, cutting tools |
| **Identity Tribe** (身份认同型) | Community belonging, social label | Specific persona markers ("new mom", "renter", "gym rat") | ⭐⭐⭐ | Niche verticals, interest community products |

---

## 15-Second Seedance 2.0 Script Structures by Hook Type

### 1. Cognitive Dissonance (认知失调型)
**Best for**: Products with a "wow, that's impossible" visual effect.

| Time | Content | Prompt Focus |
| :--- | :--- | :--- |
| 0-3s | Close-up of product producing a reality-defying effect (e.g. magic sponge erasing years of scale) | `extreme close-up, impossible cleaning result, viewer disbelief` |
| 3-10s | Rapid cuts: normal method fails → this product succeeds dramatically | `quick cuts, side-by-side comparison, dramatic difference` |
| 10-15s | Zoom out to satisfied user expression, product logo freeze frame | `reaction shot, freeze frame on product, brand overlay centered` |

**Prompt prefix**: `Mind-bending product reveal, Cognitive dissonance hook, "Wait, that actually works?" moment`

### 2. Instant Result (极简结果型)
**Best for**: Products where the transformation is visually instantaneous.

| Time | Content | Prompt Focus |
| :--- | :--- | :--- |
| 0-3s | One hand holds product, other hand shows dirty/messy scene (close-up pan) | `split attention, messy scene close-up, handheld movement` |
| 3-8s | Product touches surface → instant dissolve/absorb/transform | `instant transformation, one-touch solution, satisfying dissolve` |
| 8-15s | Camera pulls back revealing entire area spotless, no extra effort needed | `wide reveal, pristine result, effortless completion, no wipe needed` |

**Prompt prefix**: `Satisfying instant result, One-touch transformation, Lazy genius solution`

### 3. Price Anchoring (价格锚点型)
**Best for**: Products with a dramatic price gap vs retail competitors.

| Time | Content | Prompt Focus |
| :--- | :--- | :--- |
| 0-3s | Screen shows "$199 ???" which gets crossed out in red | `price tag animation, red X strike-through, centered text` |
| 3-8s | Stack of 10 identical products, text: "Factory direct, only $9.9" | `product stacking, quantity display, price reveal bold red` |
| 8-15s | Quick close-ups of quality details proving it matches the expensive version | `quality macro shots, material details, premium feel proof` |

**Prompt prefix**: `Price shock reveal, "How is this so cheap?" moment, Factory-vs-retail comparison`

### 4. Emotional Bond (情感绑架型)
**Best for**: Products that solve a personal pain point or make great gifts.

| Time | Content | Prompt Focus |
| :--- | :--- | :--- |
| 0-3s | Person looking tired, rubbing shoulders, desk cluttered | `tired expression, shoulder pain, messy environment, soft lighting` |
| 3-8s | Camera pans to gift-giver (or self-care moment), beautifully wrapped product appears | `gift reveal, beautiful packaging, warm lighting transition` |
| 8-15s | Using product → relaxed smile, text overlay: "You deserve this" | `relief moment, genuine smile, freeze frame with text overlay` |

**Prompt prefix**: `Emotional self-care moment, Gift-giving warmth, "Treat yourself" aesthetic`

### 5. Visual Spectacle (视觉奇观型)
**Best for**: Products with inherently satisfying visual/audio qualities.

| Time | Content | Prompt Focus |
| :--- | :--- | :--- |
| 0-3s | Macro shot of thick sauce flowing over food surface | `extreme macro, viscous liquid flow, slow-motion pour` |
| 3-10s | Cutting into food reveals molten/explosive filling (slow-motion) | `cross-section reveal, slow-motion explosion, ASMR texture` |
| 10-15s | First bite close-up with visible crunch, text: "Listen to the crunch" | `bite close-up, crunch moment, text overlay centered` |

**Prompt prefix**: `ASMR visual feast, Oddly satisfying, Sensory overload close-up`

### 6. Identity Tribe (身份认同型)
**Best for**: Products targeting a specific lifestyle or community.

| Time | Content | Prompt Focus |
| :--- | :--- | :--- |
| 0-3s | Bold text on screen: "Every renter's biggest pain" | `bold text overlay, identity callout, relatable hook` |
| 3-8s | Show typical problem for that identity (e.g. cramped counter, moldy corner) | `real-life problem scene, authentic messy environment` |
| 8-15s | Product appears → transforms space, text: "Landlord begged me to leave it behind" | `space transformation, humorous text, freeze frame result` |

**Prompt prefix**: `"This is for the [identity] crowd", Tribal callout, Niche community hook`

---

## Hook Selection Decision Tree (for automated/cron mode)

```
START → Analyze product category & visual features
  │
  ├─ Product has a "magic" visual effect? → Cognitive Dissonance ⭐⭐⭐⭐⭐
  ├─ Product shows instant before/after? → Instant Result ⭐⭐⭐⭐⭐
  ├─ Price gap vs retail > 70%? → Price Anchoring ⭐⭐⭐⭐
  ├─ Product is a gift / self-care? → Emotional Bond ⭐⭐⭐⭐
  ├─ Product has ASMR / satisfying visuals? → Visual Spectacle ⭐⭐⭐⭐
  └─ Product targets specific group? → Identity Tribe ⭐⭐⭐
  
  If multiple hooks match → Pick the one with highest Viral Index
  If tied → Prefer hooks NOT used in last 3 videos (variety rule)
```

---

## Hook Performance Tracking

Record each video's hook type and outcome. After accumulating data:

| Metric | Action |
| :--- | :--- |
| Hook selected 3+ times consecutively → | Increase its Viral Index weight |
| Hook consistently gets low scores (<25/40) → | Decrease weight, investigate prompt patterns |
| New hook type discovered from viral trends → | Add to this library with initial ⭐⭐⭐ rating |
| Same hook used 3 days in a row → | Force-switch to next best match (variety rule) |
