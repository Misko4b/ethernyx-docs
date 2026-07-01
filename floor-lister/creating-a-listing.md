---
description: Set up a listing task — token, price, marketplace.
---

# Creating a Listing

Hit **Add Task** (or **Create Task** from an [owned asset](owned-assets.md)) to open the listing form. It's shorter than a bidding task — no bid modes, just what to list and the floor you won't go below.

<div align="left"><figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure></div>

## The fields

* **Collection Slug or Contract Address** — loads the collection automatically. If it's not found, hit **Try to add collection** or use a different slug (Blur slug or contract works best).
* **Wallet Address** — the wallet that holds the NFT. Defaults to your main wallet.
* **Marketplace** — **OpenSea**, **Blur**, or **All** (list on both).
* **Token ID** — the ID of the NFT you're listing.
* **Minimum Price (ETH)** — the bot **never lists below this**. Your protection against dumping into a crashed floor.
* **Trait filter** *(optional)* — price against a specific trait's floor instead of the whole collection.
* **Name** *(optional)* — a friendly label in the task header; cosmetic only.

The **Collection panel** on the side shows live floor, top bid, and floor profit so you can pick a sensible minimum.

## What the bot does with it

* Lists at the **current floor**, but clamps to your **Minimum Price** — never lower.
* Re-prices as the floor moves and **re-lists instantly** when a listing fills.
* On first run it handles the **collection approval** on the chosen marketplace(s) for you. If approval fails on one side while you're on **All**, it falls back to the other.
* Listing length and the gas ceiling come from your [Listing Settings](../features/settings.md) (minimum duration 15 minutes).

## Tips

{% hint style="warning" %}
* Use the **Blur slug or contract address** so you don't load the wrong collection — always double-check the loaded collection before saving.
* Your **Minimum Price** is the important one. Set it to the lowest you'd actually accept, or you risk selling into a dip.
* You own your parameters — the bot lists exactly what you tell it to.
{% endhint %}
