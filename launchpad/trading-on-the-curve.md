# Trading on the Curve

Tap any coin on the Launch tab to open its page. While the coin is **Bonding**, you buy and sell directly on its curve here (not in Swap).

{% hint style="info" %}
📸 **Screenshot here:** A coin page in Bonding state: header with graduation gauge, price chart and the "Trade on the Curve" ticket. Suggested file: `.gitbook/assets/33-curve-trade.png`
{% endhint %}

## The coin page

* **Header**: logo, name, phase, price in the pair asset (and USD), market cap, and a **Graduation** gauge with *"Graduates at X \<PAIR\> raised. Liquidity then moves to a locked \<VENUE\> pool."*
* **Stats**: 24h Volume, Holders (approximate), Progress.
* **Price chart**: built from the coin's curve trades over the last day. A flat line at the launch price until the first trade.
* **Trade on the Curve** ticket (see below).
* **Your Holdings** (if you hold any): Balance, Pending rewards, Claim Rewards.
* **Creator Fees**: fee mode, creator tax, fee recipient, and claim buttons for the creator.
* **Recent Trades**: the last 25 buys and sells with trader, amount and age. Tap one to open it on Monadscan.
* **About**: description, token and creator addresses, creator tax, fee-sharing flag, graduation venue and links.

## Buy

1. In the ticket, keep **Buy** selected.
2. Enter an amount of the pair asset (or tap the max button to use your balance).
3. The quote updates as you type:
   * **You receive**: coins
   * **Curve fee**: 1% of your input
   * **Early-buy tax**: shown only in the first seconds after launch, in the attention colour
   * **Refunded (curve full)**: shown if your buy is more than the curve still needs; the excess comes straight back
4. Tap **Buy $TICKER**. The confirmation shows **You pay**, **You receive** and **Minimum** (your quote minus 1% slippage). ERC-20 pairs add an "Approve \<PAIR\>" step first; MON needs none.

The buy that reaches the threshold **completes the curve and graduates the coin in the same transaction**. It needs more gas than a normal buy. If your wallet's estimate came in too low you'll see *"This buy would graduate the token and needs more gas. Try again."*; just retry.

## Sell

1. Switch the ticket to **Sell**.
2. Enter a number of coins.
3. The quote shows **You receive** in the pair asset, **Curve fee** (1% of the output) and **Creator tax** if the creator set one. There's no early-buy tax on sells.
4. Tap **Sell $TICKER**. Steps: "Approve $TICKER" then the sell.

## How the price moves

The curve is a constant-product curve with a virtual reserve, like most launchpads: each buy raises the price, each sell lowers it. About 68.4% of the supply is available on the curve; the rest is withheld. At graduation about two-thirds of it (21.6% of supply) seeds the pool at the curve's final price so there's no jump, and the remaining 10% of supply stays locked outside the pool.

## Fees on the curve

| Fee | Buy | Sell |
| --- | --- | --- |
| Curve fee 1% | Off the input | Off the output |
| Creator tax (0–10%) | Off the input | Off the output |
| Early-buy tax | Seconds 0–3 after launch: 98% / 25% / 3% / 0.3% | None |

The creator, the deployer and the developer buy never pay the early-buy tax. Half of the curve fee and early-buy tax goes to DyorHQ; the other half plus the creator tax goes to the creator, or into the holder-reward pool when fee sharing is on.

## Slippage

Curve trades use a fixed **1%** floor: the transaction reverts if you would receive less than 99% of the quote. Quotes are re-fetched 300 ms after you stop typing, so what you review is current.

## Watch-only and signed-out users

The ticket shows "Sign in to trade." and the buttons are disabled. You can still browse every coin, chart and trade list.
