# OOH Super App Moodboard

Reference collection for one out of home format: **a message block on one side, an app screen on the other, where the screen communicates the full breadth of what the app does.**

**Open:** `Pura-OOH-Superapp-Moodboard.html` (single file, works offline, no server needed).

## Curated set (current)

Brenton pruned the collection to **15 references**: 9 Tier 1, 6 Tier 2, 11 photographed placements and 4 mockups. Regions: GCC 6, Americas 4, Europe 2, Africa 1.

The counts in the sections below describe the **full round 1 sweep** that produced the findings. Those findings stand on the full set; the 15 kept here are the ones worth looking at.

## What is in it

46 entries, filtered by eye from 524 downloaded candidates, which were themselves filtered from 1,240 raw image search results, then audited a second time at full resolution.

| | Count |
|---|---|
| Tier 1 (meets the split strictly) | 20 |
| Tier 2 (adjacent execution, kept for the pattern analysis) | 26 |
| Photographed real placements (`photo`) | 27 |
| Agency renders and templates (`mockup`) | 19 |
| Tier 1 **and** photographed | 14 |

Regions covered: GCC (15), Americas (11), South Asia (5), Africa (4), Europe (4), Southeast Asia (4), East Asia (1), plus 2 brand neutral templates.

Breadth devices: single dense screen (19), none / typographic only (10), icon grid (8), multi phone (5), stacked cards (4).

Brands include Yango, Uber, Paytm, Bolt, Yandex Go, Swiggy Instamart, Revolut, Grab, Gojek, Careem, Alipay, Monzo, Rappi, Zomato, Zepto, talabat, noon, Wio, Vodafone Cash, MTN MoMo, OPay, Nequi, Webull, Kose.

## The `type` field matters

- **`photo`** is a photographed real placement. Evidence the layout survived contact with a real site, real distance, real light.
- **`mockup`** is an agency render, case study asset, or stock billboard template.

Both belong in a format study. Filter to `photo` in the viewer to see only what has actually run.

## Documents

| File | What it is |
|---|---|
| `00-reference-brief.md` | The filter. Written before the scrape. Defines what qualifies, what does not, and the search vocabulary used |
| `02-pura-ooh-creative-brief.md` | The output. Pattern analysis across the 52, the gap, and the recommended Pura execution |
| `_pipeline/manifest.json` | Machine readable index. Every entry with its message, breadth device, source URL and verdict |

## How it was built

```
firecrawl search --sources images   62 queries, paced (the API rate limits at 429 well before credits run out)
        v
harvest.py    pre download filter on search metadata: width >= 800px, aspect >= 1.25 (the format is LANDSCAPE)
        v                       1,240 raw  ->  524 downloaded
contact.py    numbered contact sheets, 16 per sheet, for visual triage
        v
curate.py     the visual filter, done by eye against 00-reference-brief.md
        v                       524  ->  52 shortlisted
qa.py         second pass at 4 per sheet, big enough to catch what triage missed
        v                       52  ->  46 kept, 6 removed and 6 demoted
build.py      manifest.json -> the offline HTML viewer
```

Re-run any stage from `_pipeline/`. `search_ooh.sh` is idempotent: already-populated outputs in `.firecrawl/` are skipped, so it resumes rather than restarts.

## Coverage status and honest limits

- **The target was 30 to 40 strict examples. The honest result is 20, and only 14 of those are photographed.** This is a finding, not a shortfall to paper over. Most results for brand plus "billboard" are placement photos with no interface in them at all. The strict format is rarer in real photographed OOH than the brief assumed, which means a Pura execution in this layout would be less derivative than expected.

- **Image search in 2026 returns AI generated fakes, and they survive a fast triage pass.** The second QA pass removed three synthetic "billboards" that had passed the contact sheet review: an Uber airport scene listing "Rent" twice with the label "Explore Things a do", a bank board reading "Mobile Roseting" and "GET IT IS Google Play", and a telecom composite. All three looked plausible at thumbnail size. Any future run of this pipeline must keep the full resolution second pass.
- **The template finding is itself evidence.** Generic billboard mockup templates sold to designers have standardised on message-left / phone-right. The layout is the default convention for app advertising, which is why it is worth knowing before choosing it.
- **GCC is well represented but mostly at Tier 2.** 15 GCC entries, yet Careem, talabat and noon deliberately do not show app screens. The GCC Tier 1 examples are Bolt, GoChat, Wio and the Vodafone Cash RTL set. See the creative brief.
- **No Behance or awards gallery scrape was run.** Image search plus trade press carried the collection to target, so the planned `--format images` gallery harvest was not needed. If a deeper craft reference set is wanted later, that is the next lever.
- **Alamy and Shutterstock watermarked results were rejected** rather than kept, as was a heavily Envato watermarked template.
- **Two entries were removed as not being out of home at all:** a close up of an Alipay payment terminal, and a Yandex case study layout pairing a phone render with a placement photo.
- Third party advertising images held for internal reference. Not for reproduction.
