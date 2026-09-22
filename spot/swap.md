# Swap

Swap any Monad token from your own wallet. DyorHQ quotes **Kuru Flow**, **Uniswap** (v3 and v4) and **Monday Trade** at the same time, ranks them by what you receive, and executes the one you pick through that venue's own router. No DyorHQ contract sits in the path and DyorHQ charges no fee.

**Where:** Trade tab → **Swap** (the default mode). Also reachable from the side menu ("Spot"), from a token's detail page (**Swap SYM**), and from graduated Launchpad and Moment coins (**Swap SYM on …** / **Trade $SYM**).

{% hint style="info" %}
📸 **Screenshot here:** Swap screen with an amount entered and the three-venue Quotes list. Suggested file: `.gitbook/assets/10-swap.png`
{% endhint %}

## The screen

* **You Pay**: token picker, amount field, your balance and its USD value, and 25% / 50% / 75% / 100% buttons. Tapping 100% on MON keeps about 0.02 MON back for gas.
* **⇅** flips the pair.
* **You Receive**: token picker and the quoted amount ("Finding the best price" while quoting).
* **Quotes**: one row per venue with the output amount, the route and price impact; venues that couldn't quote get their own row with the reason. The best output is tagged **Best** and preselected; tap another row to choose it instead.
* **Slippage** (the slider icon, top right) opens the slippage sheet; the current tolerance shows in the "Minimum received … at X% slippage" line under the quotes.
* **Swap History** (signed-in wallets): your swaps over 24H / 7D / 30D / All, with Monadscan links.
* The primary button reads **Enter an Amount**, **Insufficient SYM**, **Wrap MON**, **Unwrap WMON** or **Review Swap** depending on state.

## How to swap

1. Choose the token you pay and enter an amount.
2. Choose the token you receive.
3. Quotes arrive within a second or two. Each venue has up to 20 seconds; a slow venue never hides the others. Quotes refresh every 15 seconds while an amount is entered.
4. Keep the **Best** quote or tap another venue.
5. Tap **Review Swap**. The sheet lists **You pay**, **You receive**, **Minimum received**, **Venue**, **Route** and **Slippage**.
6. Tap **Swap**. If **Require Face ID** is on, confirm with Face ID.
7. Each step is simulated, sent and confirmed in order. Approvals you already granted are skipped. Tap **View** on any step to see it on Monadscan.

You get a "Swap complete" notification, and the swap appears in Swap History, Recent Activity and Portfolio.

## The venues

| Venue | Route text you'll see | Approval steps |
| --- | --- | --- |
| **Kuru Flow** | "Aggregated across Kuru order books and Monad pools" | Approve SYM for Kuru Flow (exact amount) → Swap on Kuru Flow |
| **Uniswap v3** | "v3 · MON → USDC · 0.05%" | Approve SYM for Uniswap (exact amount) → Swap on Uniswap v3 |
| **Uniswap v4** | "v4 · MON → USDC · 0.05%", "+ launchpad", "moments 1.5%" | Approve SYM for Permit2 → Allow the Universal Router to spend SYM (Permit2, 30 days) → Swap on Uniswap v4 |
| **Monday Trade** | "MON → USDC · 0.05%" or "USDC → WETH → MON · 0.05% + 0.3%" | Approve SYM for Monday Trade → Swap on Monday Trade |
| **Wrap** | "Wrap MON → WMON, 1:1" / "Unwrap WMON → MON, 1:1" | None |

Native MON never needs an approval. Uniswap and Monday routes are searched directly at the deepest fee tiers and through one hop via WMON, USDC, USDT0 or WETH. Uniswap offers the better of its v3 and v4 routes as one quote. Launchpad coins that graduated to Uniswap v4, and all Moment coins, are reached through Uniswap v4; coins that graduated to Monday Trade are quoted by the Monday Trade venue.

Swap transactions carry a 10-minute deadline. Kuru Flow quotes are tied to your wallet address and refreshed automatically (Kuru allows one quote per second per address).

## Errors you might see

| Message | Meaning |
| --- | --- |
| No venue can route this pair right now. | None of the three venues found liquidity for this pair. |
| No route for this pair. | That one venue has no pool for the pair. |
| \<Venue\> did not answer within 20s. | Venue timed out; others still show. |
| Kuru Flow rate limit reached. Retrying on the next refresh. | Kuru's 1 request/second limit; wait for the next refresh. |
| Insufficient SYM | Amount exceeds your balance. |
| Not enough MON to pay for gas. | Top up MON. |

Next: [Slippage & Price Impact](slippage-and-price-impact.md) and [Adding Any Monad Token](adding-tokens.md).
