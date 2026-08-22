# Pura OOH concepts, August 2026

Ten pieces of Pura artwork: **five billboards and five digital verticals**, generated with Gemini 3 Pro Image (Nano Banana Pro).

Open `01-concepts.md` for all ten with copy, placement and layout. Artwork in `renders/`, layout wireframes in `sketches/`, the shared grid in `LAYOUT-SYSTEM.md`.

## Where the directions came from

Not from taste. From the 80 reference moodboard in `../../Research/App-Feature-Showcase-Moodboard/`, which measured what actually survives a billboard:

| Treatment | Billboard viable |
|---|---|
| Photographic | 100% |
| 3D render | 86% |
| Flat vector | 26% |

| Arrangement | Billboard viable |
|---|---|
| container-spill, mosaic-gestalt, object-metaphor, world-place, replacement-stack | **100%** |
| orbit-3d | 88% |
| **radial** | **36%** |

Every one of the ten sits in the winning half of that table. **The whiteboard sketched a radial, which scores 36%.** The idea in the sketch is kept in B4 and B5. The execution is not a labelled ring, because labelled rings die at distance.

## The ten

| | Direction | Descends from |
|---|---|---|
| B1 | The Container | ERA Real Estate suitcase |
| B2 | The Gestalt | Capsule heart built from pill shapes |
| B3 | The Replacement | ClickUp, One app to replace them all |
| B4 | The Convergence | WHOOP, plus the whiteboard's left panel |
| B5 | The Small World | SJ InterCity miniature, the whiteboard's right panel |
| V1 | The Day | The GoTo ecosystem clock, unrolled |
| V2 | The Body | Body centred, plus Pura's Digital Twin anatomy work |
| V3 | The Score Tower | WHOOP score with inputs beneath |
| V4 | The Unfold | Container and cutaway, verticalised |
| V5 | The Pocket | The deployed It's everything X in your pocket template |

## Brand compliance

- Copy checked against the five locked feature headlines and the launch hero. Every asset closes on the locked tagline.
- **No em dashes, en dashes or hyphens.** British English. Every headline six words or fewer.
- Mandatory infinite value loop honoured: each line carries both what goes in and what comes out.
- Art direction follows the campaign visual grammar: morning light, single focal action, no busy compositions, restraint over flourish.
- Key Visual versus Lived Imagery rule respected: the billboards hold one treatment, the verticals another, never mixed within a moment.

## Honest limits

- **Typography is a stand in.** Pura has no documented typeface; the brand brain still marks typography Pending and the brand book PDF is too large to extract. The renders use a clean geometric sans. Final artwork must be reset by the design team in the real face.
- **Text is model rendered, at Brenton's instruction.** It came out clean on ten of ten after regeneration, but it is not typeset and will not match a Pura face. Three assets needed regeneration to fix it: B3 lost its headline twice and rendered the word "Blank" onto the props before an out of focus treatment fixed it; V3 lost its headline once; V1 was regenerated for a weak composition.
- **No Arabic.** Model rendered Arabic is unreliable, and the RTL version is a mirror of the layout rather than a translation of it. AR is a compositing job for the design team.
- **These are concepts, not final artwork.** Product screens are indicative, not real Pura UI. Nothing here has been through clinical or legal review.

## Reproducing

`_pipeline/prompts.json` holds every prompt. `_pipeline/render.py` calls the model directly. Each render has its exact prompt saved beside it. The API key lives only in the session scratchpad and is never written into this folder or committed.
