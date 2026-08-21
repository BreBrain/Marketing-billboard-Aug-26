# App Feature Showcase Moodboard

One app at the centre, its features arranged around it. The ecosystem graphic, the exploded render, the feature constellation.

**Open:** `Pura-App-Feature-Showcase-Moodboard.html` (single file, works offline, no server needed).

Sibling to `../OOH-Superapp-Moodboard/`. That collection studied how brands **claim** breadth on a billboard. This one studies how they **show** it, and answers the question that one left open.

## The finding

Every entry records how many features it shows and whether it still reads at a glance. Legibility was judged per image on what it actually looks like, never derived from the count, because deriving it would have made the finding a restatement of the threshold.

| Features shown | Entries | Still legible | Hit rate |
|---|---|---|---|
| 1 to 3 | 4 | 4 | **100%** |
| 4 to 6 | 18 | 18 | **100%** |
| 7 to 9 | 13 | 13 | **100%** |
| 10 or more | 15 | 9 | **60%** |

**Nothing below ten features failed. All 35 of them read.** So the first answer is simple: up to nine, count is not the constraint.

**Above ten, one structure carries almost everything: the grid.**

| Above ten and still legible | Count | Arrangement |
|---|---|---|
| Revolut Hub | 20 | grid |
| Apple devices and services | 13 | grid |
| Careem app grid | 12 | grid |
| Paytm | 12 | two branches of six |
| Apple Health Browse (twice) | 10 | grid |
| Starling categories | 10 | grid |
| Apple Watch health | 10 | radial |
| Apple Services objects | 10 | floating |

And what fails above ten: Gojek's seventeen plain spokes, Grab's eighteen loose icons, Inc42's sixteen scattered logos, a sphere of forty icons, Apple's forty icon concentric diagram.

**The distinction is not how many things, it is whether they add up to ONE object.** A grid is a single familiar shape the eye takes in whole, so Revolut can put twenty services in a Hub screen and it still reads. Seventeen spokes are seventeen separate things, and they do not.

Grouping does the same job by another route: Paytm splits twelve into two branches of six, Rappi hangs twenty sub brands off eight ring segments, Revolut hangs thirty products off eight buckets. **Make it one object, or make it few groups. Never make it a list.**

## What is in it

50 entries, built in two rounds. Round 1 produced 58; Brenton pruned it to 25 references, which tightened the definition (see `00-reference-brief.md`). Round 2 added 25 more against the tightened rules, weighted toward **Revolut, Apple, Monzo and the well known super apps**.

| | Count |
|---|---|
| Shipped product marketing (`product`) | 36 |
| Portfolio and concept work (`concept`) | 14 |
| Legible at a glance | 44 |
| Not legible at a glance | 6 |

Arrangements: radial (14), grid around (14), orbit 3d (14), flat diagram (3), stacked cards (2), exploded (2), fanned screens (1).

Treatments: 3d render (20), flat vector (17), real UI composite (9), illustration (4).

Brands: Apple, Apple Health, Apple One, Apple Watch, Revolut, Monzo, Starling Bank, Wise, Chime, Cash App, Careem, Careem Pay, Rappi, Gojek, GoTo, Grab, WeChat, Paytm, PhonePe, Google, Gemini, Samsung Health, BMW, Inc42.

Note the treatment shift between rounds. Round 1 skewed to flat vector strategy diagrams; the prune killed most of them, and round 2 is dominated by **3d render** and real product marketing. That is the collection Brenton actually wanted.

## Documents

| File | What it is |
|---|---|
| `00-reference-brief.md` | The filter. Written before the scrape |
| `02-synthesis.md` | What it means for Pura, and the answer back into the OOH creative brief |
| `_pipeline/manifest.json` | Machine readable index, every entry with its count, legibility verdict and source |

## How it was built

```
firecrawl search --sources images   45 queries, paced (the API rate limits at 429 long before credits run out)
        v
harvest.py    width >= 800px, aspect >= 0.6, stock-library domains rejected at the URL
        v                       900 raw  ->  436 downloaded  ->  411 decodable
contact.py    contact sheets, 16 per sheet, for triage
        v
curate.py     the visual filter, by eye against 00-reference-brief.md
        v                       411  ->  60 shortlisted
qa.py         second pass, 4 per sheet at full resolution
        v                       60  ->  58 kept
build.py      manifest.json -> the offline HTML viewer
```

The pipeline is the one built for the OOH moodboard, copied across. Two changes were required, and the first would have silently wrecked the run:

1. **`MIN_ASPECT` dropped from 1.25 to 0.6.** The OOH value existed to enforce landscape billboards. This genre is square, 4:3 and portrait, so the old value would have discarded most of the good supply without saying so.
2. **A stock-library domain blocklist** (`shutterstock`, `istockphoto`, `dreamstime`, `vecteezy` and others). It rejected **105 results**, more than a tenth of everything found. This genre is the most flooded category on stock sites.

## Coverage status and honest limits

- **AI generated filler is now a serious contaminant in this genre, worse than in photographed OOH.** The full resolution second pass removed a Tata Neu "ecosystem strategy" that was AI generated, betrayed by garbled type reading "Data Flows to trasse NeuCoins flow", "Delivery truks" and "activisto in monta new uents". It was completely convincing at thumbnail size. **Do not run this pipeline without the second pass.**
- **A VectorMine watermarked diagram was also removed** at the second pass, having survived triage.
- **One query returned literal exploding phones.** "phone with app features exploding" surfaced Galaxy Note 7 battery fires. Worth remembering that this genre's vocabulary overlaps with hardware failure.
- **No Dribbble or Behance scrape was run.** Image search plus trade and agency sources carried the collection past target, so the planned gallery harvest was not needed. That is the next lever if a higher craft ceiling is wanted, and it is where the best concept work lives.
- **Health is under represented relative to commerce**, which is itself a finding and is discussed in the synthesis.
- Third party marketing images held for internal reference. Not for reproduction.
