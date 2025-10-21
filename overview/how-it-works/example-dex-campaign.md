# Example DEX Campaign

## Example DEX Campaign: Two Incentives in 10 Minutes

**What you'll build:** A two-part campaign that (1) attracts liquidity providers on day one and (2) keeps your top traders competing every week.

### Incentive 1 — LP Reward Program (Rebate)

**Goal:** Get more liquidity in your pools

**Setup:**

* **Type:** Rebate (Recurring)
* **Frequency:** Daily
* **Duration:** 30 days
* **Query:** New LP depositors with minimum threshold
* **Reward:** 10% bonus on qualifying deposits
* **Distribution:** Claim (72-hour window)

**Your Query:**

sql

```sql
SELECT 
  depositor_address as address,
  deposit_amount * 0.10 as amount
FROM lp_deposits
WHERE deposit_date BETWEEN '{startDate}' AND '{endDate}'
  AND deposit_amount >= {min_deposit}
  AND is_first_deposit = true
```

**Why it works:** Users see immediate rewards but must claim them regularly, keeping them engaged with your protocol.

**Safety settings:**

* Cap per wallet: 1,000 tokens
* Total campaign budget: 50,000 tokens
* Minimum deposit: $100

***

### Incentive 2 — Weekly Top Trader Leaderboard

**Goal:** Drive consistent trading volume

**Setup:**

* **Type:** Leaderboard (Recurring)
* **Frequency:** Weekly (resets every Monday)
* **Query:** Traders ranked by 7-day volume across multiple pairs
* **Reward:** Tiered payouts for Top 1/5/10/50
* **Distribution:** Claim (72-hour window after each week ends)

**Your Query:**

sql

```sql
SELECT 
  trader_address as address,
  SUM(trade_volume) as score
FROM trades
WHERE trade_date BETWEEN '{startDate}' AND '{endDate}'
  AND market_count >= 3
  AND total_volume >= {min_volume}
GROUP BY trader_address
ORDER BY score DESC
```

**Reward Tiers:**

* 1st place: 5,000 tokens
* Top 5: 2,000 tokens each
* Top 10: 1,000 tokens each
* Top 50: 500 tokens each

**Why it works:** Clear competition with predictable rewards. Traders know exactly what they're competing for each week.

***

### Bonus: First-Time Trader Rebate (Optional)

**Goal:** Smooth onboarding for new traders

**Setup:**

* **Type:** Rebate (One-off)
* **Duration:** First 7 days of campaign
* **Query:** First-time traders
* **Reward:** 0.5% of trading fees back
* **Distribution:** Claim (daily, 48-hour window)

**Your Query:**

sql

```sql
SELECT 
  trader_address as address,
  SUM(trading_fees) * 0.005 as amount
FROM trades
WHERE trade_date BETWEEN '{startDate}' AND '{endDate}'
  AND is_first_trade = true
```

***

### Quick Setup Checklist

#### 1. Create Your Queries

* **New LP Depositors** — Filters for first deposits above minimum threshold
* **Active Traders** — 7-day volume across 3+ markets
* **First-Time Traders** — New users within first week

#### 2. Configure Your Incentives

* **LP Rebate:** Daily recurring, 30-day campaign
* **Trading Leaderboard:** Weekly recurring, ongoing
* **Onboarding Rebate:** One-off, 7-day duration

#### 3. Set Distribution Methods

* All set to **Claim** with 72-hour windows
* Gives users flexibility to claim on their schedule
* Reduces gas costs vs. airdrops

#### 4. Add Safety Rails

* Per-wallet caps to prevent whales from dominating
* Total budget limits per epoch
* Query filters to exclude wash trading patterns

#### 5. Measure Success

Track these metrics in your incentive dashboard:

* Total LP added
* Weekly active traders
* Claim rate (% of eligible users who claim)
* Cost per engaged wallet

Adjust your query thresholds and reward tiers weekly based on results.

***

### What You Get

Instead of building indexing infrastructure, ranking systems, claim interfaces, and analytics dashboards, you just:

1. Write your queries
2. Configure your incentives
3. Set your budgets
4. Launch

Torque handles the rest.

***

### Want to Expand Later?

Once these core incentives are running, consider adding:

**Raffle for Long-Tail Engagement**

* Randomly reward 100 users from anyone who traded this week
* Keeps smaller traders engaged even if they can't compete with whales

**Direct Distribution for Milestones**

* Celebrate hitting 10,000 total traders
* One-time reward to everyone who participated

Both are one-click additions once your base campaign is live.
