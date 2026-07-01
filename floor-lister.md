---
description: List and re-list your NFTs at the floor, automatically.
icon: list-radio
---

# Floor Lister

The Floor Lister is the **sell side** of Ethernyx. Point it at an NFT you own, and it lists it — then keeps the price in line with the floor and **re-lists instantly** after a fill or a floor move. Your inventory stays on the market at a competitive price without you babysitting a single listing.

Works on **OpenSea** and **Blur**.

<div align="left"><figure><img src=".gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure></div>

The page has two tabs:

* **[Owned Assets](floor-lister/owned-assets.md)** — every NFT across your wallets, with one-click task creation.
* **[Tasks](floor-lister/managing-tasks.md)** — your listing tasks as live cards you can start, stop, group, and bulk-edit.

## How it works

Pick a token, set a **minimum price**, choose the marketplace. From there Ethernyx:

* Lists your NFT at the **floor** — but never below your minimum price.
* Watches the collection and **re-prices** when the floor moves.
* **Re-lists instantly** the moment a listing fills (or gets stale).
* Handles the marketplace **approvals** for you on the first run.

Set it up on [Creating a Listing](floor-lister/creating-a-listing.md), then manage everything from [Managing Tasks](floor-lister/managing-tasks.md).

{% hint style="info" %}
Listing duration and the gas ceiling for on-chain steps (approvals, wrapping) come from your global **Listing Settings** — see [Settings](features/settings.md).
{% endhint %}
