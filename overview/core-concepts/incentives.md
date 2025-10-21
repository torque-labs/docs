# Incentives

## Incentives

### Overview

An **incentive** defines how participants compete and how rewards are allocated. Incentives are campaign wrappers that organize your reward distributions, connecting queries, distribution logic, and token budgets into a cohesive reward program.

### Incentive Types

Torque supports four types of incentives, each designed for different use cases:

| Type            | Description                            | Use Case                                               | Best For                      |
| --------------- | -------------------------------------- | ------------------------------------------------------ | ----------------------------- |
| **Leaderboard** | Rewards based on ranked position       | Top 10 traders get rewards based on volume             | Competition-driven engagement |
| **Rebate**      | Rewards based on calculated metric     | Users get .5% back on trading fees                     | Volume incentivization        |
| **Raffle**      | Random selection from qualified users  | 100 winners from active users                          | Community engagement          |
| **Direct**      | One-off rewards not tied to incentives | Quickly distribute rewards to users based on your file | Quick use                     |

### How Incentives Work

#### Epochs and Distribution Cycles

Incentives operate on a cycle called an **epoch**. Each epoch follows this flow:

1. **Query Execution** - Your query runs to identify qualifying participants
2. **List Generation** - Torque creates an immutable snapshot of addresses and allocations
3. **Review & Approval** - You review the list and can make adjustments if needed
4. **Distribution** - Rewards are distributed via claim or airdrop

**Important**: Once an epoch starts, you cannot change the query or incentive mechanics. All updates will take effect in the next epoch.

### Incentive Configuration

#### Frequency Settings

| Setting                    | Options                  | Description                 | Example                            |
| -------------------------- | ------------------------ | --------------------------- | ---------------------------------- |
| **Frequency**              | Recurring / One-off      | Campaign frequency          | Weekly competition vs single event |
| **Start Date & Time**      | Date/Time picker         | When campaign begins        | Jan 15, 2024 9:00 AM UTC           |
| **End Date & Time**        | Date/Time picker         | When campaign ends          | Jan 22, 2024 9:00 AM UTC           |
| **Distribution Frequency** | Daily / Weekly / Monthly | For recurring distributions | Weekly leaderboard resets          |

#### Distribution Settings

| Setting             | Options         | Description                  | Client Benefit                 |
| ------------------- | --------------- | ---------------------------- | ------------------------------ |
| **Method**          | Claim / Airdrop | How users receive rewards    | User choice vs automatic       |
| **Claim Window**    | 1-72 hours      | How long claim stays active  | Flexibility for user schedules |
| **Claim Open Time** | Configurable    | When claims become available | Coordinate with announcements  |

### Creating an Incentive

#### Step 1: Choose Your Type

Select the incentive type that matches your goal:

* **Leaderboard** for ranked competitions
* **Rebate** for performance-based rewards
* **Raffle** for random / weighted randomization selection
* **Direct** for one-time distributions

#### Step 2: Configure Schedule

Set your campaign timing:

* Choose **Recurring** for ongoing programs or **One-off** for single events
* Set start and end dates
* For recurring incentives, choose your distribution frequency

#### Step 3: Connect Your Query

* Select an existing query or create a new one
* Ensure your query returns the required columns (`address` and `score`/`amount`)
* Preview results to verify accuracy

#### Step 4: Set Distribution Parameters

* Choose your distribution method (Claim or Airdrop)
* Set token type and budget allocation
* Configure claim windows if using the Claim method

#### Step 5: Review & Launch

* Preview your configuration
* Review the generated list for the first epoch
* Launch when ready

### Incentive Properties

* **Reusability**: One query can power multiple incentives with different distribution logic
* **Immutability**: Lists are locked once an epoch begins
* **Update Cadence**: Changes to recurring incentives take effect in the next epoch
* **History Tracking**: All incentive changes are logged for audit purposes

### Example: Weekly Trading Leaderboard

Let's say you want to reward your top traders each week:

1. **Type**: Leaderboard
2. **Frequency**: Recurring
3. **Distribution Frequency**: Weekly
4. **Query**: Top traders by volume
5. **Distribution**: Top 10 get tiered rewards (1st place gets 1000 tokens, 2nd gets 750 tokens, etc.)
6. **Method**: Claim (72-hour window)

Each Monday at 1200 AM UTC, the query runs, generates a new list, and distributor. The team would need to go in and fund the distributor to launch the distribution.
