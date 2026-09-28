# 📜 Contracts & Addresses

Everything DyorHQ touches on Monad mainnet (chain ID 143). DyorHQ's own contracts are immutable (no proxies) and source-verified. Always confirm an address here or on [monadscan.com](https://monadscan.com) before interacting with it outside the app. This page is updated with each new contract release.

## DyorHQ Launchpad

| Contract                            | Address                                      |
| ----------------------------------- | -------------------------------------------- |
| LaunchpadFactory                    | `0x6B1C8769a8d6745955aC35b91FF1F37AB76859dB` |
| LaunchAndBuyRouter                  | `0x454822dc56072696ab7cf8Bac357FFd3315477Fc` |
| LaunchDeployer                      | `0x91666B230B7F1780C189a90Df4BC40445B88C4bE` |
| FeeEscrow                           | `0x5EDA8765934fE22fa63d671465eF914Cd196968e` |
| HolderFeeSharing                    | `0xc618bB26bBc3C84c30519F31e32eE52EA2BFac52` |
| MemeHook (Uniswap v4 hook)          | `0xf2b849B3FC4a2b19B39DA3F707Fc32b801eea0Cc` |
| GraduationExecutor (Uniswap v4)     | `0x46Ef24229a494586049584a6Ba1E5ca530A738Ad` |
| MondayGraduationExecutor            | `0xBe0B7EA10B166Ba25577F00621211eC1036B93B3` |
| LaunchLocker (Uniswap v4 positions) | `0xac64BbB7bc4E638Bb30889ff6FE07289a21cE331` |
| MondayFeeVault (Monday positions)   | `0xfEEDF827c421f3a300630e680a367A42A1a26d50` |

Each launched coin has its own token and curve contracts; the token address is shown under **About** on its page.

**Earlier releases:** factories `0x10F34A174d9C393a90aFf94BDED7E1Db185446D7`, `0x2F02972E166dE71097EEAC8303cE7Fe6B6Ebe9f4` and `0xad3d3Cb821279E52cFD499D15b26f77976eBA1Ea`. Nothing new launches on them; coins launched there keep their pages, curves and history in the app.

## DyorHQ Moments&#x20;

| Contract                        | Address                                      |
| ------------------------------- | -------------------------------------------- |
| MomentsFactory                  | `0x0FD4aC52bbf387DBB3156805769bFC0c260F7E26` |
| MomentCollect                   | `0xb53897A4C6280480c267351518D184C2E6591D30` |
| MomentVesting                   | `0x05584910ab57d65723eB878D295b3353a4cbb021` |
| MomentGraduation                | `0xA2231E39ce7AE4f7d5e56Beae2dD3a8a59F3b9aA` |
| MomentLocker                    | `0x37C5A2c15d99701CF698B146cdCD1853825Ef455` |
| MomentFeeHook (Uniswap v4 hook) | `0xD5BFff467FDAe04664357e75bF059986c41260CC` |
| MomentBuyback                   | `0x3B574312Bb4e1D36C9a1Ba698bf77BbD223ca913` |

Each Moment has its own coin (ERC-20) and NFT (ERC-721) contracts, shown under **About this Moment**. The NFT's `external_url` points to `https://dyorhq.fun/moments/<id>`.

**Earlier releases (past cohorts):** factories `0xc12B6b6948185cef75F861c5327702c30CB8a581` and `0x64698c7702d85F87f43a6dFF7D495CDD2327C020`. Publishing is closed on them. In the app, holders can claim vested coins and creators can withdraw their own proceeds and pool fees; collecting and trading are closed.

## Venues and infrastructure

|                          | Address                                      |
| ------------------------ | -------------------------------------------- |
| Perpl Exchange           | `0x34B6552d57a35a1D042CcAe1951BD1C370112a6F` |
| Uniswap v4 PoolManager   | `0x188d586Ddcf52439676Ca21A244753fA19F9Ea8e` |
| Uniswap Universal Router | `0x0d97dc33264bfc1c226207428a79b26757fb9dc3` |
| Uniswap v4 Quoter        | `0xa222dd357a9076d1091ed6aa2e16c9742dd26891` |
| Uniswap v4 StateView     | `0x77395f3b2e73ae90843717371294fa97cc419d64` |
| Uniswap v3 SwapRouter02  | `0xfe31f71c1b106eac32f1a19239c9a9a72ddfb900` |
| Uniswap v3 QuoterV2      | `0x661e93cca42afacb172121ef892830ca3b70f08d` |
| Permit2                  | `0x000000000022D473030F116dDEE9F6B43aC78BA3` |
| Monday Trade SwapRouter  | `0xFE951b693A2FE54BE5148614B109E316B567632F` |
| Monday Trade QuoterV2    | `0xB97eCD41Aef0F842E773C8F9905919cDE49880C9` |
| Kuru Flow Entrypoint     | `0xb3e6778480b2E488385E8205eA05E20060B813cb` |
| WMON                     | `0x3bd359C1119dA7Da1D913D1C4D2B7c461115433A` |
| USDC                     | `0x754704Bc059F8C67012fEd69BC8A327a5aafb603` |
| AUSD                     | `0x00000000eFE302BEAA2b3e6e1b18d08D69a9012a` |
| aBIL                     | `0x4fc5b9f8933597d3ecf84d0611687e1dc8dd576f` |

The full curated token list is in [Supported Network & Assets](../getting-started/supported-network-and-assets.md).

## Approvals the app may ask for

| Spender                                                       | Why                                                                                                                                                                                   |
| ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Permit2                                                       | Uniswap v4 swaps: an exact approval of the input token to Permit2, then a Permit2 allowance for the Universal Router for that amount, which expires about two minutes after it is set |
| Uniswap SwapRouter02, Monday SwapRouter, Kuru Flow Entrypoint | Exact-amount approvals per swap                                                                                                                                                       |
| LaunchAndBuyRouter / curves                                   | Pair-asset approval for developer buys (router) and curve buys (curve); coin approval for curve sells. The launch fee is paid in MON, no approval.                                    |
| MomentCollect                                                 | An exact USDC approval of what each Moment collect costs                                                                                                                              |
| Perpl Exchange                                                | AUSD approval for deposits                                                                                                                                                            |
| Aurora deposit addresses                                      | Direct transfers when bridging (no approval)                                                                                                                                          |
