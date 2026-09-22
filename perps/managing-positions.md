# Managing Positions

Below the chart or ticket, four tabs track everything for the selected market: **Positions**, **Orders**, **Assets** and **Trade History**.

{% hint style="info" %}
📸 **Screenshot here:** Positions tab with an open position card showing "Add Margin" and "Close". Suggested file: `.gitbook/assets/24-positions.png`
{% endhint %}

## Positions

Each open position is a card:

* **Long / Short N×** with P&L in USD and as a percentage of margin
* **Size**, **Entry**, **Mark**, **Margin**, **Liq.** (liquidation price) and **Notional**
* Two buttons: **Add Margin** and **Close**

Liquidation price = entry ± (maintenance requirement − margin − premium) ÷ size. Perpl's default fractions where the contract doesn't specify otherwise are 10% initial and 5% maintenance.

### Close a position

Tap **Close** to open **Close Position**:

* Rows: Position, Mark price, Unrealized
* **Close order** picker: **Market** or **Limit**
  * Market: *"Market, reduce-only, 1% slippage"* → button **Close at Market**
  * Limit: enter a **Limit price**, optional **Post only (maker)**. The note reads *"Rests as a reduce-only limit at your price until it fills. It won't reduce your position until then."* → button **Place Limit Close**

### Add margin

Tap **Add Margin**: enter an amount (25% / 50% / Max shortcuts). The **After** section previews the new Margin, Leverage and Liq. price. Funds come from your available Perpl balance.

## Orders

Resting orders appear as cards: **Buy / Sell**, **Limit** or **Limit · reduce-only**, Price, Size, Leverage, Distance from mark, and a **Cancel** button (confirmed in a **Cancel Order** sheet).

TP/SL triggers show as **Take Profit** / **Stop Loss** "on Long / Short" cards. Live triggers stream from your Perpl trading connection and are marked **Keeper trigger**; the app also keeps a local copy marked **Pending…** for a few seconds after placement and while the connection is down, cleaned up once the position or order they belong to is gone.

## Assets

Total balance, In use (margin), Available and Unrealized for your Perpl account.

## Trade History

Your last 50 fills on the selected market with Price, Size, Value, Fee and P&L. Needs Perpl Trading connected (see [One-Click Trading](one-click-trading.md)); otherwise it reads *"Connect Perpl trading in Profile to see your history."*

## Perps Portfolio

Perps → **⋯** → **Portfolio**:

* **Account Value**, **Available**, **Unrealized**
* Tiles: **All-Time Volume**, **Realized P&L**, **Win Rate**, **Trades**, **Fees**
* History switch: **Fills** / **Closed** (the most recent 100 rows are listed; totals cover up to 1,000, with "Showing your most recent activity." when truncated)

Also needs Perpl Trading connected for the history part.

## Notifications

When a position's size grows between refreshes (a fill landed), the app posts an **Order filled** notification. On-chain orders post a "Long/Short \<MARKET\>" notification; One-Click orders post **Order placed** (limit) or **Order filled** (market). The master **Enable Notifications** switch controls all of these; **Swaps & Fills** additionally gates the swap and One-Click order notifications.

## Watch-only

Watching an address shows its positions and orders read-only. Long/Short and every action button are disabled with "Sign in to trade."
