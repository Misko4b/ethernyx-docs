---
description: Groups, search, bulk actions, import/export — running a lot of tasks at once.
---

# Managing Tasks

Once you're running more than a handful of tasks, the list view is where you live. Here's everything you can do with it.

## The toolbar

At the top of the Collection Bidder page:

* **Search** — type to filter by task name, collection slug, trait, or token ID. Slug/name matches float to the top.
* **Status filter** — `All Tasks` · `Active` · `Inactive`.
* **Sort** — `Created ↓` (newest first, default) · `Created ↑` · `Slug A-Z` · `Slug Z-A`.
* **Group by** — `No grouping` · `Status` · `Marketplace` · `Group` · `Collection` · `Wallet`. Purely visual — buckets the cards so a big list stays readable.
* **Select All** — selects every task currently visible (respects your search/filter). Click again to clear.
* **Import** / **Add Task** — bring tasks in from a file, or create one from scratch.

## Groups

Groups are folders for your tasks — sort them however makes sense (by client, by strategy, by chain, whatever).

* **New Group** — the `+` in the groups row. Give it a name, hit create.
* **Rename** — the pencil next to a group.
* **Delete** — the trash next to a group. ⚠️ Deleting a group **also deletes every task inside it** — you'll get a confirmation with the count first.
* **Filter** — click a group name to show only its tasks; **All Tasks** shows everything.
* **Move tasks in** — select tasks, hit **Move**, pick a group (or **No Group** to pull them out).

## Selecting tasks & bulk actions

Click any card to select it (it gets a green ring). Select as many as you want — or use **Select All**. A bulk action bar appears with a live count:

| Action | What it does |
|---|---|
| **Start** | Activate all selected tasks |
| **Stop** | Pause all selected tasks |
| **Move** | Send them to a group |
| **Edit** | Open [bulk edit](#bulk-edit) |
| **Export** | Download them as an `.xlsx` file |
| **Delete** | Remove them (with confirmation) |
| **Clear** | Deselect everything |

### Bulk edit

Bulk edit changes one or more fields across every selected task at once. The trick: **each field has its own checkbox**. Only the fields you tick get changed — everything else on each task stays exactly as it was.

You can bulk-edit wallet, marketplace, bid mode, min profit % / ETH, min arbitrage, max bid (+ base), min bid (+ base), min floor, quantity, max buy, min bids above, OS margins, Blur margin, stop-at-max-buy, place-below-top, undercut, autolist (+ min price), offer duration, and the per-task wallet blacklist.

Slug, traits, and token IDs aren't bulk-editable — those are per-collection. Hit **Apply to N tasks** and any active task restarts automatically with the new settings.

## Import & export

### Export

Select tasks → **Export**. You get an `.xlsx` (Excel) file named `Ethernyx.io Bidding Bot Export <timestamp>.xlsx` with every parameter of every task, plus a **Help** sheet explaining the columns. Great for backups or bulk-editing in a spreadsheet.

### Import

Hit **Import** and pick your source:

* **Ethernyx (.xlsx)** — our own format. Round-trips perfectly with export, so this is how you back up, tweak in Excel, and re-upload. There's a **Download template** button for a blank sheet.
* **nftper (.csv)** — coming from another bot? Drop your nftper CSV and Ethernyx converts it. You'll need to **pick a wallet** for the imported tasks first.

Import runs in stages, and you see each one:

1. **Preview** — how many rows are valid, which have errors (skipped), and which import with adjustments. Bad rows are listed with the reason.
2. **Adding collections** — any collection Ethernyx doesn't know yet gets registered, in batches of 10. Big lists take a minute — keep the window open.
3. **Importing** — the valid tasks get created in one shot.
4. **Done** — a summary of created vs. failed, with reasons for anything that didn't make it (bad collection, duplicate, etc.).

{% hint style="warning" %}
**Imported tasks are created paused.** Always open each one and check the parameters — wallet, max bid, mode — before you start it. Don't bulk-start a fresh import blind.
{% endhint %}

## Task cards

Each card is a live dashboard for one task:

* **Name & rename** — your friendly name (or the collection name), with an inline pencil to change it.
* **Wallet** — the short `0x…` address it runs on.
* **Trait / ID chips** — the traits or token IDs you're bidding, each with its own live floor (`F`) and top bid (`B`). Green chip = your max bid can take the top spot; red chip = it can't.
* **Live stats** — floor, top bid, floor profit, your min-profit settings, bid range, margins, and mode — as much as the screen fits.
* **Risk color** — the whole card tints itself:
  * **Red** — you can't outbid the top (your max bid is below it), or for token bids, 75%+ of your tokens are out of reach.
  * **Amber** — a limit is holding you back (min floor, min profit), or 50–74% of token bids are out of reach.
  * **No tint** — you're good, you can take the top.
* **Buttons** — start/stop, edit, live logs, delete, and **details** (the `⋯` opens a full read-only breakdown of every parameter).

{% hint style="info" %}
The red/amber tint is your at-a-glance health check. If a card is red, the bot literally can't win the top spot with your current Max Bid — either raise it or accept you're bidding below the leader.
{% endhint %}
