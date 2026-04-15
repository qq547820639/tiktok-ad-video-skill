# Product Usage Tracker Template

Use this table to track all products featured in ad videos. Before selecting a new product,
check this list to avoid repeats.

---

## Tracking Table

| Day | Date | Product Name | Price | Category | Template | Score | Status |
|-----|------|-------------|-------|----------|----------|-------|--------|
| 1 | YYYY-MM-DD | [Product Name] | $X.XX | Home/Beauty | A/B/C | /40 | ✅/❌ |
| 2 | YYYY-MM-DD | [Product Name] | $X.XX | Home/Beauty | A/B/C | /40 | ✅/❌ |

### Column Definitions
- **Day**: Sequential production day number
- **Date**: Calendar date of generation
- **Product Name**: English product name (same as used in prompt)
- **Price**: App price in USD
- **Category**: Home Gadget / Beauty Tech / Personal Care / Kitchen Tech / Lifestyle
- **Template**: A (Price Anchoring) / B (Lifestyle Transformation) / C (Tech Reveal)
- **Score**: Evaluation rubric total score out of 40
- **Status**: Used (submitted & accepted) / Rejected (regenerated) / Pending

---

## How to Maintain

### Adding New Entries
After each daily video generation:
1. Add a new row with the product details
2. Score the video using the evaluation rubric
3. Mark status based on whether the video was accepted

### Checking for Repeats
Before selecting a new product:
1. Search this table for the product name (or similar products)
2. Also search for the product category — avoid over-indexing on one sub-category
3. Rule: No exact product repeat. Similar products (e.g. two different facial massagers) 
   should be spaced at least 14 days apart.

### Storage Recommendations
- Store as product-tracker.md in the project directory
- Update after every production run
- The AI agent should read this file at the start of each daily execution
- Keep in MEMORY.md as a reference pointer: "See product-tracker.md for full list"

---

## Category Balance Guide

Track category distribution to maintain variety:

| Category | Count | % of Total | Target % |
|----------|-------|-----------|----------|
| Beauty Tech | X | X% | 30-40% |
| Home Gadgets | X | X% | 30-40% |
| Personal Care | X | X% | 10-20% |
| Kitchen Tech | X | X% | 5-15% |
| Lifestyle | X | X% | 5-15% |

**Rule**: No single category should exceed 50% of total videos. If a category is overrepresented, 
prioritize other categories in the next selection cycle.

---

## Competitor Price Research Checklist

When selecting a product, research the competitor retail price using this process:

1. **Amazon US** — Search product name → Note "retail price" or top brand price
2. **Walmart** — Cross-reference for price confirmation
3. **Brand website** — If the product has a known brand equivalent (e.g. Dyson, SkinGym)
4. **Google Shopping** — Quick price comparison

### Price Anchoring Validation
- App price must be **< 30%** of competitor retail price
- Document both prices in the tracker
- If no clear competitor exists, use "typical retail" as baseline

Example:
- HuoPan LED neck device: $16.18
- SkinGym/CurrentBody equivalent: $89
- Ratio: $16.18 / $89 = 18% (well below 30% threshold)

---

## File Naming Convention for Downloaded Videos

When the user downloads the generated video, use this naming pattern:

```
[APP]_ad_[DAY]_[TEMPLATE]_[PRODUCT-SHORT]_[DATE].mp4
```

Examples:
- huopan_ad_d8_B_led-neck-device_20260415.mp4
- huopan_ad_d9_C_smart-humidifier_20260416.mp4
- huopan_ad_d10_A_skin-scrubber_20260417.mp4

This makes it easy for the ad placement team to:
- Identify which app the video is for
- Know the template style (for A/B testing analysis)
- Find the product quickly
- Sort chronologically
