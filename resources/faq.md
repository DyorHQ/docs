# FAQ

## General

**Is DyorHQ a wallet or an exchange?**
A wallet with trading built in. The keys are on your iPhone; the trading happens on public protocols (Uniswap, Monday Trade, Kuru, Perpl) and on DyorHQ's own Launchpad and Moments contracts. DyorHQ never holds your funds.

**Which phones are supported?**
iPhone, iOS 18 or later. There's no Android or web app yet.

**How do I get the app?**
Join the waitlist at [dyorhq.fun](https://dyorhq.fun). Invites go out by email.

**Which network is this?**
Monad mainnet only (chain ID 143). Only send Monad-network assets to your DyorHQ address.

**Does DyorHQ charge fees?**
No fee on swaps. 5 MON to launch a coin, 50% of the 1% Launchpad trade fee (not the creator tax), the swap fees earned by Monday-graduated pools, 5% of Moment collects, 0.3% of Moment coin trades and 30% of an expired Moment's reserve. Full list in [Integrations & Fees](../platform/integrations-and-fees.md).

## Account & wallet

**I forgot my password. Can you reset it?**
No. With Email & Password your password *is* the wallet. Resetting creates a new, empty wallet linked to your email; the old wallet's funds still need the old password. See [Create Your Account](../getting-started/create-your-account.md).

**Can I use the same Email & Password wallet on two iPhones?**
Yes. The same email and password recreate the same wallet anywhere. Log In on the second device.

**Where's my seed phrase?**
Email & Password wallets don't show one; your credentials are the backup. Imported wallets keep the phrase or key you imported; you can reveal an imported private key under Manage Wallets → Export Wallet (Face ID required).

**Why does Sign Out ask me to make sure I have my backup?**
Because signing out deletes the wallet key from the device. You get it back with your password (Email & Password) or your phrase/key (imported).

**Where are Sign in with Apple, Google and Passkeys?**
Built, but switched off in the current build until the supporting infrastructure is live. They'll appear on the Get started screen when enabled.

**What's "Watch an address"?**
A read-only mode for following any Monad wallet. You see balances, positions, launches and Moments; you can't sign anything.

**What does "Require Face ID" do?**
Adds a Face ID prompt before your wallet signs a transaction from a confirmation sheet (swaps, sends, curve trades, on-chain perp orders and so on). Orders forwarded through One-Click Trading are signed by your Perpl trading key and don't prompt. Profile → Security.

## Swaps

**Which venue should I pick?**
The one tagged **Best** gives you the most output for that amount right now. You can pick another if you prefer a venue.

**Why do I need to approve a token?**
ERC-20 tokens require a one-time allowance for the venue's router (or Permit2 for Uniswap v4). The confirmation lists each approval as a step; approvals you've already made are skipped.

**Why did my swap fail?**
Usually the price moved beyond your slippage tolerance (the swap cancels instead of filling worse) or you ran out of MON for gas. Retry with a fresh quote or a slightly higher tolerance.

**Can I swap a coin that's still on its Launchpad curve?**
No. Curve trading happens on the coin's page in the Launch tab. Swap handles it after graduation.

## Perps

**Why can't I place an order?**
You need a Perpl account: deposit at least 10 AUSD first (Home → Transfer or Perps → ⋯ → Deposit AUSD).

**Why aren't my Take Profit / Stop Loss placed?**
They need One-Click Trading (Profile → Perpl Trading). Without it the position opens but triggers aren't placed.

**Why is my Trade History empty?**
It needs Perpl Trading connected (the trading key) under Profile → Perpl Trading. Connect it and the history loads.

**What leverage can I use?**
Up to each market's cap (1 ÷ initial margin fraction). Set your default under Trading Preferences.

**Can I use cross margin?**
No. Perpl offers isolated margin only.

## Launchpad

**What does launching cost?**
5 MON plus gas, plus whatever you put into an optional developer buy.

**What's the early-buy tax?**
A tax on buys in the first four seconds after launch (98% / 25% / 3% / 0.3%), designed to make sniping pointless. The creator's wallet (including its developer buy) is exempt.

**When does a coin graduate?**
When the curve has raised its pair asset's threshold (for example 4,324.56 USDC). See [Graduation](../launchpad/graduation.md).

**Can the liquidity be pulled?**
No. Neither locker can remove liquidity. The Monday vault can only harvest earned swap fees; the Uniswap v4 locker has no withdrawal path at all.

**Where do I claim fees or rewards?**
Holder rewards: on the coin's page (Your Holdings) or in My Launchpad → Claimable Fees, where **Claim All** runs every claim. Creator fees are paid to your wallet automatically on every trade; a claim is only needed if a payment couldn't be delivered, or for coins on the two oldest retired Launchpads, whose fees are booked for you to claim (rows marked **Retired launchpad**).

**My coin shows "Retired launchpad". Is something wrong?**
No. It was launched on an earlier Launchpad that DyorHQ retired on 2026-09-23. It keeps trading and keeps the graduation threshold it launched with; only new launches go to the current Launchpad. See [Past Cohorts & Retired Launchpads](past-cohorts-and-retired-launchpads.md).

## Moments

**Does publishing cost anything?**
No, only gas.

**What do I get when I collect?**
An NFT edition (on OpenSea immediately) and a coin entitlement that vests if the Moment graduates.

**What if the Moment never graduates?**
You keep the NFT. No coin is created. When the window closes, anyone can expire the Moment; the reserve goes 70% to the creator and 30% to DyorHQ.

**I sold my edition on OpenSea. Do I still get the coins?**
Yes. The coin entitlement stays with the wallet that collected; it doesn't travel with the NFT.

**Why does "Collect" say "Collect and Graduate"?**
Your collect would push the reserve to the threshold. It's clamped to exactly what's needed and the pool is created in the same transaction.

**Why is the trading fee 1.5%?**
0.5% pool fee (which deepens the locked position) plus 1% hook fee split 0.2% creator / 0.3% DyorHQ / 0.5% buyback-and-LP.

**Where did the earlier Moments go?**
On 2026-09-23 DyorHQ moved Moments to a new cohort (cohort 3). The five Moments of cohorts 1 and 2 are on retired contracts where publishing is paused. They stay on-chain, and if you hold an edition or coins in one, or created one, it's listed under **Past Cohorts** in My Moments and Portfolio. Those pages are claim-only: claim vested coins and, as the creator, withdraw your own proceeds and pool fees. They aren't part of **Claim All**, and past-cohort coins can't be traded in the app. See [Past Cohorts & Retired Launchpads](past-cohorts-and-retired-launchpads.md).

## Notifications

**Why didn't my price alert fire?**
Alerts are checked every 45 seconds while the app is open. There's no background push yet.

## Something's wrong

**A transaction says "sent but not confirmed".**
Check it on Monadscan via the View link. Monad blocks are fast; if it's still pending after a minute, the RPC may be lagging. Don't resend until you've confirmed the first one failed.

**How do I report a bug?**
Get Help → **Report a Bug**. It opens an email to team@dyorhq.fun with your app version and device pre-filled.
