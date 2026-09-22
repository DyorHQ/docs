# Creator Fees & Holder Rewards

Every launch chooses one of two fee modes at creation, and it can't be changed afterwards.

| Fee mode | Shown as | Who earns the creator side |
| --- | --- | --- |
| **Share fees with holders** (default) | "Shared with holders" | Every holder, pro-rata to balance, claimable any time |
| **To creator** | "To creator" | The launching wallet |

The DyorHQ side is always 50% of the curve fee and early-buy tax; the creator side is the other 50% plus the whole creator tax.

## Where fees come from

| Source | Rate | Phase |
| --- | --- | --- |
| Curve trade fee | 1% | Bonding |
| Early-buy tax | 98% / 25% / 3% / 0.3% in seconds 0–3 | Bonding |
| Creator tax | 0–10% | Bonding, and on Uniswap v4 pool swaps after graduation |
| Pool fee (Uniswap v4 hook) | 1% | After graduation on Uniswap v4 |
| Pool fee (Monday Trade) | Monday's 1% tier | After graduation on Monday Trade: earned by the locked position and harvested by DyorHQ, **not** distributed to the creator or holders |

## Holder rewards (fee-sharing coins)

If you hold a fee-sharing coin, your share of its fees accrues in the pair asset.

* On the coin's page, **Your Holdings** shows **Pending rewards** and a **Claim Rewards** button. A **Queued for holders** line shows rewards that are one block away from being claimable (a protection against flash-loan reward sniping added in the audit).
* In **My Launchpad → Claimable Fees**, every fee-sharing coin you hold has a "TICKER rewards" row with a **Claim** button, plus **Claim All** when there's more than one thing to claim.
* Rewards are settled to your balance before every transfer, so buying or selling never loses you what you've already earned.

{% hint style="info" %}
📸 **Screenshot here:** "Your Holdings" section on a coin page with Pending rewards and the Claim Rewards button. Suggested file: `.gitbook/assets/35-holder-rewards.png`
{% endhint %}

## Creator fees (to-creator coins)

If you launched a coin with fee sharing **off**, your fees are **paid straight to your wallet on every trade**. The fee escrow only comes into play if a payment can't be delivered (for example to a contract wallet that rejects it); that amount is then booked as claimable:

* On the coin's page, **Creator Fees** shows **Your claimable fees** and **Claim Creator Fees** (or "Nothing to claim yet, fees accrue as people trade your coin."). In the normal case this stays at zero because the fees already reached your wallet.
* One claim sweeps undelivered fees across **all your launches paired in that asset**. In **My Launchpad → Claimable Fees** you'll see one "Creator fees · \<PAIR\>" row per pair asset.

## After graduation on Uniswap v4

The DyorHQ hook collects the 1% pool fee (plus creator tax) on every swap and holds it per pool. A sweep pays DyorHQ 50% of the 1% fee; the other 50% plus the whole creator tax goes to the creator, or, for fee-sharing coins, to the holder-reward pool when the fee is in the pair asset (fees collected in the coin itself go to the creator). The sweep is a public contract call that anyone can trigger; it isn't yet exposed as a button in the app.

## Fee recipient changes

* A creator can hand their fee stream to another address on-chain.
* For abandoned launches, DyorHQ can propose a new recipient with a **3-day timelock** and a 3-day window to execute, the "community takeover" mechanism. The current recipient can cancel a pending takeover. DyorHQ cannot redirect a live launch's fees any other way.
