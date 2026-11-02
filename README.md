# NovaClip — números

Everything about what NovaClip costs and what it would charge, kept out of the
site itself. Three things live here, all static, no build step, no dependencies.

| | What it is |
| --- | --- |
| **[index.html](index.html)** | The profit simulator — break-even, machines, profit at each size |
| **[restelo.html](restelo.html)** | The partnership proposal for the Agrupamento de Escolas do Restelo, in Portuguese |
| **[apresentacao/](apresentacao/)** | The school presentation, in Portuguese — 8 slides in the deck, 13 more kept as detail |

Switch Pages on under Settings → Pages → Branch `main`, folder `/ (root)`, and
both simulators open at `https://eskondoript-ship-it.github.io/Novaclip-Cost/`.

---

## 1. The profit simulator — `index.html`

Open it and drag anything; every number recalculates. Money coming in is green,
money going out is red.

It answers how many paying customers before break-even, the profit at 100 to
5,000 customers, how many machines the AI features need and what they cost to
buy and to run, which features are affordable to give away, and how likely any
of it is across three thousand simulated futures.

**The machine it prices** — RTX 5090 32GB, RTX PRO 4500 32GB, Ryzen 9 9950X,
128GB DDR5, 4TB NVMe, X870E board, 1600W PSU, cooling, case: **€7,980** and
1,020 W flat out. Every price is editable in the page and the machine cost is
nothing but their sum.

**Two cards is the ceiling, and the board is not why.** The 9950X has 24 PCIe
lanes, so two slots run at x8/x8 and there is nothing left for a third. Capacity
grows by buying whole machines, not by adding cards.

**The finding that matters.** Each AI feature has an audience — Everyone,
Customers, or Not here — and that choice matters more than how fast the card is.
Video generation at 5,000 customers: 8 machines for customers only, **63 for
everyone**. So video and character animation are what people pay for.

## 2. The Restelo proposal — `restelo.html`

A costing tool for one specific partnership meeting, in Portuguese, themed on
the Agrupamento's own navy (`#072f4c`, the colour its site uses) and carrying
its logo.

Set the number of students, how many actually use it, the monthly plan, the AI
tier, whether certificates and NovaCoins are included and at which level, and
the partnership discount. It shows the first-year total, the per-student figure,
**and what it costs us to serve them** — so the discount can be set knowingly
rather than guessed.

Default scenario, 1,300 students at 60% adoption on Family Plus with 30% off:
the school pays **€45,798** in year one, €4.89 per active student per month,
against **€8,137** of AI and payment fees. The page states the maximum discount
that still covers cost (**87%**) and turns red past it.

Every base price in it is one the site already charges. Nothing was invented for
the meeting.

## 3. The presentation — `apresentacao/`

Portuguese, for a meeting with the school's ICT teachers, with speaker notes on
every slide. `deck.json` is the index and order; `slides/` holds one file per
slide.

**The deck is eight slides**, because the meeting is mostly a live demo of the
site rather than a presentation: cover · what we're going to open · videos for
grandparents · NovaTools free with no login · what leaves the device · the
proposal · the pilot · the next step.

`slides/` still holds **thirteen more** that are not in `order` and so not in the
deck: the ten tools and what the AI does in each, the per-call AI costs, the
Trend Spotter and the Clipper, what NovaClip deliberately does *not* do, child
protection, the infrastructure numbers, the base prices, certificates, what the
school needs to provide, and the questions the teachers are likely to ask. They
are the detail behind the eight — useful as a leave-behind and as the answers
when a question goes deeper than the deck.

The slides are in the Artifact slide format — a fixed 1920×1080 canvas with
inline styles — so they are the deck's source, not pages that render on their
own. The live deck is a private Claude artifact; these files are the record of
what it says.

## Where the numbers come from

The hard figures are measured from NovaClip's own code and from published
provider prices, not estimated:

- **€3.00 per free user per year** of AI at today's rates, **€5.05 from
  1 January 2027**, when the introductory price on the model in use ends.
- **0.0317 GPU hours per person per year** on the current feature mix. One
  machine gives **1,095 usable hours** a year after allowing for the 8× evening
  peak, so one machine serves about **34,500 students** — a 1,300-student school
  uses 3.8% of one.
- Per-call costs come from the `maxTokens` written at each call site in the
  site's source, priced at the Gemini Developer API's published rates.
- Cloudflare at 500 customers is **€72 a year**; the free KV tier breaks first,
  at 1,000 writes a day against the 42,966 the traffic needs.

## What is still a guess

Two inputs carry nearly all the uncertainty and **neither is measurable until
the payment links are live**: how many free users convert (2.5% assumed; apps
like this get 1–2%) and how many buy a certificate (2% assumed; nobody has
bought one yet). Below roughly 3% conversion, growth makes the losses bigger.

Treat all of it as a model, not a forecast.

## Notes

- No build step, no dependencies, no network calls. Each page is one file.
- Notes typed into a simulator are saved in that browser only.
- The Agrupamento's logo in `apresentacao/` and in `restelo.html` is theirs,
  used in a proposal addressed to them.
