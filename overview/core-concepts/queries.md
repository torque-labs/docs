# Queries

### Overview

A **query** is a valid SQL statement that defines who qualifies for rewards through an incentive. Examples of queries could be buy and hold, trading competitions, liquidity provisioning, or program specific queries to your protocol.&#x20;

Queries are the foundation of Torque's reward distribution system, allowing you to target specific users based on on-chain behavior, metrics, or custom logic.

### Query Requirements

#### Basic Structure

All queries must return at least **two columns**:

* **`address`** - The wallet address of the recipient
* **`score`** or **`amount`** - A numeric value used for allocation

#### Recurring Incentive Parameters

To use a query with a recurring incentive, you must include two time-based parameters and return at least two columns

* **`startDate`** - The beginning of the evaluation period
* **`endDate`** - The end of the evaluation period

**Columns**

* **`address`  -** the address of the user's score or allocated amount
* **`score or amount`** - the calculated metric for determining the rewarded amount (rebate) or score (leaderboard / raffles)&#x20;

### How Queries Work

Torque's engine uses your query to power the entire incentive lifecycle:

1. **Calculation** - Runs your query to identify qualifying addresses
2. **Allocation** - Applies distribution logic based on the scores/amounts returned and the distribution mechanics
3. **Distribution** - Allocates tokens to an onchain distributor upon funding.

The specific behavior depends on your incentive type (Leaderboard, Raffle, Rebate, or Direct).

### Example: Rewarding Token Holders

Let's say you're a token creator who wants to reward users for holding your token. Here's how you'd set it up:

#### Step 1: Select or Create Your Query

Choose a pre-defined query from the library or write your own SQL.

<figure><img src="../../.gitbook/assets/Screenshot 2025-10-21 at 2.16.05 PM.png" alt=""><figcaption></figcaption></figure>

#### Step 2: Configure Parameters

Set your custom parameters along with the required time parameters:

* `startDate` - Epoch start date
* `endDate` - Epoch end date
* `token_mint` - Your token's mint address
* `min_balance` - Minimum holding threshold

<figure><img src="../../.gitbook/assets/Screenshot 2025-10-21 at 2.16.29 PM.png" alt=""><figcaption></figcaption></figure>

#### Step 3: Test Your Query

Run the query to verify the results look correct and return the expected addresses and scores.

<figure><img src="../../.gitbook/assets/Screenshot 2025-10-21 at 2.16.14 PM.png" alt=""><figcaption></figcaption></figure>

#### Step 4: Create Your Incentive

Click **"New Incentive"** and complete the setup flow, selecting your query and configuring your distribution settings.
