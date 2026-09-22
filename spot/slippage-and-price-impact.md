# Slippage & Price Impact

Two different things protect you on a swap. **Slippage tolerance** is your limit; **price impact** is a measurement.

## Slippage tolerance

Slippage is how far the price may move between your quote and settlement. If a swap would fill worse than your tolerance allows, it **cancels instead of filling worse**. The **Minimum received** row on every confirmation is your quote minus the tolerance.

**Default: 0.5%.** Tap the slippage button (top right of the Swap screen) to change it.

{% hint style="info" %}
📸 **Screenshot here:** Slippage sheet with the four presets and the Custom field. Suggested file: `.gitbook/assets/11-slippage.png`
{% endhint %}

| Preset | The app's hint |
| --- | --- |
| 0.1% | Tightest price. Best for stable pairs. |
| 0.5% | Balanced, recommended for most swaps. |
| 1% | More forgiving when the market is moving. |
| 3% | For volatile or low-liquidity pairs. |
| Custom | Any value above 0 up to 50%. |

Warnings: at 5% or more the sheet says a high tolerance can fill at a much worse price; at 0.1% or less it warns a swap can fail in a fast-moving market.

Once a quote is selected, the line under the quote list reads: *"Minimum received X SYM at Y% slippage. Quotes refresh every 15 seconds."*

{% hint style="info" %}
The Swap slippage setting is separate from **Profile → Trading Preferences → Max Slippage**, which is the default for perps market orders (0.1% / 0.5% / 1% / 2%). Both start at 0.5%.
{% endhint %}

## Price impact

Price impact is how much your own trade moves the venue's price. DyorHQ measures it against the venue's marginal price by quoting a tiny slice of your amount and comparing. Each Uniswap and Monday quote shows **Impact X%**; Kuru Flow does not report impact.

When impact is above **1%**, the figure is highlighted in the attention colour. The app never blocks a high-impact swap; it's your call. Large trades in thin pools are where a different venue, a smaller size, or a two-step route pays off.

## Approvals and Permit2

* ERC-20 inputs need an approval before the first swap on a venue. The confirmation lists each approval as its own step; approvals that already cover the amount are skipped.
* Uniswap v4 uses **Permit2**: one unlimited approval of the token to Permit2, then a Permit2 allowance to the Universal Router that lasts 30 days. The app reuses it while it has more than two minutes left.
* Kuru Flow, Uniswap v3 and Monday Trade get exact-amount approvals.

## Why a quote can change

Quotes are re-fetched every 15 seconds while an amount is entered. If the market moves between your review and your tap, the slippage floor is what protects you. The route and venue you chose stay fixed once you tap Swap.
