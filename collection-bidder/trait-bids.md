---
description: Bid only on items with specific traits — Smart mode + trait filters.
---

# Trait Bids

Trait bids target items with **specific attributes** — rare backgrounds, a certain type, a specific rarity tier — instead of the whole collection. You place one offer per trait, and only items carrying that trait can fill it.

This is the **Smart** mode, and it works on both OpenSea and Blur.

## Smart <mark style="color:blue;">OpenSea</mark> <mark style="color:orange;">Blur</mark> <mark style="color:purple;">All</mark>

* **How it prices:** one bid **per selected trait**, priced off the collection's global floor with your **OS Increased Margin** — so your effective offer can sit *below* the collection floor while still being the top bid on that trait. In other words, you can quietly be the best offer on the rares without lighting up the whole collection.
* **Requires a trait filter.** Smart mode does nothing without traits selected — that's the whole point.
* **When to use:** you want specific rares and you want to stay under the radar. Great for sniping undervalued traits where the trait floor is way above the collection floor.

{% hint style="warning" %}
On OpenSea, Smart needs the collection to have **Trait Offers enabled**. If it's off, the trait tab shows prices for reference but you can't select them — switch to [Token Bids](token-bids.md) (`Smart IDs` / `IDs`) to bid on traits via item offers instead.
{% endhint %}

## Picking traits

Open the filter and you get two columns: **Trait Types** on the left, **Trait Values** on the right. There's a **Search traits…** box that hunts values across every type at once (type "Ice" and it finds every trait with that value).

* **Pick a value** — click it. Each shows its own floor (`F`) and top bid (`B`) so you know what you're bidding into.
* **Select All** — grabs the *whole* trait type instead of one value. Ethernyx prices it by aggregating across the type (lowest floor, highest effective bid).
* **Multiple traits** — combine them two ways:

| Mode | Symbol | Meaning | Where it works |
|---|---|---|---|
| **OR** | any of | one bid per trait — item matches *any* selected trait | Everywhere |
| **AND** | all of | one bid on items matching *all* selected traits at once | OpenSea only, in `Smart IDs` / `IDs` modes |

{% hint style="info" %}
**AND is not a Smart-mode thing.** Combining traits (e.g. "Gold Fur **and** Laser Eyes") only works as an OpenSea item offer — so it needs [Token Bids](token-bids.md) (`Smart IDs` or `IDs`). In plain Smart mode you're limited to OR.
{% endhint %}

### Blur composite traits

Blur is a special case. Ethernyx can **monitor** composite (AND) traits on Blur — floor, listings, pricing all show up — but you **can't place a bid** on a trait combination on Blur, because Blur has no offer type for "items matching two traits at once." Use single traits (OR) to actually bid on Blur.

### If a trait has no listings

No listings for a trait means no floor to price against — so the bid **defaults to 0.01 ETH**. Keep an eye on thin traits; that default can be way off what you'd actually pay.

***

Trait bids also unlock the relative **+X / +X%** Max/Min Bid formats (priced off the trait) — see [Parameters](parameters.md). Want specific token IDs instead of traits? → [Token Bids](token-bids.md).
