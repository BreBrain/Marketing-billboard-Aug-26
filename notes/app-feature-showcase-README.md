# App Feature Showcase Moodboard

How a product with many services shows that breadth in a single image. Built to answer one question: **what actually goes on the right hand half of a billboard.**

**Open:** `Pura-App-Feature-Showcase-Moodboard.html` (single file, works offline, no server).

Sibling to `../OOH-Superapp-Moodboard/`, which studied how brands *claim* breadth on a hoarding. This one studies how they *show* it.

**80 references.** Closed at Brenton's call; the original target was 150. See Coverage below.

---

## The finding

Every entry carries two independent verdicts, both judged by eye, neither derived from the other:

- `legible_at_glance` — does it read on a screen
- `billboard_viable` — does it survive being cropped to half a landscape hoarding and read at distance

### Treatment predicts billboard viability. Nothing else comes close.

| Treatment | Entries | Billboard viable |
|---|---|---|
| **photographic** | 11 | **11 (100%)** |
| **3d render** | 21 | **18 (86%)** |
| illustration | 7 | 4 (57%) |
| real UI composite | 14 | 7 (50%) |
| **flat vector** | 27 | **7 (26%)** |

Photographed objects and rendered objects survive. Flat vector diagrams do not. The most collected treatment is the worst performing one.

### Feature count barely matters for a billboard

| Features shown | Entries | Legible on screen | Billboard viable |
|---|---|---|---|
| 1 to 3 | 5 | 100% | 80% |
| 4 to 6 | 29 | 100% | 69% |
| 7 to 9 | 21 | 95% | 52% |
| 10 or more | 25 | 72% | 48% |

Viability declines gently from 80% to 48% while screen legibility falls off a cliff at ten. **For a hoarding, how you draw it matters far more than how many you show.**

### Arrangement, ranked by what survives distance

| Arrangement | Entries | Billboard viable |
|---|---|---|
| container-spill · object-metaphor · mosaic-gestalt · world-place · replacement-stack | 12 | **100%** |
| orbit-3d | 16 | 88% |
| exploded | 3 | 67% |
| grid-around | 15 | 60% |
| shelf-menu | 2 | 50% |
| **radial** | **22** | **36%** |
| flat-diagram | 4 | 25% |
| stacked-cards · fanned-screens · cutaway · body-centred | 6 | 0% |

**Every metaphor led direction scores 100%. The ring of labels, which is the shape most collected and the shape the whiteboard sketches, scores 36%.**

---

## The five images that answer the brief

1. **ERA Real Estate, suitcase** — an open suitcase holding an entire neighbourhood of amenities under the line *a wide range of facilities*. Three executions, same object, different world inside each. No icons, no grid, no diagram. Works at half a billboard untouched.
2. **Capsule, heart of pills** — a large white heart built entirely from capsule shapes. At distance one heart; up close, many medicines. One object and many services at the same time.
3. **ClickUp, One app to replace them all** — a real transit poster that shows nothing and says everything.
4. **It's everything [brand], in your pocket** — a deployed ad template found in five variants. Message left, six named service chips, phone right. Almost exactly Pura's service count, already solved.
5. **General Electric, 1950s** — a railway carriage sliced open lengthways, fourteen businesses visible inside one vehicle.

---

## What is in it

| | Count |
|---|---|
| Shipped product marketing | 52 |
| Concept and portfolio work | 28 |
| Billboard viable | 47 |
| Legible on screen | 72 |

41 brands, including Apple, Apple Watch, Revolut, Monzo, Starling, Wise, Careem, Rappi, Grab, Gojek, WeChat, Paytm, PhonePe, Practo, Halodoc, Alodokter, Samsung Health, Capsule, ERA Real Estate, ClickUp, Victorinox, General Electric, SJ InterCity.

## How it was built

```
firecrawl search --sources images   paced, 429 backoff, resumable
        v
harvest.py    >=800px, aspect >=0.6, stock-library domains rejected at the URL
        v
contact.py    triage sheets, 16 per sheet
        v
qa.py         SECOND PASS at full resolution, 4 per sheet - mandatory
squint.py     small-render pass for billboard_viable, because a hoarding is a distance read
        v
curations.jsonl -> rebuild.py -> build.py -> selfcheck.py -> publish.sh
```

Curation is keyed on **content derived candidate filenames, never array indices**. `candidates.json` re-sorts every time new searches land, and index keying silently repointed 25 curated entries at the wrong images once before this was fixed.

Every publish was gated by `selfcheck.py` and verified against the **live** site, with automatic rollback on failure. Five rounds, five passing publishes, full audit trail in `_pipeline/loop/round-*.md`.

## Coverage and honest limits

- **Closed at 80 of a 150 target, by Brenton's decision.** Not a failure to reach it: yield fell from 0.57 keepers per query (commerce) to 0.18 (health) as vocabulary exhausted, then recovered to 0.42 once metaphor led directions were introduced. 362 Firecrawl credits and 268 unrun queries remain, so the collection could be resumed at any time by following `_pipeline/loop/RUNBOOK.md`.
- **Health supply is genuinely thin for this genre.** Health marketing is dominated by app screenshot rows and agency consultancy decks, both disqualified. The health entries that did qualify are among the most useful in the set.
- **Two directions returned nothing after direct targeted searching:** `character-many-arms` (octopus, many hands) and `multiple-exposure` (one person, many moments, one frame). Recorded as findings. Nobody is doing them, so Pura doing one would be distinctive rather than derivative.
- **AI generated filler is a serious contaminant.** The full resolution second pass removed synthetic images that were completely convincing at thumbnail size, including a billboard reading "Mobile Roseting" and an ecosystem graphic captioned "Data Flows to trasse NeuCoins flow". Do not run this pipeline without that pass.
- Third party marketing images held for internal reference. Not for reproduction.
