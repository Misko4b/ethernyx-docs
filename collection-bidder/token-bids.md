---
description: Item-level offers on specific token IDs — IDs & Smart IDs modes (OpenSea).
---

# Token Bids

Token bids (a.k.a. item offers) put an offer on **specific token IDs** — not the whole collection, not a trait, but the exact tokens you name. This is the most surgical way to bid, and it's **OpenSea only**, on the **Starter plan and up**.

Two modes:

## IDs <mark style="color:blue;">OpenSea</mark>

Bids only on the token IDs you list. Nothing else.

* **How it prices:** off each **token's own floor**, with your OS Increased Margin.
* **When to use:** you want these exact tokens — a hand-picked list of IDs you're hunting.

## Smart IDs <mark style="color:blue;">OpenSea</mark>

The combo: Smart's trait targeting, delivered as item offers.

* **How it prices:** resolves your **traits into the matching token IDs**, then places an item offer on each one, priced off the token floor.
* **When to use:** you want every token with a given trait, item by item — including when the collection has trait offers turned off (this routes around that), or when you want AND-combined traits (only possible here).

{% hint style="info" %}
Both modes accept **either** a trait filter **or** a raw token-ID list (or both). Traits get expanded into IDs behind the scenes.
{% endhint %}

## Entering token IDs

In the filter, switch to **Token IDs** and type them in. Format is flexible:

```
1,2,3            single IDs
1-5,10-20        ranges
1,2,3-5,10-15,50 mix and match
```

* Ranges expand automatically, capped at **500 IDs per range** (you'll get an error over that).
* Duplicates are dropped, order is kept.
* **ERC-1155** collections work fine here.

## Item offer settings

Token bids unlock three extra controls (they sit in the form and also have global defaults in [Settings](../features/settings.md)):

* **Place bids below top bid** *(default: on)* — when the top bid is out of your Max Bid reach, still drop an offer below it. Turn it **off** to save limits and only bid when you can actually take the top.
* **Undercut when far above 2nd bid** *(default: on)* — when you're the top bid and you're sitting way above the 2nd-place offer, lower yourself to just enough to stay #1. Saves you from overpaying to lead. Off keeps your price where it is.
* **Offer duration** *(OpenSea only)* — how long each offer lives, set in days / hours / minutes / seconds. Min **610 seconds (~10 min)**, max **7 days**, default **1 hour**. Blur offers are always fixed at 7 days.

## Wallet blacklist

Token bids are the only mode where you know *who owns each token* — so you can blacklist wallets you don't want to trade with:

* Add up to **20 addresses** per task. The bot won't place item offers on NFTs owned by them.
* This merges with your **global blacklist** in [Settings](../features/settings.md).
* Handy when someone's intentionally dangling tokens to bait your offers.

## Coverage color

Because a token task can cover hundreds of IDs, the card shows a **coverage** health check — the share of your tokens where your Max Bid *can't* take the top offer:

* **Red** — 75%+ of tokens out of reach.
* **Amber** — 50–74% out of reach.
* **No tint** — you're competitive across the board.

***

The pricing/limit fields (Max Bid, margins, profit, etc.) are shared with the other modes — see [Parameters](parameters.md). New to the whole thing? Start at [Creating a Task](creating-a-task.md).
