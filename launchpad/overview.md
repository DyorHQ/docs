# Launchpad Overview

The DyorHQ Launchpad is a fair-launch bonding curve on Monad. Anyone can launch a coin, anyone can trade it on the curve, and when the curve raises its target the liquidity moves into a pool that is **locked forever**. The twist: a coin can be paired with **MON, USDC, AUSD or aBIL**, a tokenized T-bill stock, which is what "launching a memecoin paired with a tokenized RWA" means in practice.

**Where:** the **Launch** tab.

{% hint style="info" %}
📸 **Screenshot here:** Launch tab showing the Graduated and Explore sections with coin cards. Suggested file: `.gitbook/assets/30-launchpad.png`
{% endhint %}

## How it works

1. **Launch.** A creator sets a name, ticker, image, description, links, the pair asset, the graduation venue, an optional developer buy, an optional creator tax and whether fees are shared with holders. The whole **1,000,000,000** supply mints straight to the bonding curve. There is no team allocation. Launching costs a **5 MON** fee.
2. **Curve trading.** Anyone buys and sells on the curve. Price rises as the curve fills. A **1%** trade fee, the creator tax (if any) and a steep, fast-decaying **early-buy tax** in the first four seconds are taken on every trade.
3. **Graduation.** The buy that pushes the raised amount to the pair asset's threshold completes the curve. In the same transaction the raised funds and the coins the final price implies are seeded into a **Uniswap v4** or **Monday Trade** pool at the curve's final price, and the position is locked in a contract with no withdrawal function. The rest of the withheld supply (10% of the total) stays in the locker, unpaired, forever.
4. **Pool trading.** From then on the coin trades in Swap like any other token. Fees keep flowing to DyorHQ and to the creator or holders.

## The numbers

| Parameter | Value |
| --- | --- |
| Supply per coin | 1,000,000,000 (fixed, no minting after launch) |
| Launch fee | 5 MON |
| Curve trade fee | 1% (buys: off the input; sells: off the output) |
| Creator tax | 0% to 10%, chosen at launch in 0.25% steps |
| Early-buy tax | 98% → 25% → 3% → 0.3% in seconds 0–3 after launch, then 0 |
| Fee split | 50% DyorHQ / 50% creator (or holders) |
| Withheld from the curve | About 31.6% of supply (about 68.4% is sold on the curve). At graduation about 21.6% goes into the pool; the remaining 10% (100M coins) is locked, unpaired, in the locker |
| Launch valuation → graduation valuation | 10× (a coin launches at about a $2,000 FDV and graduates at about $20,000) |
| Slippage on curve trades | 1% minimum-received floor |

### Graduation thresholds by pair asset

| Pair asset | Raised on the curve to graduate | Graduates on |
| --- | --- | --- |
| MON | 167,413.31 MON | Uniswap v4 (default) or Monday Trade (as TOKEN/WMON) |
| USDC | 4,324.56 USDC | Uniswap v4 (default) or Monday Trade |
| AUSD | 4,324.56 AUSD | Uniswap v4 (default) or Monday Trade |
| aBIL | 47.1999 aBIL | Monday Trade only |

The USDC and AUSD thresholds are exactly $2,000 × (√10 − 1). The MON and aBIL thresholds were fixed at deployment from the prices at the time, so their dollar value moves with those assets. The app always shows the live threshold for the pair you pick ("Graduates at X \<PAIR\> raised").

These are the thresholds of the current Launchpad, deployed on 2026-09-23 with MON at about $0.0258 and aBIL at about $91.62. Coins launched on the earlier, now retired Launchpads keep the thresholds they were launched with; see [Past Cohorts & Retired Launchpads](../resources/past-cohorts-and-retired-launchpads.md).

## Explore screen

* **Graduated**: coins that cleared the threshold, newest first, with a **Graduated** badge.
* **Explore**: coins still on the curve, sortable by **Newest**, **Market Cap** or **Near Graduation**. Cards at 80%+ show their percentage badge.
* Each card: image, name, $TICKER, market cap in the pair asset, age, and a "N% to graduation" progress bar.
* **Search coins** by name or symbol. The list polls every 20 seconds.
* Toolbar: **My Launchpad** (your holdings, launches, claims) and **New Launch**.

## Lifecycle states

| State | What it means |
| --- | --- |
| **Bonding** | Trading on the curve. |
| **Migrating** | A transient state inside the graduating transaction; you won't normally see it. Once the pool exists, trading moves to Swap. |
| **Graduated** | Pool is live and locked; trade via Swap. |
| **Stuck** | The graduation attempt failed. Anyone can retry on-chain, and a Monday-venue launch can fall back to Uniswap v4 (aBIL launches only after DyorHQ enables the fallback). The retry buttons are not yet reachable in the iOS app. |
| **Refund mode** | If graduation keeps failing for 7 days, the owner can put the launch into refund mode: buys close and sells are fee-free at the curve price. Refund-mode selling is a contract feature the iOS app does not expose yet. |

## What the owner can and cannot do

The contracts are immutable. DyorHQ can set the launch fee, fee policy and maximum creator tax for **future** launches, approve pair assets, turn a launch whitelist on or off, change where its own fee share is paid, trigger refund mode after 7 days of failed graduations, enable the Uniswap v4 fallback for aBIL launches, and (with a 3-day timelock, which the current recipient can veto) hand an abandoned launch's fee stream to a new recipient. DyorHQ cannot withdraw locked liquidity, touch a curve's reserves, change a live launch's fees, mint tokens or pause trading. The Launchpad went through an internal security audit in September 2026 and was redeployed with the fixes.

Next: [Launch a Coin](launch-a-coin.md), [Trading on the Curve](trading-on-the-curve.md), [Graduation](graduation.md), [Creator Fees & Holder Rewards](fees-and-rewards.md).
