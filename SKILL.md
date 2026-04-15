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
│  [13-15s] CTA — download app             │
│                                          │
│  Template: date%3 → 0=A 1=B 2=C         │
│  Safety:   Center 60%, no edge text      │
│  End with: "No Chinese text anywhere"    │
└──────────────────────────────────────────┘
```
