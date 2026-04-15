---
name: tiktok-ad-video-generator
description: >
  End-to-end AI ad video production pipeline for e-commerce apps via Jimeng (jimeng.jianying.com) Seedance 2.0.
  Covers product selection, cinematic prompt engineering, video submission, multi-platform ad copy,
  and quality evaluation. Use when the user wants to generate TikTok/Reels/Shorts ad videos for
  product promotion, create video ad campaigns, or automate daily ad content production.
  Trigger phrases: "generate ad video", "create TikTok ad", "product video", "广告视频", "生成视频",
  "视频素材", "Jimeng video", "Seedance prompt", "ad creative", "video ad campaign".
---

# TikTok Ad Video Generator

An end-to-end skill for producing high-conversion short-form ad videos (9:16, 15s) via **Jimeng AI (jimeng.jianying.com)** Seedance 2.0 model. Battle-tested over 80+ videos across 8 production days.

---

## Table of Contents

1. [Overview & Philosophy](#overview--philosophy)
2. [Platform & Model Configuration](#platform--model-configuration)
3. [Product Selection Methodology](#product-selection-methodology)
4. [Video Structure — The 15-Second Formula](#video-structure--the-15-second-formula)
5. [Script Templates (3-Template Rotation)](#script-templates-3-template-rotation)
6. [Prompt Engineering Masterclass](#prompt-engineering-masterclass)
7. [Branding Integration System](#branding-integration-system)
8. [Video Quality Evaluation Rubric](#video-quality-evaluation-rubric)
9. [Ad Copy Generation](#ad-copy-generation)
10. [Multi-Platform Distribution](#multi-platform-distribution)
11. [Daily Execution Workflow](#daily-execution-workflow)
12. [Points & Cost Management](#points--cost-management)
13. [Troubleshooting & Lessons Learned](#troubleshooting--lessons-learned)

---

## Overview & Philosophy

### Core Principle
> **One cinematic ad video per day → distributed to ALL platforms → drive app downloads.**

This is NOT organic content creation. This is **paid ad creative production**. The difference matters:
- Organic TikTok = algorithm-dependent, shadowban risk, engagement farming
- Paid ad creative = quality over quantity, controlled distribution, measurable ROI

### What This Skill Produces
- 1 × 15-second cinematic ad video (via Jimeng Seedance 2.0)
- 1 × universal ad copy (adaptable to TikTok, Meta, Google, YouTube, Pinterest, X, Snapchat)
- Daily execution checklist for handoff to ad placement team

### Division of Labor
| Role | Responsibility |
|------|---------------|
| **AI Agent** | Product selection → Prompt writing → Jimeng submission → Ad copy output |
| **User** | Download generated video → Hand off to ad placement team |
| **Ad Team** | Upload to ad platforms → Set budget/targeting/bidding → Manage campaigns |

---

## Platform & Model Configuration

### Fixed Parameters (DO NOT CHANGE)

| Parameter | Value | Rationale |
|-----------|-------|-----------|
| Platform | jimeng.jianying.com | Best Chinese AI video generator, Seedance model family |
| Model | **Seedance 2.0 Standard** | Cost-effective at 120pts vs 210pts for VIP. Quality sufficient for ads. |
| Mode | 全能参考 (Universal Reference) | Best prompt-following fidelity |
| Aspect Ratio | **9:16** (vertical) | Native format for TikTok/Reels/Shorts/Stories |
| Duration | **15 seconds** | Optimal for paid ads — long enough to tell a story, short enough for retention |
| Cost | 120 points per video | Standard version pricing |
| Language | **English only** | Zero Chinese characters in prompts or generated content |

### Why NOT VIP/Pro/Fast?
- **VIP (210pts)**: 75% more expensive, marginal quality gain for ad use case
- **Pro**: Overkill for 15s product ads
- **Fast**: Lower quality, not suitable for cinematic look

### Submission Workflow (Browser)
1. Navigate to `https://jimeng.jianying.com/ai-tool/generate?type=video`
2. Verify model = Seedance 2.0 (NOT VIP) — click model selector if wrong
3. Verify settings: 全能参考 / 9:16 / 15s
4. Click prompt text area (ProseMirror editor)
5. Use `type` action (NOT `fill`) to enter prompt
6. Click 生成 (Generate) button
7. Screenshot to confirm queued status + remaining points

**CRITICAL**: Use `type` not `fill` for the text area — ProseMirror editors don't respond to fill actions.

---

## Product Selection Methodology

### Selection Criteria

| Dimension | Requirement | Why |
|-----------|-------------|-----|
| **Visual Wow Factor** | HIGH — glowing, transforming, futuristic, satisfying | Must stop scrolling in <1 second |
| **Price Anchoring** | App price < 30% of competitor retail | Creates irresistible "deal shock" |
| **Demo Value** | Clear before/after or transformation | 7-second demo segment needs visual contrast |
| **Price Range** | $5–$60 | Sweet spot for impulse purchase on discount app |
| **Category** | User-defined niche (e.g. home gadgets, beauty tech) | Vertical focus builds algorithmic affinity |
| **No Repeats** | Never reuse any previously featured product | Prevents audience fatigue |

### High-Performing Product Categories (Ranked)
1. **Beauty Tech** — LED masks, facial massagers, skin scrubbers, hair tools
2. **Smart Home Gadgets** — sensor lights, smart humidifiers, robot cleaners
3. **Personal Care Devices** — electric toothbrushes, scalp massagers, neck devices
4. **Kitchen Tech** — portable blenders, smart scales, milk frothers
5. **Lifestyle Gadgets** — wireless speakers, phone stands, desk accessories

### Product Selection Process
1. Browse the e-commerce app/website product catalog
2. Filter by target category
3. Cross-check against historical product list (avoid repeats)
4. Evaluate visual demo potential — can you imagine a satisfying 7-second slow-motion sequence?
5. Calculate price anchoring ratio — is the retail equivalent 3x+ more expensive?
6. Select the single best candidate

### Competitor Price Research
To validate price anchoring, check competitor retail prices using these sources (in order):
1. **Amazon US** — Search product name → Note top brand price or "List Price"
2. **Walmart.com** — Cross-reference for confirmation
3. **Brand official website** — If a known brand equivalent exists (e.g. Dyson, SkinGym, CurrentBody)
4. **Google Shopping** — Quick multi-retailer price scan

**Validation rule**: App price must be **< 30%** of the best competitor retail price found.
Document both prices for the ad copy (e.g. "retail $89" vs "only $16.18").

### Product Usage Tracking
Maintain a running log of all products used to prevent repeats. See `references/product-tracker-template.md` for the full tracking table format.

**Minimum tracking per product**: Product name, date, price, category, template used, score.

**Category balance**: No single category should exceed 50% of total videos. If Beauty Tech dominates, shift to Home Gadgets for the next cycle.

**Similar product spacing**: The same *type* of product (e.g. two different facial massagers) should be spaced at least 14 days apart, even if they are technically different products.

### Red Flags — Skip These Products
- Commodities with no visual differentiation (plain cables, basic containers)
- Products that look identical across brands (generic phone cases)
- Items requiring complex setup to demonstrate (furniture, large appliances)
- Text-heavy products (books, stationery with text)
- Products with safety/compliance concerns in ads (supplements, medical devices)

---

## Video Structure — The 15-Second Formula

```
┌─────────────────────────────────────────────────────┐
│ [0-3s]   HOOK — Visual Impact                       │
│          Must stop scrolling. Shock, intrigue,       │
│          or relatable pain point.                    │
├─────────────────────────────────────────────────────┤
│ [3-10s]  DEMO — Cinematic Product Showcase           │
│          Slow-motion close-ups. Material textures.   │
│          Function demonstration. Before/after.       │
├─────────────────────────────────────────────────────┤
│ [10-13s] PRICE — Anchoring Reveal                    │
│          Competitor high price → App low price.      │
│          Bold red price tag. "Free Shipping" badge.  │
├─────────────────────────────────────────────────────┤
│ [13-15s] CTA — Call to Action                        │
│          App logo + "Download [App] App"             │
│          "Free Shipping Worldwide"                   │
└─────────────────────────────────────────────────────┘
```

### Why This Structure Works
- **0-3s Hook**: TikTok's algorithm measures "loop rate" — if users don't stop, they never see the ad. The hook is the single most important element.
- **3-10s Demo**: 7 seconds of pure product cinema. This is where Seedance 2.0 shines — cinematic slow-motion, dramatic lighting, satisfying textures.
- **10-13s Price**: The "price shock" moment. Showing competitor's $89 → your app's $16 creates an irresistible impulse.
- **13-15s CTA**: Clean, centered, unmissable. Logo + download instruction + free shipping.

---

## Script Templates (3-Template Rotation)

Rotate templates using `date % 3` to ensure variety:

### Template A — Price Anchoring (date % 3 = 0)
**Story arc**: "Look how expensive it is elsewhere → look how cheap it is on our app"

```
Cinematic product ad, 9:16 vertical, premium studio lighting.
HOOK: [Competitor scene showing high price]. Bold red price tag centered on screen:
"[Competitor]: $XX.XX".
Dramatic flash transition to [App] UI — sleek white interface,
[APP_LOGO_DESCRIPTION], [product] centered on white background.
[Premium product close-ups: material, texture, light reflections].
[Product in-use scene: slow-motion, cinematic lighting].
Price reveal centered on screen: bold red "$X.XX" zooms in,
green "Free Shipping Worldwide" badge pulses. Orange "BUY NOW!" button.
All text and UI elements stay in the center 60% of the frame.
Final frame: [App] icon on phone screen, text overlay centered:
"Download [App] — Factory Prices, Free Shipping."
No Chinese text anywhere.
```

### Template B — Lifestyle Transformation (date % 3 = 1)
**Story arc**: "Pain point → product solves it → upgraded life"

```
Aspirational lifestyle ad, 9:16 vertical, warm cinematic color grading.
HOOK: [Relatable pain point scene, soft lighting, emotional resonance].
Elegant transition: [Product appears, scene upgrades to aspirational setting].
[Product in-use: slow-motion close-ups showing texture and effect].
[Satisfaction/enjoyment moment after using the product].
Lower-third overlay centered: [App] mockup — [APP_LOGO_DESCRIPTION],
bold red "$X.XX", green "Free Shipping" badge.
All text and UI elements stay in the center 60% of the frame.
Final frame centered: "Your upgrade starts at $X — Download [App] App."
No Chinese text anywhere.
```

### Template C — Tech Reveal (date % 3 = 2)
**Story arc**: "What is this mysterious thing? → Reveal! → It does something amazing"

```
Tech reveal ad, 9:16 vertical, dark moody lighting with neon accents.
HOOK: Extreme close-up of [unique product detail] — mysterious, intriguing.
Camera slowly pulls back revealing the full product — [full product description].
[Function demonstration: LEDs activate / mechanical movement / tech effect, slow-motion].
Split-screen: [without product state] vs [with product upgraded state].
[App] UI centered: [APP_LOGO_DESCRIPTION], bold red "$X.XX",
green "Free Shipping Worldwide" badge, orange "BUY NOW!" button.
All text and UI elements stay in the center 60% of the frame.
Final text centered: "The future costs $X — Download [App] App."
No Chinese text anywhere.
```

---

## Prompt Engineering Masterclass

### The 8 Rules of Seedance Prompt Writing

1. **ENGLISH ONLY** — Zero Chinese characters anywhere in the prompt. Seedance handles English prompts reliably; Chinese can cause rendering artifacts.

2. **SCENE-BY-SCENE SEQUENTIAL** — Write the prompt as a chronological storyboard. Each sentence = one shot. Don't describe the overall video abstractly.

3. **SPECIFY CAMERA AND LIGHTING** — "slow-motion close-up", "premium studio lighting", "warm cinematic color grading", "dark moody with neon accents". Without these, Seedance defaults to flat, amateur-looking output.

4. **EMBED UI ELEMENTS AS VISUAL DESCRIPTIONS** — Don't say "show the app UI". Instead: "sleek white interface, bold red '$16.18', green 'Free Shipping Worldwide' badge, orange 'BUY NOW!' button". Seedance renders described UI elements as part of the scene.

5. **CENTER 60% SAFETY ZONE** — Add "All text and UI elements stay in the center 60% of the frame" to EVERY prompt. Platform UI (like/share/comment buttons, progress bars) overlays the edges. Without this rule, your CTA gets hidden behind TikTok's UI.

6. **LOGO AS VISUAL DESCRIPTION** — Don't upload logo images (Jimeng blocks file uploads in automated workflows). Instead, describe the logo precisely: colors, shapes, icons, text. Example: "orange-red rounded square icon with a white shopping cart, u-shaped handle, two white wheels."

7. **"NO CHINESE TEXT ANYWHERE"** — Always end the prompt with this instruction. Seedance occasionally inserts Chinese text without this explicit prohibition.

8. **MATERIAL AND TEXTURE DETAILS** — "brushed aluminum surface", "matte silicone finish", "translucent LED glow", "marble countertop". These details make the difference between a cheap-looking render and a cinematic ad.

### Prompt Structure Template
```
[Visual style declaration], 9:16 vertical, [lighting style].
HOOK: [0-3s scene description — maximum visual impact].
[Transition description].
[3-10s product demo — 2-3 sentences of cinematic action].
[Price/brand UI elements — described as visual overlays, centered].
All text and UI elements stay in the center 60% of the frame.
Final frame: [CTA text centered on screen].
No Chinese text anywhere.
```

### Prompt Length Guide
| Element | Recommended Length |
|---------|-------------------|
| Full prompt | **150–300 words** (sweet spot for Seedance 2.0) |
| Hook description | 2–3 sentences |
| Product demo section | 3–5 sentences |
| Price/brand overlay | 2–3 sentences |
| CTA + safety rules | 2–3 fixed sentences |

- **Too short** (<100 words): Seedance fills blanks with generic, uncontrolled content
- **Too long** (>400 words): Model ignores later instructions, produces incoherent results
- **Sweet spot** (150–300 words): Enough detail for cinematic quality, consistent execution

> See `references/cinematic-vocabulary.md` for a full library of camera, lighting, transition, material, and scene-setting terms to build prompts from.

### What NOT To Do
- ❌ "Make a TikTok video about this product" — too vague, Seedance will produce generic content
- ❌ Including Chinese characters anywhere — causes rendering issues
- ❌ Describing abstract concepts — "show the value proposition" means nothing to a video model
- ❌ Requesting specific fonts or exact text rendering — AI video models don't reliably render text
- ❌ Uploading images as reference — Jimeng blocks automated uploads (security policy)
- ❌ Using more than 400 words — model loses coherence in later sections

---

## Branding Integration System

### Required Brand Elements (customize per project)

| Element | How to Integrate |
|---------|-----------------|
| **App Logo** | Describe precisely in text: shape, colors, icon details. No image upload. |
| **Primary Color** | Specify hex codes in prompt (e.g. "orange #FF4500 gradient") |
| **Price Display** | "bold red '$X.XX'" — always bold, always red, always centered |
| **Free Shipping Badge** | "green 'Free Shipping Worldwide' badge" — green conveys trust |
| **CTA Button** | "orange 'BUY NOW!' button" — high-contrast action color |
| **App Name** | In final CTA: "Download [App Name] App" |

### Logo Description Template
When the user provides a logo image, analyze it and create a precise text description:
```
[shape] [color/gradient] [corner style] icon with [main graphic element] in the center —
[graphic details: handle shape, decorative elements, sub-elements].
[Additional text elements if any].
```

Example:
> A rounded-corner square icon with an orange-to-red gradient background (bright orange top-left fading to deeper red bottom-right). In the center, a white stylized shopping cart icon — the cart body shaped like a lowercase "u" with a small notch/handle on the top-left edge, two round white wheels at the bottom. No text on the logo icon itself.

---

## Video Quality Evaluation Rubric

Score each generated video on these 8 dimensions (1-5 scale):

### Dimension 1: Hook Effectiveness (0-3s)
| Score | Criteria |
|-------|----------|
| 5 | Instantly arresting — would stop even fast-scrolling users. Strong visual surprise or emotional hook. |
| 4 | Eye-catching, clear opening shot that creates curiosity. |
| 3 | Decent opening but doesn't demand attention. Could be scrolled past. |
| 2 | Weak opener, generic scene, nothing distinctive. |
| 1 | No clear hook, video starts with irrelevant or confusing content. |

### Dimension 2: Cinematic Quality
| Score | Criteria |
|-------|----------|
| 5 | Professional commercial quality — beautiful lighting, smooth motion, rich textures. |
| 4 | High quality with minor imperfections (slight lighting inconsistency, minor artifacts). |
| 3 | Acceptable quality, looks AI-generated but not distractingly so. |
| 2 | Noticeable AI artifacts — uncanny valley, distorted objects, flickering. |
| 1 | Poor quality — major artifacts, unrecognizable product, broken physics. |

### Dimension 3: Product Clarity
| Score | Criteria |
|-------|----------|
| 5 | Product is immediately recognizable, key features clearly visible, material/texture conveyed. |
| 4 | Product is clear, most features visible, minor details may be off. |
| 3 | Product recognizable but some key features are unclear or missing. |
| 2 | Product is vaguely recognizable but details are wrong or confusing. |
| 1 | Product is unrecognizable or looks nothing like the real item. |

### Dimension 4: Brand Element Rendering
| Score | Criteria |
|-------|----------|
| 5 | Logo, price tag, badges, and CTA are all clearly visible and correctly positioned. |
| 4 | Most brand elements present and readable, minor positioning issues. |
| 3 | Some brand elements visible but partially obscured or incorrectly rendered. |
| 2 | Brand elements barely visible or significantly distorted. |
| 1 | No recognizable brand elements in the video. |

### Dimension 5: Price Anchoring Impact
| Score | Criteria |
|-------|----------|
| 5 | Price comparison creates strong "wow" reaction — the deal feels irresistible. |
| 4 | Clear price contrast that makes the deal attractive. |
| 3 | Price is shown but the anchoring effect is weak (competitor price not prominent enough). |
| 2 | Price barely visible or poorly positioned. |
| 1 | No price anchoring at all. |

### Dimension 6: CTA Clarity
| Score | Criteria |
|-------|----------|
| 5 | CTA is unmissable, perfectly centered, clearly reads "Download [App]", free shipping visible. |
| 4 | CTA visible and readable, minor positioning adjustment needed. |
| 3 | CTA present but may be partially obscured or too small. |
| 2 | CTA barely readable or in a bad position. |
| 1 | No CTA or completely illegible. |

### Dimension 7: Safety Zone Compliance
| Score | Criteria |
|-------|----------|
| 5 | All text/UI elements in center 60% — nothing near edges. Would work on all platforms. |
| 4 | Most elements centered, 1-2 minor elements slightly toward edge. |
| 3 | Some important elements near edges — would be partially hidden on some platforms. |
| 2 | Key text/CTA near edges — would be hidden behind platform UI on most platforms. |
| 1 | Critical elements at edges — completely unusable on all platforms. |

### Dimension 8: Overall Ad Effectiveness
| Score | Criteria |
|-------|----------|
| 5 | Would confidently run this as a paid ad. Compelling, professional, clear message. |
| 4 | Good ad quality, minor improvements possible but usable as-is. |
| 3 | Passable ad, would use if no better option but room for improvement. |
| 2 | Below ad quality threshold — needs regeneration with revised prompt. |
| 1 | Unusable — regenerate with completely different approach. |

### Scoring Guide
- **35-40**: Excellent — use immediately
- **28-34**: Good — use as-is or with minor edits
- **20-27**: Acceptable — consider regenerating if points allow
- **Below 20**: Reject — regenerate with revised prompt

---

## Ad Copy Generation

### Universal Ad Copy Template
```
[Hook: 1 sentence — price shock OR pain point resonance]
[Benefit: 1 sentence — core product value proposition]
Only $X.XX (retail $XX) | Free Shipping Worldwide
Download [App] App

#[AppName] #[Niche1] #[Niche2] #TikTokMadeMeBuyIt #FactoryPrice #FreeShipping
```

### Platform Adaptation Guide

| Platform | Adaptation | Character Limit |
|----------|-----------|----------------|
| **TikTok** | Use as-is | 2,200 chars |
| **Instagram/Facebook** | Add direct App Store link | 2,200 chars |
| **YouTube Shorts** | Condense to 2 sentences + CTA | 100 chars (title) |
| **Pinterest** | Add product keyword tags (5-10) | 500 chars |
| **X (Twitter)** | Compress to 280 chars total | 280 chars |
| **Snapchat** | Use as-is | 200 chars |

### Hook Sentence Formulas (rotate for variety)
1. **Price Shock**: "I found the [retailer] version of this for $X.XX — but this one is only $Y.YY."
2. **Confession**: "I spent $XXX on [category] that did nothing — this $X device changed everything."
3. **Question**: "Why is nobody talking about this $X [product]?"
4. **Social Proof**: "This [product] has 50K+ orders on [App] and it's only $X."
5. **Comparison**: "[Brand] charges $XX for this. [App] has the same quality for $X."

---

## Multi-Platform Distribution

### One Video → All Platforms
The same 9:16 / 15s video works natively on ALL major ad platforms:

| Platform | Format Support | Min Budget | Notes |
|----------|---------------|------------|-------|
| TikTok Ads | 9:16 native | $50/campaign | Best for discovery, viral potential |
| Meta (FB/IG) | Reels/Stories native | $1-5/day | Largest audience, best targeting |
| Google Ads | YouTube Shorts | $20+/day recommended | App Campaigns automated |
| Snapchat | 9:16 native | $5/day | Excellent for young discount shoppers |
| Pinterest | Idea Pins | $1/day | Slower conversion, good for lifestyle |
| X (Twitter) | Video ads | Requires X Premium | Less optimized for app installs |

### Platform Priority
1. **TikTok + Meta** (HIGH) — Start here, largest ROI for e-commerce apps
2. **Snapchat** (HIGH) — Underrated for discount shopping audience
3. **Google/YouTube** (MEDIUM) — App Campaign automates everything
4. **Pinterest + X** (LOW) — Supplementary reach

### Safety Zone Rule (Critical)
> **All text, price tags, CTAs, and logos must stay in the center 60% of the frame.**
> Top/bottom/left/right 20% margins are reserved for platform UI overlays.

This is platform-universal — every short-form video platform overlays UI on the edges:
- TikTok: like/comment/share buttons (right), description text (bottom), progress bar (bottom)
- Instagram Reels: engagement buttons (right), caption (bottom)
- YouTube Shorts: engagement buttons (right), title (bottom)

---

## Daily Execution Workflow

### Step-by-Step Procedure

```
1. CHECK POINTS
   → Visit jimeng.jianying.com → Check points balance
   → Need ≥120 points. If insufficient, STOP and notify user to recharge.

2. SELECT PRODUCT
   → Browse e-commerce app/site product catalog
   → Filter by target niche category
   → Cross-check against historical product list (no repeats)
   → Pick 1 product with highest visual wow + price anchoring potential

3. DETERMINE TEMPLATE
   → Calculate: today's date % 3
   → 0 = Template A (Price Anchoring)
   → 1 = Template B (Lifestyle Transformation)
   → 2 = Template C (Tech Reveal)

4. WRITE PROMPT
   → Fill selected template with product details
   → Include brand elements (logo description, colors, price, badges)
   → Include safety zone instruction
   → Include "No Chinese text anywhere"
   → All content in English

5. SUBMIT TO JIMENG
   → Navigate to Jimeng video generation page
   → Verify: Seedance 2.0 Standard / 全能参考 / 9:16 / 15s
   → Type prompt into text area
   → Click Generate
   → Screenshot confirmation

6. GENERATE AD COPY
   → Write universal ad copy using template
   → Include platform adaptation tips
   → Include hashtags

7. OUTPUT DAILY CHECKLIST
   → Points balance
   → Product selected + price
   → Template used
   → Submission status
   → Ad copy
   → User action items (download + handoff)
```

### Video Download & File Naming
After the user downloads the generated video from Jimeng, use this naming convention:
```
[APP]_ad_d[DAY]_[TEMPLATE]_[product-short-name]_[YYYYMMDD].mp4
```
Examples:
- `huopan_ad_d8_B_led-neck-device_20260415.mp4`
- `huopan_ad_d9_C_flame-humidifier_20260416.mp4`

This ensures the ad placement team can:
- Sort videos chronologically
- Identify the template style for A/B testing analysis
- Match the video to its ad copy quickly

### Daily Output Checklist Template
```markdown
## ✅ AI Completed Today
- [ ] Points balance check: [balance] points
- [ ] Product selected: [product name] $[price]
- [ ] Script template: [A/B/C] — [template name]
- [ ] Prompt generated and submitted to Jimeng
- [ ] Video status: Queued / Insufficient points
- [ ] Ad copy generated

## 📋 Your Action Items
- [ ] Download video from Jimeng once generation completes
- [ ] Hand off video + ad copy to ad placement team
```

---

## Points & Cost Management

### Cost Structure
| Item | Value |
|------|-------|
| Per video (Seedance 2.0 Standard, 15s) | 120 points |
| Per month (30 videos) | 3,600 points |
| Basic membership monthly grant | ~1,080 points |
| Monthly shortfall to purchase | ~2,520 points |

### Cost Optimization Rules
1. **Never use VIP model** unless Standard produces unacceptable quality — saves 90pts/video (75% markup for marginal gain)
2. **Don't regenerate unless score < 20/40** — each retry costs 120pts
3. **Keep buffer of 500+ points** — prevents workflow interruption
4. **Track daily consumption** — log balance before and after each submission

### Points Alert Thresholds
- **🟢 500+ points**: Safe, proceed normally
- **🟡 200-499 points**: Warn user to plan recharge
- **🔴 < 200 points**: Only 1 video possible, must recharge before next session
- **⛔ < 120 points**: Cannot generate, STOP and notify user

---

## Troubleshooting & Lessons Learned

### Known Issues & Solutions

| Issue | Solution |
|-------|---------|
| **Image upload fails** (`UPLOAD_PATH_DENIED`) | Don't upload images — embed visual descriptions in prompt text instead |
| **Jimeng security blocks fetch()** | Cannot use browser console to inject images — text-only prompts |
| **ProseMirror editor doesn't respond to fill** | Use `type` action, not `fill`, when entering text via browser automation |
| **Chinese text appears in video** | Always end prompt with "No Chinese text anywhere" |
| **Text/CTA hidden behind platform UI** | Add "All text and UI elements stay in the center 60% of the frame" |
| **Product looks generic/unrecognizable** | Add material/texture details: "brushed aluminum", "translucent LED", "matte silicone" |
| **Video looks flat/amateur** | Specify lighting: "premium studio lighting", "cinematic color grading", "moody neon accents" |
| **Seedance defaults to VIP** | Manually check model selector before submission — click to switch to Standard |

### Strategy Evolution Log
This skill was refined through 8 production days:
- **Days 1-3**: 10 videos/day, all categories, organic TikTok → **FAILED** (shadowban, zero views)
- **Day 4-6**: Reduced to 1/day, still organic strategy → **FAILED** (low engagement)
- **Day 7**: Strategy pivot — abandoned organic, switched to paid ad production
- **Day 8+**: 1 cinematic ad/day, multi-platform paid distribution → **CURRENT STRATEGY**

Key lesson: **Don't fight the algorithm. Pay to reach your audience. Quality > quantity for paid ads.**

### Prompt Iteration Heuristic
If a video scores below threshold:
1. Identify the weakest dimension(s) from the evaluation rubric
2. Add MORE specific detail to that section of the prompt
3. Common fixes:
   - Weak hook → Add more dramatic/specific opening action
   - Poor product clarity → Add material/color/texture descriptors
   - Missing brand elements → Ensure logo description is detailed enough
   - Bad safety zone → Explicitly add "centered on screen" to each text element

---

## Quick Reference Card

```
┌──────────────────────────────────────────┐
│         DAILY VIDEO GENERATION           │
│                                          │
│  Model:    Seedance 2.0 Standard         │
│  Mode:     全能参考                       │
│  Ratio:    9:16                          │
│  Duration: 15s                           │
│  Cost:     120 pts/video                 │
│  Language: English only                  │
│                                          │
│  Structure:                              │
│  [0-3s]  Hook — stop the scroll          │
│  [3-10s] Demo — cinematic product show   │
│  [10-13s] Price — anchoring reveal       │
│  [
