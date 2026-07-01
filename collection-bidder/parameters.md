---
description: Every field in the task editor, what it does, and how to set it.
---

# Parameters

This is the full reference for every field in the task form. Most apply to all bid modes; a few are mode-specific and noted as such.

<div align="left"><figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure></div>

## Profit guards

* **Min Profit %** — the minimum margin between your bid and the floor. If the floor is 1.2 ETH and you want 30%, the bot bids at most 0.92 ETH (0.92 + 30% = 1.196, just under floor). Keeps you from bidding into a loss.
* **Min Profit ETH** — same idea, in flat ETH. Floor 1.2, min profit 0.3 → bids max 0.9 ETH.
* **Min Arbitrage** — bid based on the *other* marketplace's price. If Blur's bid is 2 ETH but OpenSea's is 3 ETH, the arbitrage (bid − fees) is ~1 ETH: buy on Blur, instantly dump into the OpenSea bid. This sets the minimum arb profit (in ETH) you'll accept — e.g. 0.1.

## Bid range

* **Max Bid** — the ceiling. The bot **never** bids above this. Use it always (see [Tips](tips-and-rules.md)).
  * Absolute: `0.5` — a hard number.
  * Relative: `+2.5` or `+10%` — computed live from a base. **Relative needs a trait filter, token IDs, or a `Smart IDs`/`IDs` mode.**
  * **Base** (shows up for relative values): `Bid` = min(floor, top bid) + X — the safer default; `Floor` = floor + X only, ignoring the top bid (less safe).
* **Min Bid** — the floor of your bidding. Useful for collections where the top bid is silly-low (floor 2 ETH, top bid 0.05 ETH — no one sells at 0.05, so don't bother). Same absolute/relative/base rules as Max Bid.
* **Min Floor** — if the collection (or trait) floor drops below this, the bot **stops bidding**. Your circuit breaker against a collapsing floor.

## Volume

* **Quantity** — how many offers to place. If your ETH can't cover them all, the bot places as many as it can (want 100, funded for 20 → it places 20).
* **Max Buy** — the most NFTs you want to end up holding. Set to 1, and once you buy one the task pauses until you sell it.
  * ⚠️ Quantity and Max Buy are independent: with quantity 5 and max buy 1, you still have **5 live offers** — several can fill at once. Same with Smart mode (one bid per trait). Size accordingly.
* **Min Bids Above** — *Blur points farming only, useless for flipping.* When > 0, the bot places your bid at the depth level where the bids above and at your price sum past your number. (Min Bids Above = 200; levels have 100 / 50 / 80 bids → it sits at level 3, since 100+50+80 > 200.)

## Margins

* **Blur Outbid Margin** — how much ETH you outbid by on Blur. Usually `0.01`.
* **OS Default Margin** — the multiplier for standard OpenSea outbidding (usually `1`). OpenSea prices snap to a tiered precision:

| Offer price | Decimals | Valid | Invalid |
|---|---|---|---|
| 0.0001–0.0999 ETH | 4 | 0.0542 | 0.00005, 0.00992 |
| 0.100–0.999 ETH | 3 | 0.235 | 0.1001, 0.9999 |
| 1.00+ ETH | 2 | 1.05 | 1.003, 13.2002 |

  Your margin multiplies that smallest step. Margin 1 = outbid by one tick; margin 3 = three ticks.
* **OS Increased Margin** — a bigger multiplier used by Smart, Smart IDs, and IDs modes, so your item/trait offer sits comfortably above the competition and *you* specifically get the sale.

## Bid behavior (all modes)

* **Place bids below top bid** *(default: on)* — when you can't outbid the top within Max Bid, still post an offer below it. Off saves limits — only bid when you can lead.
* **Undercut when far above 2nd bid** *(default: on)* — when you're top and way above 2nd place, trim your offer to the minimum needed to stay #1. Off holds your price.

## After a fill

* **Autolist** *(default: off)* — automatically list NFTs you buy, right after the purchase, to lock profit in. Turn it on and set **Autolist Min Price** (ETH) — the floor it'll never list below.
* **Stop when max buy limit reached** *(default: on)* — when Max Buy is hit: **on** = task stops for good (restart it by hand, even after you sell); **off** = task auto-resumes once a slot frees up (you sell the NFT).

***

See the [gotchas](tips-and-rules.md) before going live — a couple of these interact in ways that surprise people.
