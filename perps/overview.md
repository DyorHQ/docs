# Perps Overview

DyorHQ trades perpetual futures on **Perpl**, the fully on-chain perpetuals order book on Monad. Your wallet talks to Perpl's exchange contract directly: your collateral sits in your own Perpl account, and every order is signed by you.

**Where:** Trade tab → **Perps** (or side menu → Perps).

{% hint style="info" %}
📸 **Screenshot here:** Perps screen in Trade view showing the market header, order ticket and Long/Short buttons. Suggested file: `.gitbook/assets/20-perps.png`
{% endhint %}

## Markets

| Market | Asset |
| --- | --- |
| BTC-PERP | Bitcoin |
| MON-PERP | Monad |
| ETH-PERP | Ether |
| SOL-PERP | Solana |
| HYPE-PERP | Hyperliquid |
| ZEC-PERP | Zcash |

Tap the market name at the top to open **Select Perpetual**, with search, mark price and 24h change per market. BTC is selected when you first open the tab.

## Key facts

| | |
| --- | --- |
| Collateral | **AUSD** (6 decimals). Deposit at least **10 AUSD** to open your account. |
| Margin mode | **Isolated** only (Perpl offers isolated margin only). |
| Leverage | Set per order with the leverage button. Default comes from Profile → Trading Preferences (2× out of the box). Each market caps leverage at 1 ÷ its initial margin fraction (for example 10× where initial margin is 10%). |
| Order types | Market (immediate-or-cancel at mark ± your slippage), Limit (Last or Mid price fill), with optional Take Profit / Stop Loss, Post-Only and Reduce Only. |
| Fees | Perpl's trading fee; the ticket estimates 0.069% of notional. |
| Funding | Hourly. Positive rate: longs pay shorts. Shown with a countdown on the ticket. |
| Data | Exchange contract polled every 8 s; live order book and trades over Perpl's market-data feed; candles refreshed every 15 s. |

## The two views

A pill in the header switches between:

* **Chart**: TradingView candles (1m / 5m / 15m / 1h / 4h / 1D, default 1h) with your entry, liquidation and open-order levels drawn on, plus **Order Book** (with three price-grouping levels and the spread) and **Trades** tape.
* **Trade**: the order ticket.

Below both: **Positions**, **Orders**, **Assets** and **Trade History** tabs.

## The ⋯ menu

**Deposit AUSD**, **Withdraw AUSD**, **Portfolio** (your Perpl account value, volume, realized P&L, win rate, fills and closed positions), and a live-data status line ("Live market data" / "Connecting…").

## Set-up checklist

1. Hold some **AUSD** (and MON for gas). If you only have MON, the Transfer sheet on Home can swap it for you on the way in.
2. **Deposit** at least 10 AUSD. Your first deposit opens your Perpl account. See [Deposit & Withdraw Collateral](deposit-and-withdraw.md).
3. Optional but recommended: connect **Perpl Trading** in Profile → Perpl Trading (a trading key, which unlocks Trade History and the Perps Portfolio history) and enable **One-Click Trading** (which additionally lets you place Take Profit / Stop Loss). See [One-Click Trading](one-click-trading.md).
4. Place your first order. See [Placing Orders](placing-orders.md).

{% hint style="warning" %}
Perpetuals are leveraged products. You can lose your entire margin on a position. Read [Risk Disclosures](../resources/risk-disclosures.md).
{% endhint %}
