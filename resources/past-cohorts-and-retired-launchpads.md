# Past Cohorts & Retired Launchpads

On **2026-09-23** DyorHQ deployed a new Launchpad and a new Moments cohort (cohort 3) that pay DyorHQ's new fee wallets, and retired the earlier contracts. Nothing you hold on the old contracts was moved or lost: your coins, editions, vesting and fees are still on-chain. This page explains what you can still do with them. The addresses are in [Contracts & Addresses](contracts-and-addresses.md#retired-do-not-use-for-new-activity).

## What was retired

| | Contracts | Status |
| --- | --- | --- |
| **Launchpad** | Three earlier factories (`0x10F3…`, `0x2F02…`, `0xad3d…`) | Closed to new launches. Coins already launched there keep trading. |
| **Moments** | Cohort 2 (`0xc12B…`, 2 Moments) and cohort 1 (`0x6469…`, 3 Moments) | Publishing paused. Claim-only in the app. |
| **Moments** | v1 (`0x47D9…`) | Publishing paused. Not shown in the app. |

New launches and new Moments only happen on the live contracts.

## Moments from past cohorts

If your wallet has anything in a retired cohort (an edition, coins still vesting or unclaimed, or creator earnings), it shows up under **Past Cohorts**:

* **My Moments** (Moments tab → the person icon), below **Your Moments**
* **Portfolio**, as a **Past Cohorts** card

Each row opens the Moment's claim-only page, marked **Past cohort — collecting closed**. There you can:

* **Claim** your vested coins, if the Moment graduated
* As its creator, **Withdraw Proceeds** and, once it has graduated, **Withdraw Pool Fees**

That's all. Collecting, expiring, retrying a graduation, buybacks and trading are closed for past cohorts in the app, because each of those would pay or credit DyorHQ's retired fee wallets.

{% hint style="info" %}
Past cohorts are **not** part of the four tiles at the top of My Moments and are **not** included in **Claim All**. Claim each past-cohort Moment from its own page.
{% endhint %}

Cohort 1's Moment #2 graduated before the relaunch, so its collectors and creator can keep claiming from its Past Cohorts page as their coins vest.

### Past-cohort coins and editions

* A past cohort's coin shows as **Past cohort · trading closed** in Home, Portfolio, Swap and on its Moment page. The app doesn't offer a swap for it.
* Your editions stay yours. In **Portfolio → My Holdings → NFTs** they show as **Past cohort Moment** and open the claim-only page.
* Their NFT links use a per-cohort path (`https://dyorhq.fun/moments/c1/<id>` and `https://dyorhq.fun/moments/c2/<id>`), because Moment numbers restart at 1 on every cohort.

{% hint style="warning" %}
"Collecting closed" is true **in the DyorHQ app**. The retired collect contracts have no pause, so a past-cohort Moment still inside its window could be collected on-chain from outside the app. Don't: its fee shares go to the retired wallets and the result is claim-only.
{% endhint %}

## Coins on retired Launchpads

* Coins launched on a retired Launchpad keep trading: on their curve until they graduate, then in Swap. Their cards and pages carry a **Retired launchpad** label.
* They keep the graduation threshold they were launched with, which can differ from the live Launchpad's figures in [Graduation](../launchpad/graduation.md). The coin's page shows its own *"Graduates at X \<PAIR\> raised"* figure.
* Holder rewards on fee-sharing coins work as before, from the coin's page or **My Launchpad → Claimable Fees**.

### Creator fees on the `0x2F02…` and `0xad3d…` Launchpads

The fee escrows of these two older Launchpads **book creator fees as a claimable balance** instead of paying them straight to your wallet on every trade. If you launched a coin with fee sharing off on one of them, your fees wait for you in **My Launchpad → Claimable Fees**, in a **Creator fees · \<PAIR\>** row captioned **Retired launchpad**. Tap **Claim** on the row, or **Claim All** to include it with everything else.

## If something looks missing

Pull to refresh on My Moments or Portfolio. If a past cohort can't be read, the app says *"Couldn't read every past cohort (pull to refresh)"* rather than hiding it. If it still looks wrong, email [team@dyorhq.fun](mailto:team@dyorhq.fun) with your wallet address (never your password, phrase or key).
