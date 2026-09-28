# ⏳ Graduation & Vesting

## When a Moment graduates

A Moment graduates when its **reserve** (75% of everything collected) reaches **771.428571 USDC**, which is about **$1,028.57** of collects. The collect that gets it there is clamped so the reserve lands exactly on the threshold, and graduation runs inside that same transaction:

1. The reserve USDC and the reserved coins seed a full-range **coin/USDC** pool on **Uniswap v4** at the price collectors paid, so there's no jump at open. The position goes to the **Moment locker**, which has no withdrawal function.
2. Coins become claimable on the vesting schedule.
3. The NFT collection closes: the number of editions is now fixed forever.
4. Trading fees start flowing (see [Earnings, Fees & Buybacks](earnings-and-fees.md)).

At the default 10% creator allocation the pool opens at a **$2,000 fully diluted valuation** (about 38.57M coins against 771.43 USDC). If the creator took a smaller allocation the untaken coins go into the pool at the same price, so the FDV is lower ($1,800 at 0%).

### How the coins are split

Coin entitlements accrue at one fixed rate per USDC collected, chosen at publish so that collectors' price equals the pool's opening price. That makes the split at graduation always the same:

|                                              | Share of 100M    |
| -------------------------------------------- | ---------------- |
| Collectors (in proportion to what they paid) | ≈ 51.43M (51.4%) |
| Pool (locked)                                | ≈ 38.57M (38.6%) |
| Creator (at 10%)                             | 10M (10%)        |

## Vesting

Nothing is minted before graduation. After it, coins are minted **only when you claim**.

|                | At graduation | Month 1    | Month 2     | Months 3–5                       |
| -------------- | ------------- | ---------- | ----------- | -------------------------------- |
| **Collectors** | 60%           | +20% (80%) | +20% (100%) | —                                |
| **Creator**    | 20%           | +16%       | +16%        | +16% each month, 100% at month 5 |

A "month" is 30 days from graduation. Cliffs are monthly on purpose: they give collectors a reason to come back.

### Claiming

* On the Moment page, **Your Position** shows **Claimable now**, **Claimed**, **Vested %** and a **Claim X $TICKER** button.
* In **My Moments**, **Claim All** sweeps every vested tranche of your graduated Moments on the current Moments contracts in one transaction. Moments on earlier contract releases are listed under **Past Cohorts** and claimed one at a time from their own pages.

Claimed coins land in your wallet. For Moments on the current contracts, they also show under **Home → My Holdings → Moments** and can be traded in Swap. Coins of Moments on earlier contract releases can't be traded in the app; their token page shows "Past cohort · trading closed".

## If the window closes first

If the deadline passes with the reserve below the threshold, the page shows **Window Closed** and anyone can tap **Expire Moment**:

* The NFT collection closes at its current size; editions stay with their owners.
* **No coin is ever minted.** Entitlements never vest. There's no dead coin and no dead pool.



Expired Moments show **Expired** with the end date: _"The window closed before the threshold; the reserve was wound down. Editions stay with their collectors."_

## Trading a graduated coin

Tap **Trade $TICKER** on the Moment page (in the **Pool** section) to open Swap with USDC → coin. Uniswap v4 routes label it "moments 1.5%". The **Pool** section also shows coin price, opening price, graduation date, what seeded the pool, fees accrued, the buyback budget and the last buyback.
