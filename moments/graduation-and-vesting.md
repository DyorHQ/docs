# Graduation & Vesting

## When a Moment graduates

A Moment graduates when its **reserve** (75% of everything collected) reaches **771.428571 USDC**, which is about **$1,028.57** of collects. The collect that gets it there is clamped so the reserve lands exactly on the threshold, and graduation runs inside that same transaction:

1. The reserve USDC and the reserved coins seed a full-range **coin/USDC** pool on **Uniswap v4** at the price collectors paid, so there's no jump at open. The position goes to the **Moment locker**, which has no withdrawal function.
2. Coins become claimable on the vesting schedule.
3. The NFT collection closes: the number of editions is now fixed forever.
4. Trading fees start flowing (see [Earnings, Fees & Buybacks](earnings-and-fees.md)).

At the default 10% creator allocation the pool opens at a **$2,000 fully diluted valuation** (about 38.57M coins against 771.43 USDC). If the creator took a smaller allocation the untaken coins go into the pool at the same price, so the FDV is lower ($1,800 at 0%).

### How the coins are split

Coin entitlements accrue at one fixed rate per USDC collected, chosen at publish so that collectors' price equals the pool's opening price. That makes the split at graduation always the same:

| | Share of 100M |
| --- | --- |
| Collectors (in proportion to what they paid) | ≈ 51.43M (51.4%) |
| Pool (locked) | ≈ 38.57M (38.6%) |
| Creator (at 10%) | 10M (10%) |

## Vesting

Nothing is minted before graduation. After it, coins are minted **only when you claim**.

| | At graduation | Month 1 | Month 2 | Months 3–5 |
| --- | --- | --- | --- | --- |
| **Collectors** | 60% | +20% (80%) | +20% (100%) | — |
| **Creator** | 20% | +16% | +16% | +16% each month, 100% at month 5 |

A "month" is 30 days from graduation. Cliffs are monthly on purpose: they give collectors a reason to come back.

### Claiming

* On the Moment page, **Your Position** shows **Claimable now**, **Claimed**, **Vested %** and a **Claim X $TICKER** button.
* In **My Moments**, **Claim All** sweeps every vested tranche across all your graduated Moments in one transaction.

Claimed coins land in your wallet and show under **Home → My Holdings → Moments** and in the Swap picker.

{% hint style="info" %}
📸 **Screenshot here:** "Your Position" on a graduated Moment showing Claimable now, Claimed, Vested % and the Claim button. Suggested file: `.gitbook/assets/44-claim.png`
{% endhint %}

## If graduation fails

If the pool creation reverts, the Moment shows **Graduation Pending** with the first failure date and a **Retry Graduation** button. Anyone can retry; you pay only gas. There is no admin lever on this path by design.

## If the window closes first

If the deadline passes with the reserve below the threshold, the page shows **Window Closed** and anyone can tap **Expire Moment**:

* The NFT collection closes at its current size; editions stay with their owners.
* **No coin is ever minted.** Entitlements never vest. There's no dead coin and no dead pool.
* The reserve is booked **70% to the creator and 30% to the DyorHQ treasury**, both pull-only. The creator's 20% and DyorHQ's 5% collect-time shares are unaffected.

If the threshold was reached but graduation kept failing, the same wind-down becomes available once the window has closed **and** 7 days have passed since the first failed attempt, so retries always come first.

Expired Moments show **Expired** with the end date: *"The window closed before the threshold; the reserve was wound down. Editions stay with their collectors."*

## Trading a graduated coin

Tap **Trade $TICKER** on the Moment page (in the **Pool** section) to open Swap with USDC → coin. Uniswap v4 routes label it "moments 1.5%". The **Pool** section also shows coin price, opening price, graduation date, what seeded the pool, fees accrued, the buyback budget and the last buyback.
