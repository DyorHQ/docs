# Risk Disclosures

DyorHQ is a self-custodial interface to public, permissionless protocols on Monad. Using it involves real risk of loss. Please read this page before you trade, launch, publish or collect.

## General

* **Self-custody means self-responsibility.** DyorHQ cannot recover a lost password, phrase or key, reverse a transaction, or freeze funds. See [Self-Custody & Security](../platform/self-custody-and-security.md).
* **Nothing here is investment advice.** Prices, charts, "Top Tokens", holder counts and P&L are information, not recommendations.
* **Early access.** The app is in early access. Expect rough edges, and never put in more than you can afford to lose.
* **Third-party protocols.** Swaps, perps and bridging run on contracts DyorHQ does not control (Uniswap, Monday Trade, Kuru, Perpl, Aurora). Their availability, fees and behaviour can change.
* **Smart contract risk.** Contracts can have bugs. Both the Launchpad and the Moments contracts have had internal security reviews with proof-of-concept, fuzz, invariant and fork testing, and the Launchpad was redeployed with its fixes. No independent audit has been completed yet; one is planned after the Moments validation launch.
* **Monad network risk.** RPC outages, reorgs and congestion can delay or fail transactions. Gas is charged on the limit, not usage.
* **Tax.** Selling, swapping or earning tokens may be taxable where you live.

## Spot swaps

* Any token can be listed by anyone. Names and symbols are not unique. Verify contract addresses.
* Thin pools mean high price impact. Watch the **Impact** figure and your slippage tolerance.
* Quotes are estimates; the slippage floor is the only guarantee.

## Perpetuals

* Leverage magnifies gains and losses. **You can lose your entire margin** on a position through liquidation.
* Market orders fill inside your slippage band or cancel; limit orders may never fill.
* Funding payments accrue every hour while a position is open.
* Take Profit / Stop Loss are keeper-managed triggers; they need One-Click Trading and a live connection, and are not guaranteed to fill at the trigger price in fast markets.
* Perpl's exchange is a third-party protocol with its own risks and rules.

## Launchpad

* Launch coins are highly speculative. Most will lose most of their value.
* The early-buy tax is severe (98% in the first second). Buying in the first seconds without an exemption almost guarantees a loss.
* The creator sets a creator tax of up to 10% on every curve trade and whether fees go to holders or to themselves. Check **About** before trading.
* Graduation is not guaranteed. Coins that never graduate stay on their curve. If graduation fails for 7 days the owner can put the launch into refund mode; the app doesn't yet expose refund-mode selling.
* Locked liquidity cannot be withdrawn by anyone, which also means it can never be "rescued".
* Coins paired with aBIL depend on that asset's liquidity on Monday Trade.

## Moments

* **The collector cohort is negative-sum without new demand.** 25% of every collect goes to the creator and DyorHQ before any trading. Absent new buyers after graduation, collectors as a group recover less than they paid.
* **Most Moments will never graduate.** That's by design: they remain keepsakes and no coin is created. Do not collect expecting a coin.
* **A graduated coin can be thin.** A single wallet can collect a Moment to its threshold and sell into the pool. DyorHQ shows holder counts and the top wallet's share; use them.
* **Vesting.** Collector coins unlock 60% at graduation, then 20% a month for two months. Creator coins unlock over five months. The price can move a lot in between.
* **Editions are bearer NFTs.** Owning an edition doesn't prove you were there, and nothing verifies that a creator owns the media they publish. The coin entitlement stays with the collecting wallet, not the NFT.
* **Media is permanent.** Once published, the media pointer and fingerprint can't be changed by anyone. Publish only what you have the right to publish.
* **No KYC, no geofence.** DyorHQ Moments is a permissionless protocol. Whether you may use it, and how gains are taxed, depends on your jurisdiction. It's on you to check.
* **Marketplaces are third parties.** OpenSea can delist collections and doesn't guarantee royalties.

## Bridge

Cross-chain transfers are settled by Aurora Intents and can be delayed or refunded. Never bridge more than you can wait for.

---

By using DyorHQ you accept the [Terms of Use](https://dyorhq.fun/terms).
