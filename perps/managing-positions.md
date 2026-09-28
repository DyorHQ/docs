# 🎛️ Managing Positions

Below the chart or ticket, four tabs track everything for the selected market: **Positions**, **Orders**, **Assets** and **Trade History**.

## Positions

Each open position is a card:

* **Long / Short N×** with P\&L in USD and as a percentage of margin
* **Size**, **Entry**, **Mark**, **Margin**, **Liq.** (liquidation price) and **Notional**
* Three buttons: **Add Margin**, **TP/SL** and **Close**. **TP/SL** sets, moves or removes the position's take-profit and stop-loss, and needs [One-Click Trading](one-click-trading.md). The triggers close the position's size at the moment you set them. When a position has triggers, the card also shows a "TP … · SL …" line.

Liquidation price = entry ± (maintenance requirement − margin − premium) ÷ size. The app reads each market's initial and maintenance margin fractions from Perpl's exchange contract, and they differ by market. If they can't be read, the liquidation price shows "Unknown", leverage is limited to 1×, and a stop-loss can't be set until they load.

### Close a position

Tap **Close** to open **Close Position**:

* Rows: Position, Mark price, Unrealized
* **Close order** picker: **Market** or **Limit**
  * Market: _"Market, reduce-only, 1% slippage"_ → button **Close at Market**
  * Limit: enter a **Limit price**, optional **Post only (maker)**. The note reads _"Rests as a reduce-only limit at your price until it fills. It won't reduce your position until then."_ → button **Place Limit Close**

### Add margin

Tap **Add Margin**: enter an amount (25% / 50% / Max shortcuts). The **After** section previews the new Margin, Leverage and Liq. price. Funds come from your available Perpl balance.

## Orders

Resting orders appear as cards: **Buy / Sell**, **Limit** or **Limit · reduce-only**, Price, Size, Leverage, Distance from mark, and a **Cancel** button (confirmed in a **Cancel Order** sheet).

TP/SL triggers show as **Take Profit** / **Stop Loss** "on Long / Short" cards. A trigger that Perpl confirms is live has a **Cancel** button, and you confirm the cancel in a sheet. A new trigger reads **Pending…** for a few seconds until Perpl lists it. While Perpl trading is offline, a banner says TP/SL can't be verified, and rows read "Last seen on Perpl" or "Saved on this device · unverified". TP/SL left with no position to close get their own banner with a **Cancel** button.

## Assets

Total balance, In use (margin), Available and Unrealized for your Perpl account.

## Trade History

Your fills on the selected market with Price, Size, Value, Fee and P\&L: up to 50, taken from your latest 100 fills across all markets. Needs Perpl Trading connected (see [One-Click Trading](one-click-trading.md)); otherwise it reads _"Connect Perpl trading in Profile to see your history."_

## Perps Portfolio

Perps → **⋯** → **Portfolio**:

* **Account Value**, **Available**, **Unrealized**
* Tiles: **All-Time Volume**, **Realized P\&L**, **Win Rate**, **Trades**, **Fees**
* History switch: **Fills** / **Closed** (the most recent 100 rows are listed; totals cover up to 1,000, with "Showing your most recent activity." when truncated)

Also needs Perpl Trading connected for the history part.

## Notifications

While the Perps screen is open, the app posts an **Order filled** notification when a position's size grows between refreshes (a fill landed). Fills aren't noticed while the Perps screen is closed, so don't rely on this to protect a position: set a stop-loss. On-chain orders post a "Long/Short \<MARKET>" notification; One-Click orders post **Order placed** (limit) or **Order filled** (market). The master **Enable Notifications** switch controls all of these; **Swaps & Fills** additionally gates the swap and One-Click order notifications.

## Watch-only

Watching an address shows its positions and orders read-only. **Long** and **Short** are disabled with "Sign in to trade." The Add Margin, TP/SL, Close and Cancel sheets still open, but they can't be confirmed and say "You are watching this address. Sign in to trade."
