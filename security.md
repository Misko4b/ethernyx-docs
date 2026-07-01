---
description: How Ethernyx protects your private keys and your funds.
icon: shield-halved
---

# Security

Trusting a bot with a wallet is a big deal — you should know exactly how your keys are handled. Here's the honest, complete picture.

## Your key is encrypted before it's ever stored

The moment you add or generate a wallet, your private key is **encrypted with industry-standard public-key cryptography** (libsodium / NaCl sealed-box) — before it touches any database.

What actually gets saved is an **encrypted blob**, nothing else. Your key is **never stored in plaintext**, anywhere, ever. Even someone with full read access to the database sees only ciphertext they can't unlock.

## Only one isolated service can decrypt it

The key that can decrypt your wallet lives in a **single hardened, private service** — the one that runs the bot. Nothing else has it: not the website, not the public API, not the database.

* That decryption key is **entered by hand when the service starts** and is **never written to disk**. It's wiped from memory right after startup.
* Your wallet key is only ever decrypted **in memory, for the split second it takes to sign** an offer or listing — then it's **immediately zeroed out** of memory.
* Keys are **never written to disk and never logged.** Logs only ever reference a user ID and the first few characters of a wallet address.

## Keys never leave that service

Ethernyx is built as separate, isolated services on purpose:

* The **public side** (website + API) can *encrypt* keys and store the encrypted blob — but it **cannot decrypt anything**. It never holds a usable key.
* The **private side** (the bot) is the only place keys are decrypted, and it **only accepts requests from our own backend** — locked down with an IP allow-list *and* a secret token. There's no public door to it.

Your key never gets emailed, exported, sent to a third party, or moved off that service. Signing happens inside; the key stays inside.

## What the bot can — and can't — do

Being straight with you: to bid and list for you, the bot **does** sign with your key. Here's exactly what that means.

**It can:**

* Sign **offers (bids)** and **listings** — the marketplace orders you set up in your tasks.

That's it. These are **off-chain signatures** (EIP-712 / Seaport orders) that OpenSea and Blur read to place your bids and listings.

**It cannot:**

* Transfer, withdraw, or move your ETH or NFTs anywhere.
* Send funds to any address.
* Run arbitrary on-chain transactions (no swaps, no transfers, no approvals you didn't trigger).

The bot only ever acts **within the parameters you set** on a task. It can't drain a wallet, because placing a signed bid or listing is the only thing it's built to do with your key.

## Sign-in with no passwords

You log in by **signing a message with your wallet** (MetaMask, Rabby, WalletConnect). There's no password and no email to leak — just a Web3 signature that proves the wallet is yours.

## Payments are verified on-chain

Every subscription payment is **checked against the Ethereum blockchain** before your plan activates — the transaction has to be confirmed, sent to the right address, for the right amount, and recent. No off-chain "trust me" — the chain is the source of truth.

## No secrets in your browser

Our web app ships through a hardened production build with an **automated leak scan** — no source maps, no debug data, no developer paths, nothing sensitive baked into what your browser downloads.

## Smart habits on your end

Security is a two-way street. A few things we always recommend:

{% hint style="warning" %}
* **Save your private key when you generate a wallet** — Ethernyx shows it once and can't recover it for you.
* **Use a dedicated trading wallet**, not your main vault. Fund it with what you're actively trading — that's just good practice with any bot.
* **Never share your private key** with anyone. We will never DM you or ask for it.
* Only ever use our [Official Links](resources/official-links.md).
{% endhint %}
