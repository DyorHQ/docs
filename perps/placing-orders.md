# Placing Orders

**Where:** Trade tab → Perps → **Trade** view.

{% hint style="info" %}
📸 **Screenshot here:** The order ticket with Limit selected, TP/SL fields open and the summary rows (Liq. Price, Max, Fee). Suggested file: `.gitbook/assets/23-order-ticket.png`
{% endhint %}

## The order ticket, top to bottom

1. **Isolated** chip: the margin mode. Perpl only offers isolated margin, so it's fixed.
2. **Leverage button** ("2x" by default): opens **Adjust Leverage** with a draggable ruler from 1× to the market's maximum, quick picks **2x / 5x / 10x / Max**, and **Confirm**. Your default comes from Profile → Trading Preferences → **Default Leverage** (stepper 1–50; the market cap still wins).
3. **Available X AUSD** with a **+** to deposit.
4. **Order type**: **Market** ("Execute immediately at current price") or **Limit** ("Set a specific price for your order").
5. **Price** (limit only) with a stepper, and a **Last / Mid** pill that fills the field with the last traded price or the mid of the book.
6. **Amount** with a stepper and a unit toggle: size in the asset (e.g. BTC) or in **AUSD** (converted at the current price).
7. **Percent-of-margin slider** with stops at 0 / 25 / 50 / 75 / 100%. Size = available × percent × leverage ÷ price, rounded down to the lot size.
8. **Flags**:
   * Market: **Max Slippage** (reveals a % field, default from Settings, 0.5% out of the box) and **TP/SL**.
   * Limit: **TP/SL**, **Post-Only**, **Reduce Only**.
9. **Take profit** / **Stop loss** fields (USD) with expected profit / loss rows.
10. Summary: **Liq. Price** (long and short), **Max** (available × leverage), **Fee** (≈ 0.069% of notional).
11. **Long** / **Short** buttons.

## Market orders

A market order is sent as an immediate-or-cancel limit at the mark price ± your slippage, exactly as Perpl's own interface does it. Whatever can't fill inside that band is cancelled, never filled worse.

## Limit orders

Rests on Perpl's book at your price. **Post-Only** guarantees you're the maker (the order is rejected instead of crossing the book). **Reduce Only** guarantees the order only reduces an existing position. Both are limit-only and clear when you switch to Market.

## Take Profit / Stop Loss

TP/SL orders are **keeper-managed triggers linked to your position** and need [One-Click Trading](one-click-trading.md). The status line under the fields tells you where you stand:

* *Placed on Perpl as keeper-managed trigger orders linked to this position.*
* *Connecting to Perpl trading to place your take-profit and stop-loss.*
* *Connect Perpl trading in Profile to place take-profit and stop-loss.* / *Enable one-click trading in Profile to place take-profit and stop-loss.*
* *Couldn't reach Perpl trading, retrying. Take-profit and stop-loss need it live.*

Rules: for a long, take-profit must be above entry and stop-loss below; for a short the reverse. The app checks this and tells you which side is wrong. Take profit triggers on the **Last** price; stop loss triggers on the **Mark** price.

If you place TP/SL without One-Click Trading, the position opens but the confirmation shows **"TP/SL: Needs one-click trading, not placed"**.

## Confirming

Tap **Long** or **Short**.

* **With One-Click Trading:** the **Place Order** sheet ("Review Order · Perpl") lists Market, Side, Type, Size, Leverage, Margin, Take profit, Stop loss, then *"Signed and forwarded by your Perpl API key over the trading connection."* You'll see "Order sent to Perpl." on success. If the position opened but a trigger was rejected, the sheet says so and you can set it again from the ticket.
* **Without:** the **Review Order** sheet with Market, Side, Type, Size, Leverage and Margin rows (plus the TP/SL warning if you typed triggers), confirmed with **Long \<ASSET\>** / **Short \<ASSET\>** and signed as an on-chain transaction from your wallet.

With **Require Face ID** on, on-chain orders prompt for Face ID before signing. Orders forwarded through One-Click Trading are signed by your trading key and don't prompt.

## Validation messages

| Message | Fix |
| --- | --- |
| Deposit AUSD to open a trading account first. | Make your first deposit (10 AUSD minimum). |
| Enter an amount in AUSD. / Enter a size in \<ASSET\>. | Fill the amount. |
| Enter a limit price. | Fill the price on a limit order. |
| Not enough available margin. | Reduce size or leverage, or deposit more. |
| Take-profit must be above your entry (X) for a long. (and the other three variants) | Move the trigger to the correct side. |

## Funding

The ticket shows **Funding (1h)** and a countdown to the next settlement. Positive funding: longs pay shorts; negative: shorts pay longs. It's paid or received on your open position each hour.
