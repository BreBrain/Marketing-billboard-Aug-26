# Reference Brief: the "message left, app screen right" OOH format

Written before the scrape. This document is the filter. It decides what enters the collection and what does not, so the result is a format study rather than a billboard scrapbook.

---

## The format under study

A landscape out of home execution split into two halves:

```
┌──────────────────────────────┬─────────────────────┐
│                              │                     │
│   MESSAGE                    │    APP SCREEN       │
│   short, high contrast       │    legible UI       │
│   readable at speed          │    shows breadth    │
│                              │                     │
└──────────────────────────────┴─────────────────────┘
        left 40 to 60%              right remainder
```

The left half carries the claim. The right half proves it by showing the product doing many things at once. This is the layout super apps reach for when the strategic problem is breadth: "we do everything" is hard to say in words and easy to show in an interface.

## Why Pura needs this

Pura has the same problem. PureScore, care plans, online consultations, pharmacy, nutrition, wearables and the AI agent are one offer, but a roadside audience gets roughly three seconds. The brands in this collection have already solved the compression problem. The collection exists to learn how, and then to brief Pura's own execution against it.

---

## Qualifying criteria

An example enters as **Tier 1** only when all four hold.

1. **Format.** Landscape out of home. Billboard, unipole, hoarding, digital LED, transit side, mall banner, metro panel.
2. **Composition.** A copy or message block occupies roughly the left 40 to 60 percent. A phone or app interface occupies the right.
3. **Legibility and breadth.** The app screen is readable at reproduction size, and it shows more than one thing. A service grid, a stack of cards, a set of icons, a populated dashboard. A single feature screen does not qualify no matter how well shot.
4. **Category.** A super app or a breadth claiming app. Mobility, delivery, fintech, commerce, or health in one place.

## Disqualifying

- Portrait only formats where the split cannot exist
- Logo and tagline with no interface present
- Single feature screens (one balance, one map, one meal)
- App screens too small or too low contrast to read
- In app screenshots or digital display units presented as if they were out of home

## Tier 2: collect, label, do not count toward the target

Useful for the pattern analysis but not the format itself.

- Phone on the left, message on the right (the mirror)
- Multi screen lockups of three or more devices
- Portrait executions of the same breadth idea
- Strong breadth communication in a layout that is not split

---

## Photo versus mockup

Every entry carries a `type` field, and the distinction is not cosmetic.

- **`photo`** is a photographed real placement. Evidence that the layout survived contact with a real site, real distance, real light.
- **`mockup`** is an agency portfolio render. Behance and awards galleries are dominated by these. They show craft intent, not proven legibility.

Both belong in a format study. Presenting them as the same thing would misrepresent the evidence, so the moodboard filters on this field and the creative brief reports the split.

---

## Fields captured per entry

| Field | Meaning |
|---|---|
| `brand` | Advertiser |
| `market` | Country and city where known |
| `year` | Campaign year, or `unknown` |
| `type` | `photo` or `mockup` |
| `message` | The left hand copy, verbatim |
| `screen_communicates` | What the right hand screen actually shows |
| `breadth_device` | `icon-grid`, `stacked-cards`, `multi-phone`, `single-screen-dense` |
| `source_url` | Where it was found |
| `tier` | 1 or 2 |

---

## Search vocabulary

Recorded so the run is reproducible.

**GCC brands.** Careem, Talabat, noon, Tabby, Yango, Liv by Emirates NBD, Wio, Deliveroo UAE, Amazon UAE.

**Global super apps.** Grab, Gojek, WeChat, Alipay, Rappi, Nubank, PhonePe, Paytm, Swiggy, Zepto, Bolt, Yandex Go, Kakao.

**Western breadth apps.** Revolut, Monzo, Cash App, Klarna, Uber, PayPal.

**Format terms, rotated against each brand.** billboard · OOH advertising · hoarding · unipole · outdoor campaign · out of home campaign · Sheikh Zayed Road billboard · metro advertising.

---

## Target and stop condition

Thirty to forty Tier 1 entries. Stop when the target is met or the query set is exhausted.

If strict application of the criteria yields fewer than twenty five, the shortfall gets reported as a finding rather than fixed by loosening the filter. A thin result would itself say something: that the layout is less common than assumed, and that Pura would be doing something less derivative than expected.
