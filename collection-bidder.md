---
description: Explanation for the Collection Bidder Page
---

# 🔨 Collection Bidder

<div align="left"><figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure></div>

On Collection Bidder page you can see:

* **Header**
* **Tasks**

### Header:

1. **Task groups**: You can create an unlimited number of task groups for easy sorting. Modify and delete these groups at any time. Add new tasks to them.
2. **Search**: You can find any task by typing its slug
3. **"Select All" button**: Select all tasks from the list to move them to another group, bulk edit, start and stop, delete
4. **"Add Task" button**: Button for adding a new task to the task list
5. **Sorting**: Active / Inactive, By Creation Time, By Slug
6. **Grouping**: By Status, By Marketplace, By Group, By Collection



### Tasks list:

In task list you can see task cards with basic information about the collection, parameters. Change a task, start / stop it, delete it, see detailed information. Select several tasks by clicking on them for further work with the whole group at once

## Task Edit:

### Collection:

<div align="left"><figure><img src=".gitbook/assets/image (3).png" alt="" width="407"><figcaption></figcaption></figure></div>

Here you can see the collection details, chart, sales, flips, current floor profit etc.



### Parameters:

<div align="left"><figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure></div>

When creating or editing a task, you must specify the parameters. Here is the list of all parameters with decoding:

* **Collection Slug or Contract Address**: Enter collection slug or contract address. The collection data will be loaded automatically. If the system does not find the collection, you can try to add it by clicking the “Try to add collection” button or use a different slug.
* **Wallet Address**: Select the wallet you want to use in this task. If you haven't added a wallet yet, you can do it in [Wallet Setup](wallet-setup.md)
* **Marketplace**: Select marketplace for bidding (OpenSea, Blur of All for both)
* **Bid Mode**: Choose bid mode

> **Standard**: Standard mode for the entire collection. The bot will always try to bid the best top bid based on the parameters.
>
> **Smart**: Trait filter required. The bot will always try to put the best top bid on the trait attributes selected in the parameters, but calculating max bid on the global floor of the collection. Can be used to hide your bids from other bidders, keeping you the top offerer in the shadows.
>
> **Smart IDs (OpenSea only)**: Trait filter or IDs required. The bot will always try to put the best top bid on all tokens (or only selected ones) on the trait attributes selected in the parameters, calculating max bid on the global floor of the collection. Can be used to hide your bids from other bidders, keeping you the top offerer in the shadows, or if collection doesn't support trait bidding.
>
> **IDs (OpenSea only)**: Trait filter or IDs required. The bot will only bid on tokens that are specified in the IDs, uses token floor for calculating max bid.
>
> **0.01 Above (Blur Only)**: Same as standard.
>
> **Level Below (Blur Only)**: The bot will always put the bid at the level after the top bid. The bid will never be first on the list.
>
> **One Below (Blur Only)**:The bot will always put the bid at top bid - blur outbid margin. The bid will never be first on the list.
>
> **Matched (Blur Only)**: Specific bid, but never above max bid.

