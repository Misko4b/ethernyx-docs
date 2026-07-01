---
description: One offer across the whole collection — the simplest way to bid.
---

# Collection Bids

A collection bid is a single offer that applies to **every token in the collection**. Anyone can sell you any item at that price. It's the cheapest, simplest way to be the top bidder — one offer, one slot, the whole floor.

Use it when you want the floor, don't care which specific token you get, and just want to be at (or near) the top of the book.

## OpenSea

### Standard <mark style="color:blue;">OpenSea</mark>

The default. Places one collection-wide offer and keeps it at the top within your limits.

* **How it prices:** takes the current top bid and outbids it by your **OS Default Margin**, never going above your **Max Bid**.
* **When to use:** your bread-and-butter mode for grabbing the floor. Set a Max Bid, set a min profit, let it ride.
* **Heads up:** the collection must have **Collection Offers enabled** on OpenSea (most do). If it doesn't, this mode is locked and you'll want [Trait](trait-bids.md) or [Token](token-bids.md) bids instead.

## Blur

Blur gives you four collection-level modes, because on Blur the *position* of your bid in the book matters (that's how bidding points and fills work).

### 0.01 Above <mark style="color:orange;">Blur</mark>

The Blur equivalent of Standard — sit right on top.

* **How it prices:** top bid **+ your Blur margin** (usually 0.01). You're the leader.
* **When to use:** you want fills and you want to be first in line. Simplest aggressive mode.

### Level Below <mark style="color:orange;">Blur</mark>

Bids one level *below* the top — you're never first on the list.

* **How it prices:** parks at the price tier just under the leader.
* **When to use:** you want depth/points exposure without being the one who actually gets hit first. Safer, more patient.

### One Below <mark style="color:orange;">Blur</mark>

Sits a fixed step under the top.

* **How it prices:** top bid **− your Blur margin**. Always just below the leader, never on top.
* **When to use:** you want to shadow the top bid closely but never lead it.

### Matched <mark style="color:orange;">Blur</mark>

A flat offer parked at your Max Bid.

* **How it prices:** it just bids **your Max Bid, exactly** — every time, no matter what the top bid or the rest of the book is doing. It doesn't chase anyone or step around other offers; your Max Bid _is_ the offer.
* **When to use:** you've decided the exact number you're willing to pay and want to sit right there, no dynamic outbidding. Set Max Bid to that number and it holds the line.

{% hint style="info" %}
**Bidding on All markets?** Pick a marketplace-agnostic mode (Standard / Smart) and Ethernyx runs the right strategy on each side. The Blur-only modes above only show up when the task's marketplace is Blur.
{% endhint %}

***

Collection bids ignore traits and token IDs — they're the whole collection by definition. Want to target rares or specific tokens? → [Trait Bids](trait-bids.md) · [Token Bids](token-bids.md). All the price/limit fields are in [Parameters](parameters.md).
