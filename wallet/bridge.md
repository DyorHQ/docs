# Bridge (Coming Soon)

{% hint style="info" %}
The Bridge is built into the app and will be switched on in an upcoming build. Until then the Bridge screen reads *"Cross-chain bridging isn't configured in this build yet."* Everything below describes how it works once enabled.
{% endhint %}

DyorHQ's bridge is powered by **Aurora Intents** (NEAR Intents). You send on one chain, Aurora settles across chains, and the funds arrive in your DyorHQ wallet on Monad, or the other way round.

**Where:** Home → **Bridge**.

{% hint style="info" %}
📸 **Screenshot here:** Bridge screen with Base → Monad selected, an amount, and the fee / time / route summary. Suggested file: `.gitbook/assets/53-bridge.png`
{% endhint %}

## Supported chains

One side is always **Monad**. The other can be: Ethereum, Base, Arbitrum, Optimism, Polygon, BNB Chain, Avalanche, Gnosis, Scroll or Berachain. The default is **Base → Monad**; a flip button reverses direction.

Tokens come from Aurora's list for each chain, with stablecoins (USDC, USDT0, USDT) first. The **Bridge from** picker lists every asset you hold across the supported chains, largest value first, with balances read from public RPCs.

## How to bridge

1. Pick the source chain and token. Enter an amount (25% / 50% / 75% / **Max**).
2. Read the summary: **You receive**, **Minimum received**, **Total fee** (one dollar figure and percentage covering Aurora's protocol fee, withdrawal fee, spread and any DyorHQ integrator fee), **Slippage** (default 1%, adjustable), **Estimated time**, **Route**.
3. Tap **Bridge to Monad** (or **Bridge to \<Chain\>**). There's no separate confirmation sheet: the summary above the button is the review. With Require Face ID on, confirm with Face ID.
4. The app sends exactly the quoted amount to Aurora's deposit address on the source chain, notifies Aurora, and tracks the status for up to about ten minutes.

## Status messages

*Sending on \<Chain\>…* → *Notifying the bridge…* → *Confirming your deposit…* → *Waiting for the full deposit…* → *Bridging across chains…* → **Arrived** (or **Refunded** / **Failed**).

When it lands: "Arrived on Monad · Received X", with a **View** link that upgrades from the deposit transaction to the destination transaction. If it's slow you'll see *"Still settling, this can take a minute…"* and then *"Taking longer than usual, your funds are on their way…"*; the bridge completes in the background and shows in your balance and Activity when it lands. A refund returns funds on the source chain and tells you why.

Completed bridges appear in Portfolio under **Bridge** and post a "Bridge complete" notification.

## Fees

Aurora's quote includes its own fees. DyorHQ may add an integrator fee of 0.1% once the bridge is live. Everything is shown in the **Total fee** row before you confirm.
