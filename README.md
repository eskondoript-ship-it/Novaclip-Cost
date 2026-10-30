# NovaClip — cost and profit simulator

One HTML file. Open `index.html` in any browser and every number recalculates as
you drag. Nothing is installed, nothing is fetched, no account, no network calls
at all — which is also why it works offline and why there is no key anywhere in
it.

**[Open it](https://eskondoript-ship-it.github.io/Novaclip-Cost/)** once Pages is
switched on (Settings → Pages → Branch `main`, folder `/root`).

## What it answers

- How many paying customers before NovaClip breaks even
- What the profit is at 100 / 250 / 500 / 1,000 / 2,500 / 5,000 customers
- How many machines the AI features need, and what they cost to buy and to run
- Which AI features are affordable to give away free, and which are not
- How likely any of it is, across three thousand simulated futures

Money coming in is green, money going out is red.

## The machine it prices

| Part | Price | Flat out |
| --- | --- | --- |
| RTX 5090, 32GB | €2,600 | 575 W |
| RTX PRO 4500, 32GB | €2,900 | 200 W |
| Ryzen 9 9950X | €600 | 170 W |
| 128GB DDR5, 4 × 32GB | €480 | 20 W |
| 4TB NVMe | €300 | 10 W |
| Motherboard, X870E | €350 | 30 W |
| 1600W power supply, 80+ Platinum | €300 | — |
| Cooling, 360mm AIO and six fans | €180 | 15 W |
| Case | €150 | — |
| Cables, Linux, the bits | €120 | — |
| **One machine** | **€7,980** | **1,020 W** |

Every price is editable in the page, and the machine cost is nothing but their
sum — so the buy price, the depreciation, the profit and the budget verdict all
move together when a price changes.

**Two cards is the ceiling, and the board is not why.** The 9950X has 24 PCIe
lanes, so two slots run at x8/x8 and there is nothing left for a third. A third
card means Threadripper PRO or EPYC — a different, much dearer machine. So
capacity grows by buying whole machines, not by adding cards.

## The finding that matters most

Each AI feature has an audience: **Everyone**, **Customers**, or **Not here**.
That one choice matters more than how fast the card is, because a feature given
to everyone gets multiplied by the free crowd.

Video generation, at 5,000 customers:

| Who gets it | Machines |
| --- | --- |
| Customers only | 8 |
| Everyone | **63** — €504,000 of hardware. Not possible. |

So video and character animation are what people pay for. Image generation at
2.5s is cheap enough to give away, and it still ends up the single biggest use
of the card (39%) purely because everyone gets it 22 times a year. Body tracking
runs in the browser and costs nothing. Trend scans need live web search, which a
card in your room cannot do, so they stay on an API.

## At 500 customers

| | |
| --- | --- |
| Machines needed | 1 |
| Machines to buy — one off | €7,980 |
| Electricity a year | €771 |
| Hardware spread over 3 years | €2,660 |
| Salary, ads, accountant and the rest | €11,872 |
| **Everything it costs in a year** | **€15,303** |
| Money coming in a year | €54,237 |
| **Profit a year** | **€38,934** |

One machine carries about 684 paying customers. The second machine is the only
hardware decision worth planning for, and it only arrives once the business is
already making real money.

## What is measured and what is guessed

Treat this as a model, not a forecast. Two inputs carry almost all of the
uncertainty and **neither is measurable until the payment links are live**:

- **conversion** — how many free users become paying ones (2.5% assumed; apps
  like this get 1–2%, the original plan assumed 5%)
- **certificates** — how many people buy one (2% assumed; nobody has bought one
  yet)

Below roughly 3% conversion, growth makes the losses bigger rather than smaller.
That is the single number to go and measure first.

The costs are firmer: year-one figures come from the NovaClip costs document, and
the hardware prices are retail at the time of writing.

## Notes on the page itself

- No build step, no dependencies, no framework. One file.
- Anything typed into the notes box is saved in that browser only. It does not
  travel with the link and it is not uploaded anywhere.
- Works in light and dark, and down to phone width.
