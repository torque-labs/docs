---
description: Learn How Torque Works
hidden: true
---

# How it Works

## How It Works

### 1. Plan Your Campaign

Start by answering these key questions:

1. **What's your budget?** How many tokens are you allocating?
2. **Is it recurring or one-off?** Weekly competition or single event?
3. **What are your success metrics?** Volume? Users? Retention?
4. **What do you want to optimize?** Minimum thresholds? Reward tiers? Frequency?

***

### 2. Build Your [Query](../core-concepts/queries.md)

Queries define who qualifies for rewards. You can start with a template or write custom SQL.

**Choose your approach:**

* **Use a Template** — Select from pre-built queries (top traders, LP holders, etc.)
* **Write Custom SQL** — Define your own qualification logic
* **Get AI Help** — Let Torque Intelligence assist with query writing

**What your query needs:**

* `address` column (wallet addresses)
* `score` or `amount` column (for allocation)
* For recurring incentives: `startDate` and `endDate` parameters

**Example query:**

sql

```sql
SELECT 
  trader_address as address,
  trading_volume as score
FROM trades
WHERE trade_date BETWEEN '{startDate}' AND '{endDate}'
  AND trading_volume >= {min_volume}
```

***

### 3. Configure Your [Incentive](../core-concepts/incentives.md)

Choose how rewards are distributed based on your goal:

**Incentive Types:**

* **Leaderboard** — Reward top performers by rank (top 10 traders get tiered rewards)
* **Raffle** — Random selection from qualified users (100 winners from active users)
* **Rebate** — Reward based on activity metric (0.5% back on trading fees)
* **Direct** — One-time distribution to specific addresses (quick reward distribution)

**Set your schedule:**

* Recurring: Daily, Weekly, or Monthly cycles
* One-off: Single distribution event
* Start and end dates

**Configure distribution:**

* **Claim** — Users claim their rewards (gives them flexibility)
* **Airdrop** — Automatic distribution (convenient but costs more gas)
* Set claim windows (1-72 hours)

***

### 4. Review & Launch

Before each distribution (called an "epoch"), you'll get to:

1. **Preview the** [**list**](../core-concepts/lists.md) — See exactly who qualifies and how much they get
2. **Approve** — Lock the list and start distribution

**Remember:** Once an epoch starts, the list is locked. Any changes to the query you make will apply to the next cycle.

***

### 5. Track & Optimize

Monitor your campaign performance in real-time:

**Key metrics to watch:**

* Participation rate (how many qualified users claimed)
* Cost per engaged wallet
* Total activity driven (volume, deposits, trades)
* Epoch-over-epoch trends

**Optimize continuously:**

* Adjust query thresholds between epochs
* Tweak reward tiers based on results
* Add or remove qualification criteria
* Scale budgets up or down

**For recurring incentives:** Changes take effect in the next epoch, so you can iterate weekly without disrupting active distributions.

***

### Bonus: Build It Into Your Product

Developers can integrate Torque directly into their applications:

**Integration options:**

* **Platform UI** — Use Torque's hosted interface for easy setup
* **API & SDK** — Build custom incentive flows in your own product
* **Webhooks** — Trigger actions based on onchain events

**What you can build:**

* Live leaderboards showing real-time rankings
* Custom claim pages branded for your protocol
* Automated incentive programs tied to your product milestones

Torque handles the heavy lifting—indexing, calculation, distribution, and analytics—so you can focus on your product.
