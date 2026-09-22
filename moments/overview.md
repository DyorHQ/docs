# Moments Overview

**Make your favorite moments last forever.** A Moment is a photo or video from real life, published on Monad as an NFT. People collect editions of it for USDC. If enough is collected, the Moment's own coin **graduates** into a live, permanently locked Uniswap v4 market, and everyone who collected gets coins.

Moments is a separate product from the Launchpad, with its own contracts, supply and economics. You publish a memory; you don't "launch a coin".

**Where:** the **Moments** tab.

{% hint style="info" %}
📸 **Screenshot here:** Moments feed with the All / Collecting / Graduated filter and a few Moment cards. Suggested file: `.gitbook/assets/40-moments-feed.png`
{% endhint %}

## How it works

1. **Publish.** Pick a photo or video, name it, give its coin a ticker, add the place and date, set a collect price (min $0.10), your coin allocation (up to 10%) and a collect window (1 to 30 days). Publishing is free; you pay gas only. The media is pinned to IPFS and its fingerprint goes on-chain.
2. **Collect.** Anyone pays the collect price in USDC per edition (up to 20 at a time). They get an NFT edition (numbered #1, #2, …) that appears on OpenSea as soon as it settles, plus a coin entitlement. Every collect splits **75%** to the Moment's reserve, **20%** to the creator, **5%** to DyorHQ.
3. **Graduate.** When the reserve reaches **771.43 USDC**, the collect that gets it there also graduates the coin: the reserve and the reserved coins seed a coin/USDC pool on Uniswap v4 at a **$2,000 FDV**, locked forever. Collecting closes; the edition size is fixed.
4. **Claim and trade.** Collectors' coins vest 60% at graduation, then 20% a month for two months. The creator's allocation vests 20% at graduation then 16% a month for five months. The coin trades in Swap at about 1.5% all-in (a 0.5% pool fee on the input plus 1% of the USDC leg) that pays the pool, the creator, DyorHQ and a buyback that deepens the pool.
5. **Or expire.** If the window closes before the threshold, anyone can wind the Moment down: no coin is ever minted, editions stay with their collectors, and the reserve is booked 70% to the creator and 30% to the DyorHQ treasury.

## The numbers

| Parameter | Value |
| --- | --- |
| Coin supply per Moment | 100,000,000 (fixed) |
| Settlement and pair asset | USDC only |
| Collect price | Creator-set, minimum $0.10, fixed per Moment |
| Collect split | 75% reserve / 20% creator / 5% DyorHQ |
| Graduation threshold | 771.428571 USDC in the reserve (≈ $1,028.57 collected) |
| Opening valuation | $2,000 FDV at the default 10% creator allocation ($1,800 if the creator takes 0%) |
| Coin allocation at graduation | Collectors ≈ 51.4% / pool ≈ 38.6% / creator up to 10% |
| Creator allocation | 0–10% of supply, chosen at publish; anything not taken deepens the pool |
| Collector vesting | 60% at graduation, +20% at month 1, +20% at month 2 |
| Creator vesting | 20% at graduation, +16% per month for 5 months |
| Editions per collect | 1–20 |
| Collect window | 1–30 days (in the app), ends early at graduation |
| Trading fee after graduation | About 1.5%: 0.5% pool fee + 1% of the USDC leg (0.2% creator / 0.3% DyorHQ / 0.5% buyback), the hook part always in USDC |
| NFT royalty | 5% (ERC-2981) |
| Expiry split | 70% creator / 30% DyorHQ treasury |
| Nothing editable after publish | Media, name, ticker, price, allocation, window, beneficiaries |

## The feed

* Filter: **All**, **Collecting** (still inside the window), **Graduated**.
* Each card: the media, a state badge (countdown like "2d 3h", "Window closed", "Graduation pending", "Graduated" or "Expired"), name and $TICKER, **Per edition** price (or **FDV** once graduated), **Editions** count and a "N% to graduation" bar.
* Toolbar: **My Moments** and **Publish**. Polls every 20 seconds.
* If governance has paused publishing, the header says *"Publishing is paused by governance; collecting continues."* and Publish is disabled.

## States

| State | Meaning |
| --- | --- |
| **Collecting** | Inside the window, below the threshold. Editions mint on every collect. |
| **Graduation pending** | Threshold reached but the pool creation failed. Anyone can retry. |
| **Graduated** | Pool live, collection closed, coins vesting and tradable. |
| **Window closed** | Deadline passed below the threshold; anyone can call **Expire Moment**. |
| **Expired** | Wound down. Editions remain; no coin exists. |

{% hint style="warning" %}
**Read this before you collect.** A Moment coin is a bet on outside demand layered on a keepsake. 25% of every collect leaves to the creator and DyorHQ before any trading starts, so without new buyers the collectors as a group get back less than they paid. Most Moments will never graduate, and that's by design: they stay cheap keepsakes and no coin is created. See [Risk Disclosures](../resources/risk-disclosures.md).
{% endhint %}

Next: [Publish a Moment](publish-a-moment.md), [Collect a Moment](collect-a-moment.md), [Graduation & Vesting](graduation-and-vesting.md), [Earnings, Fees & Buybacks](earnings-and-fees.md), [My Moments](my-moments.md).
