# Integrations & Fees

DyorHQ is an interface to public protocols on Monad. This page lists every integration and every fee you can meet in the app. All values below are read live from the contracts by the app; if a policy changes for future launches or Moments, the app shows the new number.

## Integrations

| Area                 | Partner                                                  | Role                                                                                              |
| -------------------- | -------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Spot swaps           | **Kuru Flow**                                            | Aggregator across Kuru's order books and Monad pools                                              |
| Spot swaps           | **Uniswap v3 & v4**                                      | Canonical Uniswap deployments on Monad, including graduated Launchpad pools and Moment pools (v4) |
| Spot swaps           | **Monday Trade**                                         | Concentrated-liquidity spot pools with an embedded order book                                     |
| Perpetuals           | **Perpl**                                                | Fully on-chain perpetuals order book; AUSD collateral                                             |
| Launchpad graduation | **Uniswap v4** or **Monday Trade**                       | Where a coin's locked liquidity pool lives after the curve                                        |
| Moments graduation   | **Uniswap v4**                                           | coin/USDC pool, locked forever                                                                    |
| Moments NFTs         | **OpenSea**                                              | Every Moment edition renders and is tradable on OpenSea (Monad)                                   |
| Bridging             | **Aurora Intents**                                       | Cross-chain deposits to and from Monad                                                            |
| Charts               | **TradingView Lightweight Charts**                       | Perps candles, bundled offline                                                                    |
| News                 | CoinDesk, Cointelegraph, Decrypt, The Defiant, The Block | Public RSS feeds                                                                                  |
| Explorer             | **Monadscan**                                            | Every "View" link                                                                                 |

## Fees at a glance

### Spot swaps

| Fee               | Amount                                                                                                                                                                                                                                                                     |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| DyorHQ fee        | **None.** DyorHQ adds no fee or referral markup on swaps.                                                                                                                                                                                                                  |
| Venue pool fee    | The pool's own tier, shown in the route (e.g. "v3 · MON → USDC · 0.05%"). Uniswap tiers 0.01% / 0.05% / 0.3% / 1%; Monday tiers 0.01% / 0.03% / 0.05% / 0.3% / 1%. Kuru Flow returns a net output, so anything Kuru charges is already reflected in the quote you compare. |
| Moment coin pools | 1.5% all-in (see Moments below)                                                                                                                                                                                                                                            |
| MON ↔ WMON wrap   | None (1:1)                                                                                                                                                                                                                                                                 |
| Gas               | Paid in MON                                                                                                                                                                                                                                                                |

### Perps (Perpl Trade)

| Fee                | Amount                                                                                                                                                                    |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Trading fee        | Set by Perpl. The order ticket estimates **0.069%** of notional under **Fee**. Your actual fees are listed per fill in Trade History and totalled in the Perps Portfolio. |
| Funding            | Settled by Perpl roughly every hour. Positive rate means longs pay shorts. Shown as "Funding (1h)" with a countdown on the ticket.                                        |
| Deposit / withdraw | No DyorHQ fee. Gas only.                                                                                                                                                  |

### Launchpad

| Fee                                      | Amount                                                                                                                                                                                               | Who receives it                                                                                                                             |
| ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| Launch fee                               | **5 MON**, paid when you launch                                                                                                                                                                      | DyorHQ treasury                                                                                                                             |
| Curve trade fee                          | **1%** of every buy and sell on the curve                                                                                                                                                            | 50% DyorHQ, 50% creator (or holders if fee sharing is on). Paid out on every trade; creator fees land in the creator's wallet automatically |
| Creator tax                              | **0% to 10%**, set by the creator at launch in 0.25% steps, on curve trades                                                                                                                          | Creator (or holders if fee sharing is on)                                                                                                   |
| Early-buy (snipe) tax                    | On buys in the first seconds after launch: **98%** in second 0, **25%** in second 1, **3%** in second 2, **0.3%** in second 3, then 0. The creator's wallet (including its developer buy) is exempt. | Split like the curve fee                                                                                                                    |
| Pool fee after graduation (Uniswap v4)   | **1%** per swap, charged by the DyorHQ hook, plus the creator tax if any                                                                                                                             | 50% of the 1% to DyorHQ; the other 50% plus the creator tax to the creator or holders, distributed when the pool's fees are swept           |
| Pool fee after graduation (Monday Trade) | Monday's **1%** fee tier                                                                                                                                                                             | Earned by the locked position and harvested by DyorHQ. Not distributed to the creator or holders.                                           |
| Slippage on curve trades                 | Fixed **1%** minimum-received floor                                                                                                                                                                  | —                                                                                                                                           |

### Moments

| Fee                                      | Amount                                                                                                                                    | Who receives it                                                               |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Publishing                               | **Free.** Gas only.                                                                                                                       | —                                                                             |
| Collecting                               | The creator's collect price (minimum **$0.10**) per edition, paid in USDC                                                                 | **75%** to the Moment's reserve, **20%** to the creator, **5%** to DyorHQ     |
| Trading the coin after graduation        | About **1.5%** per trade: **0.5%** pool LP fee on the input (accrues to the locked position) + **1%** of the USDC leg via the DyorHQ hook | Hook fee, in USDC: **0.2%** creator, **0.3%** DyorHQ, **0.5%** buyback-and-LP |
| NFT royalty                              | **5%** (ERC-2981), when marketplaces honour it                                                                                            | Creator                                                                       |
| Expiry (window closes before graduation) | Reserve is split **70%** creator / **30%** DyorHQ treasury                                                                                | —                                                                             |

### Bridge

| Fee                                            | Amount                                            |
| ---------------------------------------------- | ------------------------------------------------- |
| Aurora protocol fee, withdrawal fee and spread | Included in Aurora's quote                        |
| DyorHQ integrator fee                          | **0.1%**                                          |
| Gas                                            | On the source chain, in that chain's native token |

The **Total fee** row on the bridge screen shows everything as one dollar amount and percentage before you confirm.

### Gas

Monad charges gas on the **gas limit**, not gas used. DyorHQ sets the limit at the estimate plus 20% and simulates every transaction before you sign. The one exception you may notice: the buy that completes a Launchpad curve needs extra gas for graduation, and the app says so if your wallet's estimate came in low.
