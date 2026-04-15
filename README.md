# TikTok Ad Video Generator Skill (Seedance 2.0 Edition)

> **Core goal**: Generate high-probability viral ad videos at minimum cost for multi-platform distribution.

An AI agent skill for producing high-conversion short-form ad videos (9:16, 15s) using **Jimeng AI (jimeng.jianying.com)** Seedance 2.0 model. Designed for e-commerce apps running paid ad campaigns across TikTok, Meta, Google, YouTube, Pinterest, Snapchat, and X.

## What This Skill Does

- **Selects products** with high visual impact and price anchoring potential
- **Matches viral hook types** using a 6-pattern library for maximum first-3-second retention
- **Generates cinematic video prompts** using 3 script templates + viral boost pack
- **Submits to Jimeng** Seedance 2.0 for AI video generation
- **Produces ad copy** optimized for 6+ platforms
- **Evaluates video quality** using an 8-dimension scoring rubric (40-point scale) + viral readiness check
- **Self-iterates** — adjusts hook weights and prompt vocabulary based on performance data
- **Tracks product usage** to prevent repeats and maintain category balance

## Key Features

| Feature | Details |
|---------|---------|
| Video Format | 9:16 vertical, 15 seconds |
| Script Templates | Price Anchoring / Lifestyle Transformation / Tech Reveal |
| Viral Hook System | 6 hook types: Cognitive Dissonance, Instant Result, Price Anchoring, Emotional Bond, Visual Spectacle, Identity Tribe |
| Platform Support | TikTok, Meta (FB/IG), Google Ads, YouTube Shorts, Pinterest, Snapchat, X |
| Quality Scoring | 8-dimension rubric + viral readiness check (silent readability, completion rate, conversion signal) |
| Cost Per Video | 120 points (Seedance 2.0 Standard) |
| Automation | Cron-compatible — AI auto-selects hooks in unattended mode |

## Skill Structure

```
tiktok-ad-video-skill/
├── SKILL.md                              # Core skill document (780+ lines, 16 chapters)
├── README.md                             # This file
├── LICENSE.txt                           # MIT License
├── examples/
│   └── prompt-examples.md                # 6 real production prompts + scored evaluation example
└── references/
    ├── viral-hook-patterns.md            # 6 viral hook types, decision tree & script structures (NEW)
    ├── evaluation-rubric.md              # Quick-reference scoring sheet & failure pattern fixes
    ├── platform-specs.md                 # Multi-platform ad specs, copy formats & safety zones
    ├── cinematic-vocabulary.md           # 100+ terms + Viral Boost Pack (anti-AI, prefixes, negatives)
    └── product-tracker-template.md       # Product usage tracking, naming convention & price research
```

## Quick Start

1. Read `SKILL.md` for the complete methodology (16 chapters)
2. Configure your brand elements (logo, colors, app name)
3. Set up Jimeng account at jimeng.jianying.com
4. Follow the daily execution workflow in SKILL.md §12

## Battle-Tested

This skill was refined through **80+ videos across 8+ production days**, with iterative improvements to:
- Prompt engineering techniques for Seedance 2.0
- **Viral hook system** — 6 hook types matched to product categories
- **Anti-AI artifact suppression** — handheld feel, snappy motion, freeze frames
- Safety zone compliance across all platforms
- Brand element rendering reliability
- Product selection methodology
- Cost optimization (VIP vs Standard model)
- **Self-iteration loop** — hook weights and vocabulary evolve with performance data

## Requirements

- Jimeng AI account (jimeng.jianying.com) with sufficient points
- Browser automation capability (for Jimeng submission)
- E-commerce product catalog access

## License

MIT
