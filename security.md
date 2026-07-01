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

* Sign your **bids** and **listings** — off-chain marketplace orders (EIP-712 / Seaport) that OpenSea and Blur read to place your offers.
* **Wrap your ETH into WETH** and **deposit into the Blur bidding pool (BETH)** — the balances OpenSea and Blur need to back your bids. These funds stay **on your own wallet**, just in the form each marketplace requires; they aren't sent anywhere.

**It cannot:**

* Transfer, withdraw, or move your ETH or NFTs to any outside address.
* Send your funds to anyone.
* Do anything beyond funding and placing the bids and listings you set up.

The bot only ever acts **within the parameters you set** on a task. It can't drain a wallet or move your assets out — placing your bids and listings (and funding them as WETH/BETH on your own wallet) is the only thing it's built to do.

## Sign-in with no passwords

You log in by **signing a message with your wallet** (MetaMask, Rabby, WalletConnect) — no password, no email. This is **far safer than a password**: there's no credential to phish, leak, or reuse, and nothing sitting in a database to steal. The only key to your account is your wallet's signature, so **only you can get in** — nobody else can reach your account, your tasks, your keys, or your funds.

For an extra layer, your **login session expires every 12 hours** — after that you sign a fresh message to continue, so even a stolen session token is dead within half a day.

To be completely clear: **no one — under any circumstances — can access your tasks, your keys, or your funds. Not us, not an attacker, no one but you.**

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
