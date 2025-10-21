# Lists

## Lists

### Overview

A **list** is your final roster of wallet addresses and how much each one gets. Think of it as the spreadsheet that determines exactly who receives rewards and how many tokens they get. Torque creates these automatically from your queries, but you can also upload your own for full control.

### Types of Lists

#### Automatic Lists

Every time your incentive runs, Torque automatically creates a list based on your query results. These lists are locked once created—what you see is what gets distributed.

**What's included:**

* Wallet addresses of everyone who qualified
* Their scores or metrics from your query
* The exact token amount they'll receive
* A timestamp for easy reference

**When they're created:**

* At the end of each cycle for recurring incentives
* Right before rewards go out
* After you've had a chance to review everything

#### Custom Lists

Sometimes you need more control. Maybe you want to reward a specific group, exclude certain wallets, or manually set allocations. That's what custom lists are for.

**Use custom lists when you want to:**

* Create an allowlist for exclusive access
* Manually set reward amounts for specific users
* Block addresses you've identified as bad actors
* Make quick one-time distributions

Unlike automatic lists, you can edit custom lists anytime.

### How It Works

Here's what happens behind the scenes when your incentive runs:

1. Your query finds everyone who qualifies
2. Torque calculates their rewards based on your incentive type (top 10 for leaderboards, random selection for raffles, etc.)
3. A list is generated with exact wallet addresses and token amounts
4. You get a chance to review it
5. Once you approve, the list locks and rewards are distributed

**Important:** Once a list is locked and distribution starts, you can't change it. This keeps everything transparent and fair for participants.

### Adjusting Your Lists

Noticed something wrong? Here's how to handle it:

#### For Next Time: Update Your Query

The best way to fix ongoing issues is to update your query. For example, if you want to exclude wash traders:

sql

```sql
WHERE address NOT IN ('BadWallet1', 'BadWallet2', 'BadWallet3')
```

Your changes will apply to the next distribution cycle.

#### For Right Now: Download and Re-Upload

Need to fix the current distribution?

1. Download the list Torque created
2. Make your changes in the CSV (remove bad actors, adjust amounts, etc.)
3. Upload it back as a custom list
4. Use that custom list for this distribution

### Real World Example

You're running a weekly trading competition. Halfway through the week, you notice wallet `7xKXY...` is wash trading to boost their position.

**Quick fix for this week:**

* Download this week's list
* Remove the bad actor
* Upload the cleaned list
* Proceed with distribution

**Permanent fix:**

* Add that wallet to your query's exclusion list
* They won't appear in future weeks automatically
