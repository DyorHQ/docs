# Contracts & Addresses

Everything DyorHQ touches on Monad mainnet (chain ID 143). DyorHQ's own contracts are immutable (no proxies) and source-verified. Always confirm an address here or on [monadscan.com](https://monadscan.com) before interacting with it outside the app.

The current Launchpad and Moments contracts were deployed on **2026-09-23**. Earlier DyorHQ contracts are listed separately under [Retired — do not use for new activity](#retired-do-not-use-for-new-activity).

## DyorHQ Launchpad (live)

| Contract | Address |
| --- | --- |
| LaunchpadFactory | `0x6B1C8769a8d6745955aC35b91FF1F37AB76859dB` |
| LaunchAndBuyRouter | `0x454822dc56072696ab7cf8Bac357FFd3315477Fc` |
| LaunchDeployer | `0x91666B230B7F1780C189a90Df4BC40445B88C4bE` |
| CurveDeployer (created by LaunchDeployer) | `0x9809487C34FBeDb497E4Dc72B8667095093d18df` |
| FeeEscrow | `0x5EDA8765934fE22fa63d671465eF914Cd196968e` |
| HolderFeeSharing | `0xc618bB26bBc3C84c30519F31e32eE52EA2BFac52` |
| MemeHook (Uniswap v4 hook) | `0xf2b849B3FC4a2b19B39DA3F707Fc32b801eea0Cc` |
| GraduationExecutor (Uniswap v4) | `0x46Ef24229a494586049584a6Ba1E5ca530A738Ad` |
| MondayGraduationExecutor | `0xBe0B7EA10B166Ba25577F00621211eC1036B93B3` |
| LaunchLocker (Uniswap v4 positions) | `0xac64BbB7bc4E638Bb30889ff6FE07289a21cE331` |
| MondayFeeVault (Monday positions) | `0xfEEDF827c421f3a300630e680a367A42A1a26d50` |

Each launched coin has its own token and curve contracts; the token address is shown under **About** on its page.

## DyorHQ Moments (cohort 3, live)

| Contract | Address |
| --- | --- |
| MomentsFactory | `0x0FD4aC52bbf387DBB3156805769bFC0c260F7E26` |
| MomentCollect | `0xb53897A4C6280480c267351518D184C2E6591D30` |
| MomentVesting | `0x05584910ab57d65723eB878D295b3353a4cbb021` |
| MomentGraduation | `0xA2231E39ce7AE4f7d5e56Beae2dD3a8a59F3b9aA` |
| MomentLocker | `0x37C5A2c15d99701CF698B146cdCD1853825Ef455` |
| MomentFeeHook (Uniswap v4 hook) | `0xD5BFff467FDAe04664357e75bF059986c41260CC` |
| MomentBuyback | `0x3B574312Bb4e1D36C9a1Ba698bf77BbD223ca913` |

Policy snapshot on this factory: threshold 771.428571 USDC, minimum price 0.10 USDC, LP fee 0.5%, royalty 5%, expiry share 70% creator. Every Moment snapshots the policy and fee wallets when it is published.

Each Moment has its own coin (ERC-20) and NFT (ERC-721) contracts, shown under **About this Moment**. Moment ids restart at 1 on every factory, so the NFT's `external_url` carries a per-cohort path:

| Cohort | NFT `external_url` |
| --- | --- |
| Cohort 3 (live) | `https://dyorhq.fun/moments/<id>` |
| Cohort 2 (retired) | `https://dyorhq.fun/moments/c2/<id>` |
| Cohort 1 (retired) | `https://dyorhq.fun/moments/c1/<id>` |

The link is read from the factory each time a marketplace asks for the metadata, so DyorHQ governance can repoint it (it did so for cohorts 1 and 2 on 2026-09-23). It carries no funds and changes nothing else about a Moment. Marketplaces may need a "refresh metadata" to show a new link.

## DyorHQ wallets

| Role | Address |
| --- | --- |
| Treasury (Launchpad protocol fees and launch fee; Moments treasury share) | `0x5aDbDc19831D0f9dbdfBbA6ee3d618DbB9CEA371` |
| Fees (Monday LP fees; Moments platform share) | `0x15ED3bb488231213b141A2f78b62358D52235Cd7` |
| Governance / owner (deploys and administers the contracts) | `0xCf7A9f1DE835a691f969B76e6eb4842BFaA7Fe10` |

{% hint style="danger" %}
**Retired wallets. Never send funds to these addresses.**

* `0x5282cC04f2F17Cc296C5aEFa2576C4C0327cf045` (former treasury)
* `0xf4D4baF60e5fcAF6A092b2d6B5509af9f01Cfb48` (former fees wallet)

DyorHQ replaced them on 2026-09-23. No live contract pays them. Moments published on the retired cohorts 1 and 2 still name them, because each Moment keeps the wallets it was published with.
{% endhint %}

## Retired — do not use for new activity

These contracts are still on-chain and still hold existing positions, but DyorHQ no longer uses them for anything new. Don't start new activity on them from outside the app. What you can still do with your own positions is explained in [Past Cohorts & Retired Launchpads](past-cohorts-and-retired-launchpads.md).

### Retired Launchpads

On 2026-09-23 all three were closed to new launches (a launch there reverts), and their protocol fees and Monday LP fees were repointed to the current DyorHQ wallets above. Coins already launched on them keep trading on their curves and pools, and keep the graduation thresholds they were launched with.

| Launchpad | Factory | Router | FeeEscrow |
| --- | --- | --- | --- |
| September 16 audit-fix deployment | `0x10F34A174d9C393a90aFf94BDED7E1Db185446D7` | `0x3eE688C3b3aCd652914aD49d8Ee5ae1004bF3690` | `0xbc70ba9D66F761FFb7647D6B52C8Cf65a49E47fc` |
| September 12 deployment | `0x2F02972E166dE71097EEAC8303cE7Fe6B6Ebe9f4` | `0xbaEa633e9Ba5d927bfD6a0f5b3FB3982784DA30D` | `0xeDC73b06BE454714b6Bd0C1c742e51e605664B2A` |
| First deployment | `0xad3d3Cb821279E52cFD499D15b26f77976eBA1Ea` | `0xd5862DfB44831868CF8f459aA270d05d32031CE1` | `0x1253b18077E8b52FC2522F5B62Ebd2B176383231` |

Other contracts of the `0x10F3…` stack: LaunchDeployer `0x53C2e716bA77F75c5A433292e1017d6b8Af0A445`, HolderFeeSharing `0x70F8f64c6A4A76A507e322BCef19E6E37abe4eF6`, MemeHook `0x51A240c13164BcDF3FC11053FddEaC626A4160cc`, GraduationExecutor `0x787e49e7d2E1Bb1EF4Ee4A82DF1DE34fe3f745DA`, MondayGraduationExecutor `0x5c83D58228b9Ba133E68ea583f28dddCaf488fEd`, LaunchLocker `0x86d5143A9316d97b11a2A35C2362bf1068518902`, MondayFeeVault `0x42a1C1c1d6BC2544d3f478E4d42F5b5ec75888De`.

HolderFeeSharing and MemeHook of the older stacks: `0x1413CB051f78a4605cD150d4E97B1B06f81e2Bdf` and `0x22957b1d794A7Ca37D054acB5e993e026826E0Cc` (`0x2F02…`), `0x0C7a1F7625696bAbF9a7309ed3c4A9086eFEE8dd` and `0xB0c2Fa59aA9f30BC0907bcD785bFf068fEb0E0Cc` (`0xad3d…`). Their Monday fee vaults `0xC154C85e8a2A73B99676C31dcE8627D67A9F376A` and `0x97B80811036306838e48C409543F7C50bb6e494B` now pay the current fees wallet.

### Retired Moments cohorts

Publishing is paused on every retired Moments factory. Each of their Moments snapshotted the retired wallets above when it was published.

| Cohort | MomentsFactory | MomentCollect | MomentVesting | Status |
| --- | --- | --- | --- | --- |
| Cohort 2 ($2,000-FDV policy, 2 Moments) | `0xc12B6b6948185cef75F861c5327702c30CB8a581` | `0x8f65ea0236b5fa6351a45Bd48244c3525Fb92493` | `0xe087eff01C567F88a7cb6BDBDBF04B46Fee56C99` | Publishing paused 2026-09-23. Claim-only in the app. |
| Cohort 1 ($10 threshold, 3 Moments) | `0x64698c7702d85F87f43a6dFF7D495CDD2327C020` | `0xb4EE9e67d9e1772BC6949748e3755EA7C1DFE32c` | `0x360E2068eAEc5b5A9AF60A7c4059Bd4b30B7209C` | Publishing paused. Claim-only in the app. |
| v1 | `0x47D989a54232D3bCdB7A7760D10E596647D986BA` | `0x582E63927Ef364b3737c5F4861517C2C99a8B784` | `0xB58894e56737cd21e8dD70B9cc69e89D2AAe2466` | Publishing paused. Not shown in the app. |

Other cohort 2 contracts: MomentGraduation `0x353F245A2458B994a65116A4c69643cf6608045b`, MomentLocker `0x995735cF317656a10de52b73AB50A2aAdc069a8a`, MomentFeeHook `0x501D703588c4feAbBeE5A9a77408c7FCbD3a20Cc`, MomentBuyback `0xacae95377513C54DA9ff549DFE5cB77001F6c6F5`. Other cohort 1 contracts: MomentGraduation `0x307De00950F039969855eFb859A6088d695e76b1`, MomentLocker `0x832851A42Bf1FD1aF7a19c82cF132290c605E406`, MomentFeeHook `0x8Aa322471Bef2996D3B50cB12F63C6A0054460Cc`, MomentBuyback `0x03282D5421a3bE3ff79c5962819c9a6e5E0b52d2`.

{% hint style="warning" %}
**Don't collect on a retired cohort.** The pause only covers publishing. Collecting is closed in the DyorHQ app, but not on-chain: a retired Moment that is still inside its collecting window can technically be collected from outside the app. Don't. Its platform and treasury shares go to the retired wallets, and the app treats the result as a past cohort (claim-only, not tradable).
{% endhint %}

## Venues and infrastructure

| | Address |
| --- | --- |
| Perpl Exchange | `0x34B6552d57a35a1D042CcAe1951BD1C370112a6F` |
| Uniswap v4 PoolManager | `0x188d586Ddcf52439676Ca21A244753fA19F9Ea8e` |
| Uniswap Universal Router | `0x0d97dc33264bfc1c226207428a79b26757fb9dc3` |
| Uniswap v4 Quoter | `0xa222dd357a9076d1091ed6aa2e16c9742dd26891` |
| Uniswap v4 StateView | `0x77395f3b2e73ae90843717371294fa97cc419d64` |
| Uniswap v3 SwapRouter02 | `0xfe31f71c1b106eac32f1a19239c9a9a72ddfb900` |
| Uniswap v3 QuoterV2 | `0x661e93cca42afacb172121ef892830ca3b70f08d` |
| Permit2 | `0x000000000022D473030F116dDEE9F6B43aC78BA3` |
| Monday Trade SwapRouter | `0xFE951b693A2FE54BE5148614B109E316B567632F` |
| Monday Trade QuoterV2 | `0xB97eCD41Aef0F842E773C8F9905919cDE49880C9` |
| Kuru Flow Entrypoint | `0xb3e6778480b2E488385E8205eA05E20060B813cb` |
| WMON | `0x3bd359C1119dA7Da1D913D1C4D2B7c461115433A` |
| USDC | `0x754704Bc059F8C67012fEd69BC8A327a5aafb603` |
| AUSD | `0x00000000eFE302BEAA2b3e6e1b18d08D69a9012a` |
| aBIL | `0x4fc5b9f8933597d3ecf84d0611687e1dc8dd576f` |

The full curated token list is in [Supported Network & Assets](../getting-started/supported-network-and-assets.md).

## Approvals the app may ask for

| Spender | Why |
| --- | --- |
| Permit2 | Uniswap v4 swaps and Moment collects (unlimited approval of the token to Permit2, then scoped allowances) |
| Uniswap SwapRouter02, Monday SwapRouter, Kuru Flow Entrypoint | Exact-amount approvals per swap |
| LaunchAndBuyRouter / curves | Pair-asset approval for developer buys (router) and curve buys (curve); coin approval for curve sells. The launch fee is paid in MON, no approval. |
| Perpl Exchange | AUSD approval for deposits |
| Aurora deposit addresses | Direct transfers when bridging (no approval) |
