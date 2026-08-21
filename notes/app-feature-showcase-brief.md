# Reference Brief: the app feature showcase

Written before the scrape. This document is the filter.

Sibling to `../OOH-Superapp-Moodboard/`. That collection studied how brands claim breadth on a billboard. This one studies how they **show** it, in the genre where the product itself is the hero.

---

## The genre under study

One app or device, visually central. Its features or services arranged around it, radiating from it, or emerging out of the screen.

```
            [ feature ]
                 |
  [ feature ] ── [APP] ── [ feature ]
                 |
            [ feature ]
```

This is the standard way software says "we do all of this": the landing page hero, the App Store card, the pitch deck ecosystem slide, the launch post graphic.

## The question it exists to answer

The OOH study ended on an open decision for Pura: show a screen or not, and if so, how much. It produced a rough ceiling, that three or four elements work and eighteen do not, but only from a handful of examples.

This collection tests that properly, in the genre where designers actually push the number. So every entry records **how many features are shown** and **whether it still reads at a glance.** Those two fields crossed against each other are the output.

Pura has seven service areas (PureScore, care plans, consultations, pharmacy, nutrition, wearables, AI agent). Seven is above the suspected ceiling. Whether that is fatal, and what arrangement survives it, is the thing to find out.

---

## Qualifying

1. A single app, phone or device is **visually central and dominant**
2. Its features or services are arranged **around, radiating from, or emerging out of** it
3. The features are **named or identifiable**, not decorative shapes
4. The features are rendered as **icons, 3D objects, illustrated elements or coloured tiles**, carrying their meaning visually
5. Craft standard is high enough to be worth looking at

## Tightened after round 1 (Brenton's prune)

Round 1 returned 58 entries. Brenton kept 25 and cut 33, and the cut was not random. It sharpened the definition in two ways, both now binding:

**Arrangement.** Survival rate by arrangement:

| Arrangement | Kept | Cut | Survival |
|---|---|---|---|
| stacked cards | 1 | 0 | 100% |
| orbit 3d | 4 | 1 | 80% |
| grid around | 5 | 2 | 71% |
| radial | 10 | 9 | 53% |
| flat diagram | 3 | 4 | 43% |
| exploded | 1 | 1 | 50% |
| **fanned screens** | **1** | **13** | **7%** |
| **single dense screen** | **0** | **3** | **0%** |

A row of phone screenshots is not this genre. Neither is one screen on its own. Both are now disqualifying.

**Treatment.** Among radial entries the split was not about structure, it was about what fills it. The survivors are visually led: Careem's 3D service objects on pedestals, Rappi's coloured icon donut, Gojek's isometric world, photorealistic phones with labelled callouts. The casualties were **text heavy strategy consulting diagrams**: Revolut's bullet list donut, Tinkoff's dense segment lists, Nubank's text on arrows, WeChat's text webs, Paytm's service matrix.

The rule that follows: **this is an imagery collection, not an infographic collection.** If the features are communicated by small type rather than by pictures, it does not belong here however good the structure is.

## Disqualifying

- A plain app screenshot with nothing arranged around it
- A row of app screenshots side by side (fanned screens), which is a screenshot carousel, not a feature arrangement
- A single dense screen carrying its features only as on screen UI
- Strategy and consultancy diagrams where the features are bullet lists of small type rather than visual elements
- A feature list or icon grid with no device present
- App Store screenshot carousels (sequential screens, not an arrangement)
- Pure logo, brand or download-badge graphics
- Decorative floating shapes that do not correspond to real features
- Watermarked stock library vectors, rejected at the URL before download
- AI generated filler, rejected at full resolution in the QA pass

---

## Fields captured per entry

| Field | Values |
|---|---|
| `brand` | The product, or `generic` where it is unbranded |
| `type` | `product` (shipped marketing) · `concept` (portfolio, Dribbble, Behance) |
| `arrangement` | `radial` · `exploded` · `orbit-3d` · `fanned-screens` · `flat-diagram` · `grid-around` |
| `treatment` | `3d-render` · `flat-vector` · `real-ui-composite` · `photographic` · `illustration` |
| `feature_count` | Integer. How many distinct features are shown |
| `legible_at_glance` | `yes` / `no`. Whether it survives a three second read |
| `what_it_shows` | The features, named |
| `note` | Why it is here, or what it gets wrong |
| `source_url` | Where it was found |

`feature_count` and `legible_at_glance` cannot be judged from a thumbnail. Both get recorded in the full resolution QA pass, not during triage.

---

## Two pass filter, both mandatory

The previous run of this pipeline let three AI generated fake billboards through a contact sheet triage. They were convincing at thumbnail size. This genre is far more AI saturated than photographed OOH, so:

1. **Triage** at 16 per sheet, to reject the obvious
2. **QA** at 4 per sheet at full resolution, on everything shortlisted, before anything is kept

Nothing enters `images/` without passing the second pass.

---

## Search vocabulary

Recorded so the run is reproducible.

**Arrangement led.** app features surrounding phone · features coming out of phone screen 3D · exploded view mobile app UI · app icons radiating from phone · floating UI cards around phone render · app ecosystem illustration · phone surrounded by feature icons · all in one app illustration features.

**Brand led (product).** Grab · Gojek · Alipay · WeChat · Revolut · Careem · Rappi · PhonePe · Paytm · Toss · Nubank · Monzo, each with "ecosystem", "services graphic" or "app features". Plus health: Apple Health · Samsung Health · Fitbit · Whoop · Oura · Zocdoc.

**Craft led (concept).** dribbble app features around phone · behance super app ecosystem · app landing page hero 3D features · figma community app showcase.

---

## Target

Fifty entries. Round 1 produced 58, pruned by Brenton to 25 references. Round 2 targets the remaining 25 against the tightened definition above, with a deliberate weighting toward **Revolut, Apple, Monzo and the well known super apps**.
