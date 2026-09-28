# 💵 Earnings, Fees & Buybacks

## Creator earnings

| Source            | Rate                                                                            | When                                                                   |
| ----------------- | ------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Collect proceeds  | **20%** of every collect, in USDC                                               | Immediately, on every collect                                          |
| Coin allocation   | Up to **10%** of the 100M coins                                                 | Only if the Moment graduates; vests 20% at graduation then 16% a month |
| Trading fee share | **0.2%** of the USDC side of every trade (20% of the 1% hook fee), paid in USDC | After graduation                                                       |
| NFT royalty       | **5%** on marketplace sales that honour ERC-2981                                | Whenever an edition sells                                              |
| Expiry share      | **70%** of the reserve                                                          | If the window closes before graduation                                 |

### Withdrawing

On your own Moment's page, **You Created This** shows:

* **Proceeds to withdraw** + **Withdraw Proceeds**&#x20;
* After graduation: **Pool fees to withdraw** + **Withdraw Pool Fees**, and **Allocation claimable / vested**

Withdrawals are pull-only to the creator wallet fixed at publish. Nobody, including DyorHQ, can change the beneficiary of a live Moment.

## Fees on collects

Every collect is split at the contract:

|                                                 | Share |
| ----------------------------------------------- | ----- |
| Reserve (becomes the pool's USDC at graduation) | 75%   |
| Creator                                         | 20%   |
| DyorHQ                                          | 5%    |

Gas is paid in MON on top.

## Fees on trades (after graduation)

Every trade of a Moment coin costs about **1.5%** in total: a 0.5% LP fee on whatever you put in, plus 1% of the USDC leg, charged and held in USDC:

| Component                | Rate | Goes to                                                                 |
| ------------------------ | ---- | ----------------------------------------------------------------------- |
| Pool LP fee              | 0.5% | The locked position itself (folded back into liquidity, so depth grows) |
| Hook fee: creator        | 0.2% | Creator                                                                 |
| Hook fee: DyorHQ         | 0.3% | DyorHQ                                                                  |
| Hook fee: buyback-and-LP | 0.5% | The buyback budget (below)                                              |

## Buyback-and-LP

The 0.5% buyback share accumulates in USDC. Once the budget is at least 1 USDC and at least an hour has passed since the last run, anyone can tap **Run Buyback** in the Moment's **Pool** section. The sheet shows the **Budget**, **Spends: half on coins, half paired as liquidity**, and an **Impact cap: 1%**. It buys the coin with half the budget and adds coin + USDC to the locked position, so the pool gets **deeper with volume** instead of only decaying. Runs are bounded and MEV-aware; nothing can ever be withdrawn from the position.
