# Video Quality Evaluation Rubric — Quick Reference

Use this rubric to score generated videos on 8 dimensions (1-5 each, max 40).

## Scoring Sheet Template

```
Video: [Product Name] — $[Price]
Date:  [YYYY-MM-DD]
Template: [A/B/C]

| # | Dimension              | Score (1-5) | Notes |
|---|------------------------|-------------|-------|
| 1 | Hook Effectiveness     |             |       |
| 2 | Cinematic Quality      |             |       |
| 3 | Product Clarity        |             |       |
| 4 | Brand Element Render   |             |       |
| 5 | Price Anchoring Impact |             |       |
| 6 | CTA Clarity            |             |       |
| 7 | Safety Zone Compliance |             |       |
| 8 | Overall Ad Effectiveness|            |       |
| |   **TOTAL**              | **/40**     |       |

Decision: [ ] USE  [ ] REGENERATE  [ ] REVISE PROMPT
```

## Decision Thresholds

| Score Range | Decision | Action |
|-------------|----------|--------|
| 35-40 | ✅ Excellent | Use immediately, no changes needed |
| 28-34 | ✅ Good | Use as-is, note improvements for future prompts |
| 20-27 | ⚠️ Acceptable | Consider regenerating if points budget allows |
| Below 20 | ❌ Reject | Must regenerate — revise prompt addressing weak dimensions |

## Common Failure Patterns & Fixes

### Pattern: Low Hook Score (1-2)
**Symptom**: Opening scene is generic, doesn't create curiosity
**Fix**: Add more dramatic/specific action to the HOOK section. Use concrete visual actions, not abstract descriptions.
- ❌ "Show someone using the product"
- ✅ "Extreme close-up of glowing LED nodes activating one by one in darkness"

### Pattern: Low Cinematic Score (1-2)
**Symptom**: Flat lighting, amateur look, visible AI artifacts
**Fix**: Add lighting and camera instructions:
- "premium studio lighting with soft key light and rim light"
- "warm cinematic color grading with slight orange tint"
- "slow-motion at 120fps equivalent"
- "shallow depth of field with bokeh background"

### Pattern: Low Product Clarity (1-2)
**Symptom**: Product looks wrong or unrecognizable
**Fix**: Add material and physical detail:
- Specify exact materials: "brushed aluminum", "matte silicone", "translucent acrylic"
- Specify colors: "cream white body with rose gold accents"
- Specify key features: "three LED lights: red, blue, green — each 5mm diameter"

### Pattern: Low Brand Element Score (1-2)
**Symptom**: Logo, price, or CTA not visible
**Fix**: Make the logo description MORE detailed and add explicit positioning:
- Add "centered on screen" to every text element
- Make the logo description longer and more specific
- Separate brand elements into their own sentence

### Pattern: Low Safety Zone Score (1-2)
**Symptom**: Text/CTA hidden behind platform UI
**Fix**: Add explicit instruction AND position qualifiers:
- "All text and UI elements stay in the center 60% of the frame"
- Add "centered" before every text overlay instruction
- Add "lower-third centered" for brand UI elements

## Benchmark: What Good Looks Like

A 35+ score video typically has:
- Opening shot that makes you pause and watch
- Smooth, cinematic camera movements (no jarring cuts)
- Product clearly recognizable with correct proportions
- At least partial logo visibility and correct colors
- Price number readable and prominently displayed
- "Download [App]" text clearly visible
- All text comfortably within center area
- Would not look out of place in a paid ad feed
