---
description: Explanation for the Floor Lister Page
icon: list-radio
---

# Floor Lister

<div align="left"><figure><img src=".gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure></div>

<div align="left"><figure><img src=".gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure></div>

On Floor Lister page you can see:

* **Header**
* **Tasks**
* **Owned Assets**

### Header:

1. **Task groups**: You can create an unlimited number of task groups for easy sorting. Modify and delete these groups at any time. Add new tasks to them.
2. **Search**: You can find any task by typing its slug
3. **"Select All" button**: Select all tasks from the list to move them to another group, bulk edit, start and stop, delete
4. **"Add Task" button**: Button for adding a new task to the task list
5. **Sorting**: Active / Inactive, By Creation Time, By Slug
6. **Grouping**: By Status, By Marketplace, By Group, By Collection

### Owned Assets:

In Owned Assets you can see all NFTs on all added wallets, as well as quickly create a task on any of them by clicking "Create Task"

### Tasks list:

In task list you can see task cards with basic information about the collection, parameters. Change a task, start / stop it, delete it, see detailed information. Select several tasks by clicking on them for further work with the whole group at once

## Task Edit:

### Collection:

<div align="left"><figure><img src=".gitbook/assets/image (3).png" alt="" width="407"><figcaption></figcaption></figure></div>

Here you can see the collection details, chart, sales, flips, current floor profit etc.



### Parameters:

<div align="left"><figure><img src=".gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure></div>

When creating or editing a task, you must specify the parameters. Here is the list of all parameters with decoding:

* **Collection Slug or Contract Address**: Enter collection slug or contract address. The collection data will be loaded automatically. If the system does not find the collection, you can try to add it by clicking the “Try to add collection” button or use a different slug.
* **Wallet Address**: Select the wallet you want to use in this task. If you haven't added a wallet yet, you can do it in [Wallet Setup](wallet-setup.md)
* **Marketplace**: Select marketplace for bidding (OpenSea, Blur of All for both)
* **Token ID**: Token ID of your NFT
* **Minimum Price (ETH)**: Minimum price in ETH. The bot will never list nft below this threshold.
* **Filters**:\
  Trait filter: If selected, the bot will  consider NFTs and floor only on that trait.

### Here's some tips:

{% hint style="warning" %}
1. Please use blur slug by default if blur for the collection exists, or contract address. Otherwise, the wrong collection may be found. Always check if the collection you are going to create a task for is the right one.
2. Only you are responsible for choosing the task parameters. Always check them before saving changes.
{% endhint %}
