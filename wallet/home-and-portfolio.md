# Home & Portfolio

## Home

The Home tab is your overview. It refreshes every 30 seconds and on pull-to-refresh.

{% hint style="info" %}
📸 **Screenshot here:** Home tab, full length (hero, quick actions, Allocation, Top Tokens, My Holdings). Suggested file: `.gitbook/assets/50-home-full.png`
{% endhint %}

### Hero card

* **Total value** in USD = Spot + Perps + Launch + Moments.
* **24h change** in USD and %, weighted across your priced holdings.
* **Total Volume** with a period picker (24h / 7 days / 30 days / All). Tap it to open Portfolio.
* **Avail. Balance** (spot) and **In Use** (Perpl equity).
* The **Spot / Perps / Launch / Moments** split.

### Quick actions

| Button | Opens |
| --- | --- |
| **Bridge** | Cross-chain bridge (coming soon; see [Bridge](bridge.md)) |
| **Deposit** | Your Receive sheet (QR + address) |
| **Withdraw** | The Send sheet |
| **Transfer** | Spot ↔ Perps collateral transfer |

### Allocation

A donut of Spot / Perps / Launchpad / Moments with percentages. Shown once you hold anything.

### Top Tokens

Six tokens per tab: **Popular** (the curated list), **Hot** (largest absolute 24h move), **Gainers**, **Losers**. Tap one for its detail page: price, 24h chart, your balance and value, contract, decimals, **Swap SYM** and **View on Monadscan**.

### My Holdings

Tabs **Spot / Perps / Launch / Moments**. Spot rows show amount, value, price and 24h change; Perps rows show side, leverage, size and unrealized P&L; Launch rows show progress or phase; Moments rows show editions, coins and state. Tokens you hold that aren't on the curated list are discovered on-chain and added automatically.

## Portfolio

**Where:** side menu → Portfolio, or tap Total Volume on Home.

{% hint style="info" %}
📸 **Screenshot here:** Portfolio screen with Cumulative Volume, the four metrics, Volume by Section and a section card. Suggested file: `.gitbook/assets/51-portfolio.png`
{% endhint %}

Everything here is computed from your wallet's own on-chain history (plus Perpl's fills once Perpl Trading is connected). Signed-out users see *"Sign In to See Your Portfolio"*.

* **Cumulative Volume** for the selected period, "Across Spot, Perps, Launch and Moments".
* **Fees paid**, **P&L** (marked \* when a source is incomplete), **Claimed fees**, **Trades**.
* **Volume by Section**: a bar and legend for Spot, Perps, Launch, Moments, Bridge.
* One **card per section** with Volume, Fees, P&L, Claimed (or Trades for Perps) and the trade count. Tap a card to jump to that tab. The Perps card notes *"Enable one-click trading in Profile → Perpl Trading to include your perps history."* until you do.
* **My Holdings**: **Assets** (top 6, "Show all") and **NFTs** (your Moment editions and other NFTs).
* **Activity**: every swap, perp fill, curve trade, claim, collect, publish, Moment proceeds or pool-fee withdrawal and bridge in the period, with Monadscan links. Plain wallet sends and Perpl deposits/withdrawals live in Recent Activity instead.

Stablecoins (USDC, AUSD, USDT0) are counted at $1; other tokens at today's price. Results are cached for five minutes; pull to refresh forces a recompute.

## Recent Activity

Profile → **Recent Activity** is the simpler, chronological list: launches, swaps, buys, sells, perp orders, sends, collects and claims from this device plus the last week of on-chain activity, each linking to Monadscan. Empty state: *"Your launches, swaps, buys, sells and perp orders show up here."*
