---
description: The basics every task needs — collection, wallet, marketplace, and mode.
---

# Creating a Task

Hit **Add Task** on the Collection Bidder page and the editor opens. Every task — no matter which bid type — starts with the same four fields at the top. Once those are set, the rest of the form changes depending on the [bid mode](collection-bids.md) you pick.

## The core fields

* **Collection Slug, Name or Contract Address** — start typing a name, paste a slug, or drop a contract address. Ethernyx loads the collection automatically. If it can't find it, hit **Try to add collection** or try a different slug (Blur slug or contract usually works best).
* **Wallet Address** — which of your wallets runs this task. If the list is empty, add one first in [Wallet Setup](../wallet-setup.md). Your main wallet is picked by default.
* **Marketplace** — **OpenSea**, **Blur**, or **All** (both at once). If a collection only lives on one marketplace, Ethernyx auto-corrects this for you.
* **Bid Mode** — the strategy. The available modes change with the marketplace and with what the collection supports. This is the big one — see [Collection](collection-bids.md), [Trait](trait-bids.md), and [Token](token-bids.md) bids.

{% hint style="info" %}
**Give your task a name.** There's a rename pencil in the task header — set a friendly name like "BAYC floor snipe" so you can find it later. It's cosmetic only; the bot doesn't care what it's called.
{% endhint %}

## The Collection panel

Once a collection loads, the left side of the editor fills with live data so you're not bidding blind:

<div align="left"><figure><img src="../.gitbook/assets/image (3).png" alt="" width="407"><figcaption></figcaption></figure></div>

* **Floor price** and **top bid** — split by marketplace (Blur in orange, OpenSea in blue), so you can see where the real action is.
* **Floor profit (after fees)** — what you'd clear buying at the top bid and dumping at floor, in ETH and %. Green = profit, red = underwater.
* **Collection facts** — chain, NFT type (ERC-721 / ERC-1155), total supply, whether Collection Offers and Trait Offers are enabled, and creator fees.
* **Per-trait prices** — when you've picked traits, each one shows its own floor and top bid.
* **Sales chart** and **socials** — recent sales history plus links out to the collection's Discord, X, and site.

## Duplicate guard

You can't create two identical tasks. If a task with the same **slug + bid mode + filters** already exists, Ethernyx blocks it — so you don't accidentally run the same strategy twice and fight yourself for the top spot.

***

Next: pick your strategy → [Collection Bids](collection-bids.md) · [Trait Bids](trait-bids.md) · [Token Bids](token-bids.md). Every field on the form is documented in [Parameters](parameters.md).
