# Graduation

Graduation is the moment a coin leaves its bonding curve and becomes a normal token with a permanently locked liquidity pool.

## When it happens

The curve tracks how much of the pair asset it has raised (net of fees). When a buy pushes that amount to the pair's threshold, the curve is complete and graduation runs **in the same transaction**. The final buy is clamped to exactly what the curve needs; any excess is refunded to the buyer.

| Pair asset | Threshold |
| --- | --- |
| MON | 167,413.31 MON |
| USDC | 4,324.56 USDC |
| AUSD | 4,324.56 AUSD |
| aBIL | 47.1999 aBIL |

These are the current Launchpad's thresholds (deployed 2026-09-23). The MON and aBIL figures were fixed from those assets' prices at deployment. A coin launched on one of the earlier, retired Launchpads keeps the threshold it was launched with; its page shows its own *"Graduates at X \<PAIR\> raised"* figure. See [Past Cohorts & Retired Launchpads](../resources/past-cohorts-and-retired-launchpads.md).

## What happens at graduation

1. The raised pair asset and the coins the curve never sold are swept out of the curve. Only the coins the final price implies (about 21.6% of supply) go into the pool; the rest (10% of supply) is held in the locker outside the pool.
2. A pool is created at the **curve's final price** so there's no jump between the last curve trade and the first pool trade:
   * **Uniswap v4**: a full-range position in the canonical Uniswap v4 PoolManager on Monad, with the DyorHQ hook attached (that's what charges the 1% pool fee and creator tax). Locked in the DyorHQ **LaunchLocker**.
   * **Monday Trade**: a full-range position in a Monday spot pool at the 1% fee tier. Native-MON coins pair with WMON on Monday. Locked in the DyorHQ **Monday fee vault**.
3. The position is locked. **Neither locker has a function that removes liquidity**, not for the creator, not for DyorHQ. Only earned fees can ever leave.
4. The coin's page switches to **Graduated** and shows a **Swap TICKER on \<VENUE\>** button that opens the Swap screen with the pair preselected. The **Pool fee** row there reads the pool's own LP fee, which is 0% on Uniswap v4 because the 1% is charged by the hook instead.

{% hint style="info" %}
📸 **Screenshot here:** A graduated coin page with the "Graduated" section and the "Swap TICKER on Uniswap v4" button. Suggested file: `.gitbook/assets/34-graduated.png`
{% endhint %}

## Choosing the venue

The creator picks **Uniswap v4** or **Monday Trade** at launch. aBIL-paired coins can only graduate on Monday Trade (that's where aBIL has liquidity).

If someone pre-created a Monday pool at the wrong price to interfere with a graduation, the executor realigns it with a small bounded swap; if that can't be done safely the graduation reverts and the fallback below applies. On Uniswap v4 nobody but the DyorHQ executor can initialise a registered pool, so this can't happen there.

## If graduation gets stuck

Graduation can fail (for instance if the venue rejects the pool creation). On-chain, anyone can retry (`graduate`) paying only gas, and a Monday-venue launch can fall back into a locked Uniswap v4 pool (`graduateFallback`); aBIL launches need DyorHQ to enable that fallback first. The app has **Retry Graduation** and **Graduate on Uniswap v4 Instead** sheets built for this, but they aren't reachable for a stuck launch in the current build, so a stuck launch is handled on-chain or with support's help.

If graduation keeps failing for **7 days**, the owner can put the launch into **Refund mode**: buys close and sells are fee-free at the curve price, so holders can exit. Refund-mode selling isn't exposed in the iOS app yet.

## Trading after graduation

Graduated coins trade through **Swap**. Uniswap v4 quotes include graduated Launchpad pools automatically (the route text is tagged "launchpad"); Monday-graduated coins are quoted by the Monday Trade venue. The pool fee is 1% via the DyorHQ hook on Uniswap v4, or Monday's 1% tier on Monday Trade. See [Creator Fees & Holder Rewards](fees-and-rewards.md) for where those fees go.

The Launchpad page still tracks a graduated coin's price (read from the Uniswap v4 pool; Monday-graduated coins show the curve's final price) and market cap, and lists it under **Graduated**.
