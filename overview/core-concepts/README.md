# Core Concepts

## Core Concepts

Torque is built around three components that work together to power your incentive campaigns:

### 1. Queries

**What they do:** Define who qualifies for rewards using SQL logic.

Queries run on pre-indexed Solana data and return a list of wallet addresses with their corresponding scores or amounts. You can use templates, write custom SQL, or get help from AI.

**Key features:**

* Real-time data from major Solana programs
* Flexible filters (minimum thresholds, time windows, anti-wash trading)
* Reusable across multiple incentives
* For recurring campaigns: automatically runs each cycle with `startDate` and `endDate` parameters

**Example:** Find all traders who completed $10,000+ volume across 3+ token pairs in the last 7 days.

***

### 2. Incentives

**What they do:** Determine how rewards are allocated to qualified users.

Incentives connect your query to a distribution method and define the rules for how rewards are calculated.

***

### 3. Lists

**What they do:** Lock in exactly who gets what before distribution.

At the end of each epoch, your query runs and generates a list—an immutable snapshot of wallet addresses and their exact token allocations. You review it, approve it, and distribution begins.

**Two types:**

* **System-generated** — Created automatically from your query (immutable once approved)
* **Custom uploads** — Manual lists you create for allowlists, exclusions, or custom allocations

**Why lists matter:** They ensure transparency and prevent changes mid-distribution. What you approve is what gets distributed.

***

### Incentive Lifecycle

#### 1. Build Your Query

Write SQL that defines who qualifies. Set filters, thresholds, and time windows.

#### 2. Configure Your Incentive

Choose your type (Leaderboard, Raffle, Rebate, Direct), set your schedule (recurring or one-off), and connect your query.

#### 3. Set Distribution Method

* **Claim** — Users claim rewards themselves (default, saves gas)
* **Airdrop** — Automatic distribution (convenient but more expensive)

Configure claim windows (1-72 hours) if using Claim method.

#### 4. Review & Approve

Before each distribution, preview the list. Make adjustments if needed. Once approved, the list locks and rewards go out.

#### 5. Measure & Optimize

Track participation rates, cost per user, and activity driven. Adjust your query thresholds and reward tiers between epochs to improve results.

***

**The key difference:** Torque handles all the complex infrastructure—indexing, calculation, list generation, distribution, and analytics. You just define the logic and launch

