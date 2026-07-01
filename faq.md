---
description: Quick answers to the questions people ask most.
icon: circle-question
---

# FAQ

## Getting started

**What is Ethernyx?**\
A cloud bidding bot for OpenSea and Blur. You connect a wallet, set up a task, and it bids, counter-bids, cancels stale offers, and re-lists your fills — 24/7, nothing running on your machine. Full intro on [Welcome](README.md).

**Do I need to download or install anything?**\
No. Ethernyx runs entirely in the cloud — open [app.ethernyx.io](https://app.ethernyx.io/) in any browser, including on your phone. No VPS, no node, no app.

**How do I sign in?**\
With your Web3 wallet (MetaMask, Rabby, WalletConnect, etc.). You sign a message — there's no password and no email. More in [Security](security.md).

**How much ETH do I need to start?**\
Around **0.2 ETH** is enough to poke around and see how everything works. To actually trade for real numbers, plan for **1 ETH or more** on the wallet.

## Bidding

**What's the difference between collection, trait, and token bids?**\
Collection = one offer on the whole collection. Trait = offers only on items with specific attributes. Token = offers on exact token IDs. Each is broken down on [Collection Bids](collection-bidder/collection-bids.md), [Trait Bids](collection-bidder/trait-bids.md), and [Token Bids](collection-bidder/token-bids.md).

**What happens when someone outbids me?**\
Ethernyx counter-bids automatically, the instant a higher offer lands — within your **Max Bid** ceiling. That's the whole point of the bot.

**My task isn't placing bids — why?**\
Usual suspects:

* Your **Max Bid** is below the current top bid (the card goes red — you literally can't take the top).
* The collection has **Collection/Trait Offers disabled** for your mode — switch modes.
* Your OpenSea nickname is **missing the prefix** (see below).
* Not enough **WETH/BETH** on the wallet to cover the offers.
* The task is **paused** — imported tasks always start paused.

**What do the red / amber task cards mean?**\
Red = you can't outbid the top with your current Max Bid. Amber = a limit (min floor, min profit) is holding you back, or half your token bids are out of reach. No tint = you're competitive. Details on [Managing Tasks](collection-bidder/managing-tasks.md).

**Can it automatically sell what I buy?**\
Yes — turn on **Autolist** on a bidding task, or use the [Floor Lister](floor-lister.md) to list and re-list your NFTs at the floor (or your target) and re-list instantly after a fill.

**What's arbitrage bidding?**\
Bidding on one marketplace based on the price of the other — e.g. buy on Blur, instantly dump into a higher OpenSea bid. Set your minimum acceptable profit with **Min Arbitrage**. See [Parameters](collection-bidder/parameters.md).

## Wallets & account

**Is my private key safe?**\
Yes — keys are encrypted at rest and isolated in a hardened private service that nothing else can reach; they never leave it and are never logged. The full breakdown is on [Security](security.md).

**Can I run multiple wallets?**\
Yes. Every plan supports multiple wallets (from 1 on Free up to 10 on Ultimate) — add them in [Settings](features/settings.md). See [Pricing](pricing.md).

**Why do I need the `ethernyx_dot_io_` nickname prefix on OpenSea?**\
It's how OpenSea bidding is enabled for your wallet through Ethernyx. Set it once (see [Wallet Setup](wallet-setup.md)), or grab the **No-Prefix** add-on to skip it and use any nickname.

## Billing

**How do payments work?**\
You pay in **ETH** on Ethereum, monthly or prepaid (3/6/12 months for up to 45% off). Every payment is validated on-chain before your plan activates. Full table on [Pricing](pricing.md).

**Can I change plans or get more than 150 bids/sec?**\
Yes — upgrade anytime, or open a ticket in [Discord](https://discord.gg/D6eYfJ7kc) for a **Custom** plan with higher limits.

## Support

**Where do I get help?**\
Join our [Telegram](https://t.me/ethernyx) or [Discord](https://discord.gg/D6eYfJ7kc) — team and community answer fast. Always double-check you're on our [Official Links](resources/official-links.md) to avoid scams.
