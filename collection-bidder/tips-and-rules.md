---
description: The rules the form enforces, and the mistakes that cost people money.
---

# Tips & Rules

A few things that trip people up. Read this before you run real tasks.

## Mode & filter rules

The form enforces these — if something's greyed out or throwing an error, this is why:

* **Smart mode needs a trait filter.** No traits = nothing to bid on.
* **Relative Max/Min Bid (`+X`, `+X%`) needs a target** — a trait filter, token IDs, or a `Smart IDs` / `IDs` mode. Without one, use absolute numbers.
* **Token IDs are OpenSea-only**, and only in `Smart IDs` / `IDs` modes.
* **AND-combined traits are OpenSea-only**, in `Smart IDs` / `IDs`. On Blur you can monitor composite traits but not bid them.
* **Item (token) bidding is Starter and up.** Free/Lite do collection and trait bids.
* **Trait offers must be enabled on the collection** (OpenSea) for Smart mode. If they're off, go token bids instead.

## Don't lose money

{% hint style="danger" %}
**Always set a Max Bid.** It's the single most important setting. Without it, a pump-and-dump or a fat-finger top bid can drag your offer up and leave you holding an NFT you massively overpaid for. Set it. Every time.
{% endhint %}

* **Watch Quantity vs Max Buy.** They're independent. Quantity 5 + Max Buy 1 still means 5 live offers — several can fill in the same block. Only run quantity higher than max buy if you can afford to catch them all.
* **Thin traits price at 0.01 ETH.** A trait with no listings has no floor to price against, so the bid defaults to 0.01 — sanity-check bids on illiquid traits.
* **Mind Min Floor.** It's your kill switch: if the floor tanks below it, the bot stops. Set it somewhere sane so you're not bidding into a freefall.

## Get the right collection

{% hint style="warning" %}
**Use the Blur slug or the contract address** when a collection exists on Blur. Slugs differ between marketplaces, and the wrong slug can load the wrong collection. Always eyeball the loaded collection — name, image, contract — before you save.
{% endhint %}

## After importing

Imported tasks land **paused** on purpose. Open each one, check the wallet, mode, and Max Bid, then start it. Never bulk-start a fresh import without a look.

## The bottom line

{% hint style="info" %}
**You own your parameters.** Ethernyx does exactly what you tell it, fast. It won't second-guess a bad Max Bid or a risky quantity. Double-check every task before you hit start — the bot is only as smart as its settings.
{% endhint %}