* **Min Profit %**: The minimum percentage of profit between your bid price and the floor price. For example, if the floor price is 1.2 ETH and your bid is 1 ETH, that’s a 20% profit. The bot always sets bids below your specified Min Profit Percent. So if your Min Profit Percent is set to 30%, the bot will place a bid at 0.92 ETH because 0.92 + 30% = 1.196 < 1.2.
* **Min Profit ETH**: The minimum profit in ETH. For example, if the floor price is 1.2 ETH, your bid is 1 ETH, and min\_profit\_eth is set to 0.3 ETH, the bot will place a bid of 0.9 ETH.
* **Min Arbitrage**: You can place bids based on bids from another marketplace. For example: a bid on Blur is 2 ETH, while the bid on OpenSea for the same collection is 3 ETH. The arbitrage profit (bid - fees) in this case is 1 ETH. If your bid on Blur gets filled, you can immediately sell the NFT into the higher bid on OpenSea. The Min Arbitrage parameter sets the minimum acceptable arbitrage profit in ETH—for instance: 0.1 ETH.
* **Max Bid**: The maximum bid amount in ETH. The bot will never place a bid above this value. Highly recommended to **ALWAYS** use this setting to avoid getting caught in unpleasant pump-and-dump situations and buying NFTs at an unfavorable price. **Values: 0.5, +2.5, +10%**. There is an option to use +X and +X%, but only if a trait filter is specified. Max Bid will be automatically calculated from the global bid of the collection + X ETHth or + X %. Can be useful for trait bidding.
* **Min Bid**: It sets the minimum bid the bot will place. This is useful for collections with very few or no bids, where the top bid might be far below reasonable limits. For example: the floor is 2 ETH, but the highest bid is just 0.05 ETH. Nobody would realistically sell for 0.05 ETH, so placing a 0.05 ETH bid hoping for a miracle is pointless. **Values: 0.5, +2.5, +10%**. There is an option to use +X and +X%, but only if a trait filter is specified. Min Bid will be automatically calculated from the global bid of the collection + X ETH or + X %. Can be useful for trait bidding.
* **Min Floor**: Minimum floor for collection / trait. If the floor falls below this value, the bot will stop bidding.
* **Quantity**: The number of bids the bot will place on a collection. If your ETH balance isn’t sufficient to cover all bids, the bot will use the maximum number possible. For example, if you want to place 100 bids but only have enough ETH for 20, the bot will place 20 bids.
* **Max Buy**: The maximum number of NFTs you want to purchase. If Max Buy is set to 1 and you purchase an NFT, the task will stop until you sell this NFT. Note: Even if quantity = 5 and max\_buy = 1, the bot will still place 5 bids, so there’s a chance you’ll acquire multiple NFTs simultaneously. The same risk applies when using Smart mode since the bot places one bid per trait.
*   **Min Bids Above**: Only used for farming Blur points; useless for flipping.

    If Min Bids Above > 0, Blur points farming mode is activated. The bot will count the number of bids above and equal to yours. For example, Min Bids Above = 200. Level 1 has 100 bids, level 2 has 50 bids, and level 3 has 80 bids. The bot will place a bid at level 3, because 100 + 50 + 80 > 200.
* **Blur Outbid Margin**: The margin it ETH with which the bot will outbid other participants offers. For example: 0.01
* **OS Default Margin**: Standard multiplier for margin on OpenSea. For example: 1

> On OpenSea, offers in ETH/WETH follows a tiered precision system based on price range:

<table data-full-width="false"><thead><tr><th>Offer Price</th><th>Decimals Allowed</th><th>Valid Bids (Examples)</th><th>Invalid Bids (Examples)</th></tr></thead><tbody><tr><td>0.0001-0.0999 ETH</td><td>4</td><td>0.0542 ETH</td><td>0.00005, 0.00992 ETH</td></tr><tr><td>0.100-0.999 ETH</td><td>3</td><td>0.235 ETH</td><td>0.1001, 0.9999 ETH</td></tr><tr><td>1.00+ ETH</td><td>2</td><td>1.05 ETH</td><td>1.003, 13.2002 ETH</td></tr></tbody></table>

> So the selected margin will multiply the current bid precision by the specified value.

* **OS Increased Margin**: Increased margin multiplier. Used for Smart, Smart IDs, IDs bid modes. Necessary for the offerer to be much higher than other bidder to increase the chance of selling to you specifically
* **Filters**: \
  **Traits**: When filled, all modes (except Smart) will place bids on specific traits, considering each trait’s floor price. If a trait has no listings, the bid will default to 0.01 ETH. You can select either a single trait attribute or all attributes by clicking on the "All" button. You can also select several traits at once, but only for Bid Modes Smart (IDs), IDs.\
  **IDs**: Only for Marketplace: OpenSea in bid modes: Smart IDs, IDs. Specific IDs on which the offers will be placed. You can specify any number of IDs from the collection. The bot will put an offerer on each token. It can also be used for bidding on ERC1155 NFTs.
* **Stop when max buy limit reached**: If True, the task will stop completely after reaching max buy and will not restart even after selling NFT. It will be necessary to manually start the task again. If False - the task will restart automatically if max buy slot becomes available again.

### Here's some tips:

{% hint style="warning" %}
1. Please use blur slug by default if blur for the collection exists, or contract address. Otherwise, the wrong collection may be found. Always check if the collection you are going to create a task for is the right one.
2. You can't use Smart mode without trait filter
3. You can't use +X and +X% Max / Min bid without trait filter
4. Only you are responsible for choosing the task parameters. Always check them before saving changes.
{% endhint %}
