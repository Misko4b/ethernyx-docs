---
description: Where you build and run your bidding tasks on OpenSea and Blur.
---

# 🔨 Collection Bidder

The Collection Bidder is the heart of Ethernyx. This is where you spin up **tasks** — each task is one bidding strategy on one collection, and the bot keeps it live for you: placing offers, outbidding, cancelling stale ones, and re-listing fills if you turned on autolist.

<div align="left"><figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure></div>

The page has two parts:

* **The task list** — every task you've created, shown as cards with live floor, top bid, your bid range, and profit. Group them, search them, bulk-edit them, import/export them. → [Managing Tasks](collection-bidder/managing-tasks.md)
* **The task editor** — the form where you pick a collection, wallet, marketplace, and bid mode, then dial in your parameters. → [Creating a Task](collection-bidder/creating-a-task.md)

## Three ways to bid

Every task is one of three offer types. Which one you get is decided by the **bid mode** you pick:

* **[Collection Bids](collection-bidder/collection-bids.md)** — one offer across the whole collection. Cheapest way to be top bidder on everything.
* **[Trait Bids](collection-bidder/trait-bids.md)** — offers only on items with specific traits (rare backgrounds, 1/1 types, whatever). One bid per trait.
* **[Token Bids](collection-bidder/token-bids.md)** — offers on specific token IDs (item-level). OpenSea only, Starter plan and up.

Not sure which to use? Each page breaks down every mode: what it does, how the bot prices it, and when to reach for it.

{% hint style="info" %}
Full reference for every field is on the [Parameters](collection-bidder/parameters.md) page, and the gotchas that trip people up are in [Tips & Rules](collection-bidder/tips-and-rules.md). Read those before you start real tasks.
{% endhint %}
