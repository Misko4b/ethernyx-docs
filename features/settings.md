---
description: Your wallets, global bidding/listing defaults, blacklist, and add-ons.
---

# ⚙️ Settings

The Settings page is where you manage your wallets and set the **global defaults** that pre-fill every new task. Change anything here and hit **Save Changes** (top of the page) to apply it.

<figure><img src="../.gitbook/assets/image (1).png" alt="" width="563"><figcaption></figcaption></figure>

## Wallet Settings

Add, generate, and manage the wallets your tasks run on. Each wallet shows:

* **Address** — with a copy button, and the date you added it.
* **Balance** — ETH, WETH, and BETH, with a refresh button.
* **OpenSea profile** — avatar, nickname, and a status badge: **Ready for OpenSea** (green — prefix is set) or **Missing prefix** (yellow — fix it in [Wallet Setup](../wallet-setup.md) before OpenSea tasks will run).
* **Select as Main** — makes it the default wallet on new tasks; its nickname and avatar also become your Ethernyx profile.

Manage them with:

* **Generate Wallet** — spins up a fresh wallet. Save the private key (you only see it once), then confirm.
* **Add Wallet** — import an existing one by private key (`0x` + 64 hex chars).
* **Delete** — removes a wallet. You'll get a confirmation showing how many tasks it'll take down with it (with a short countdown so you can't fat-finger it).

## Bidding Settings

Defaults for every new bidding task:

* **Default Marketplace** — `All`, `OpenSea`, or `Blur`.
* **OpenSea Default Outbid Margin** — the standard outbid multiplier on OpenSea.
* **OpenSea Increased Outbid Margin** — the bigger multiplier used by `Smart`, `Smart IDs`, and `IDs` modes.
* **Blur Outbid Margin** — the ETH step you outbid by on Blur (e.g. 0.01).
* **Deposit Destination** — where auto-deposited funds go: `OpenSea`, `Blur`, or `Separate (50/50)`.
* **Minimum Wallet Balance** — the balance to keep on your wallet after auto-depositing to a marketplace. Set it to **9999 to turn auto-deposits off**.

### Bid logic & offer duration defaults

Defaults for item-bidding tasks (`IDs` / `Smart IDs`). Each task can override these — full details on the [Token Bids](../collection-bidder/token-bids.md) page.

* **Place bids below top bid** *(default: on)* — still post an offer below the top when it's out of Max Bid reach.
* **Undercut when far above 2nd bid** *(default: on)* — trim your offer to stay #1 without overpaying.
* **Offer duration** *(OpenSea only)* — how long offers live: min 610 sec (~10 min), max 7 days, default 1 hour. Blur is fixed at 7 days.

## Listing Settings

Defaults for the [Floor Lister](../floor-lister.md):

* **Default Marketplace** — `All`, `OpenSea`, or `Blur`.
* **Listing Duration** — how long listings stay up (minimum 15 minutes).
* **Max Gas Price (Gwei)** — the gas ceiling for on-chain actions (BETH deposit, WETH wrap, collection approvals).

## Blacklisted wallets (global)

A list of wallet addresses the bot will **never place item offers on** (`IDs` / `Smart IDs` modes). Applies across every task and merges with each task's local blacklist. Useful when someone's baiting your offers with junk tokens.

* Up to **50 addresses**, format `0x` + 40 hex chars.

## Add-ons

* **No Prefix** — `0.04 ETH/month`. Removes the required `ethernyx_dot_io_` prefix from your OpenSea nickname, so you can run OpenSea tasks with any nickname on your wallet. **Included free on Ultimate.**

{% hint style="info" %}
After changing anything, hit **Save Changes** — nothing applies until you do.
{% endhint %}
