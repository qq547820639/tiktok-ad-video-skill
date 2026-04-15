# Multi-Platform Ad Specs Reference

Quick reference for deploying the same 9:16 / 15s video across all major ad platforms.

---

## Video Specs Compatibility Matrix

| Platform | Format | Ratio | Duration | Min Budget | App Install Ads |
|----------|--------|-------|----------|-----------|-----------------|
| TikTok Ads | MP4 | 9:16 ✅ | 5-60s ✅ | $50/campaign, $20/ad group | ✅ Full support |
| Meta (FB/IG) | MP4 | 9:16 ✅ | 1-60s ✅ | $1-5/day | ✅ Full support |
| Google Ads | MP4 | 9:16 ✅ | 6-60s ✅ | $20+/day recommended | ✅ App Campaigns |
| Snapchat | MP4 | 9:16 ✅ | 3-180s ✅ | $5/day | ✅ App Install |
| Pinterest | MP4 | 9:16 ✅ | 4-15min ✅ | $1/day | ⚠️ Limited |
| X (Twitter) | MP4 | 9:16 ✅ | 0-140s ✅ | Varies | ⚠️ Less optimized |

**Result**: 9:16 / 15s works on ALL platforms without re-editing.

---

## Platform-Specific Ad Copy Formats

### TikTok Ads
```
[Hook sentence]
[Product benefit]
Only $X.XX (retail $XX) | Free Shipping Worldwide
Download [App] App 👇

#Hashtag1 #Hashtag2 #TikTokMadeMeBuyIt #FactoryPrice #FreeShipping
```
- Max: 2,200 characters
- Use as-is from universal copy

### Instagram / Facebook (Meta)
```
[Hook sentence]
[Product benefit]

Only $X.XX (retail $XX)
🚚 Free Shipping Worldwide
📲 Download [App] App — Link in bio

#Hashtag1 #Hashtag2 #TikTokMadeMeBuyIt #FactoryPrice #FreeShipping
```
- Max: 2,200 characters
- Add App Store / Google Play link

### YouTube Shorts (via Google Ads)
```
[Hook — 1 sentence max]
Only $X.XX | Free Shipping | Download [App] App
```
- Title: 100 chars max
- Description: 5,000 chars
- Google App Campaigns auto-generate most copy

### Pinterest
```
[Hook sentence]
[Product benefit — 2 sentences max]
Only $X.XX | Free Shipping Worldwide
Download [App] App

Tags: [Product Name], [Category], [Material], [Use Case], [Gift Idea]
```
- Max: 500 characters
- Add 5-10 product keyword tags for search discovery

### X (Twitter)
```
[Compressed hook + benefit — must fit 280 chars total]
Only $X.XX | Free shipping
Download [App] App
#Hashtag1 #Hashtag2
```
- Strict 280 character limit
- Prioritize hook + price + CTA

### Snapchat
```
[Hook sentence]
[Product benefit]
Only $X.XX | Free Shipping
Download [App] App 👇
```
- Max: 200 characters for caption
- Use as-is from universal copy (shorten if needed)

---

## Platform Priority Matrix

| Priority | Platform | Why |
|----------|----------|-----|
| 🔴 HIGH | TikTok Ads | Discovery engine, best for new app awareness |
| 🔴 HIGH | Meta (FB/IG) | Largest audience, most sophisticated targeting |
| 🟠 HIGH | Snapchat | Underrated for discount shopping audience |
| 🟡 MEDIUM | Google/YouTube | App Campaigns automate everything |
| 🟢 LOW | Pinterest | Good for lifestyle, slower conversion cycle |
| 🟢 LOW | X (Twitter) | Less optimized for e-commerce app installs |

---

## Safety Zone Overlay Map

```
┌──────────────────────────────────┐
│  ████ DANGER ZONE (top 20%) ████ │  ← Status bar, notch, time
│                                  │
│      ┌──────────────────┐        │
│      │                  │        │
│      │   SAFE ZONE      │   ██   │  ← Right: Like/Share/
│      │   (center 60%)   │   ██   │     Comment buttons
│      │                  │   ██   │
│      │  Place ALL text  │   ██   │
│      │  and UI here     │        │
│      │                  │        │
│      └──────────────────┘        │
│                                  │
│  ████ DANGER ZONE (bot 20%) ████ │  ← Caption, progress bar
└──────────────────────────────────┘
```

Every platform overlays UI differently, but the center 60% is universally safe.

---

## Pre-Launch Checklist (for Ad Team)

Before running app install ads on any platform:
- [ ] App is live on App Store AND Google Play
- [ ] App Store listing has screenshots, description, ratings
- [ ] MMP integrated (AppsFlyer / Adjust / platform SDK) for install tracking
- [ ] Business account / ad account created on each platform
- [ ] Payment method added to each ad platform
- [ ] Review timeline: expect 24-48h for ad approval (longer for Chinese cross-border apps)
