# 📜 Contracts & Addresses

Everything DyorHQ touches on Monad mainnet (chain ID 143). DyorHQ's own contracts are immutable (no proxies) and source-verified. Always confirm an address here or on [monadscan.com](https://monadscan.com) before interacting with it outside the app. This page is updated with each new contract release.

## DyorHQ Launchpad

| Contract                            | Address                                      |
| ----------------------------------- | -------------------------------------------- |
| LaunchpadFactory                    | `0x3B1f5f562f5F61B980aBfDDbebD6cdF9a73b0b5b` |
| LaunchDeployer                      | `0x4DE6B141249488Ab20f9BD04d78489Ae6b31EaC9` |
| CurveDeployer                       | `0xc93BA85c831A21e8f964dF61ceBb8ea0386190bC` |
| FeeEscrow                           | `0x690eaa0b66C3738887007a0D99ED90b5f5af86F1` |
| HolderFeeSharing                    | `0x5358a136a50eE4F961B532064dc641E8F4Fa5656` |
| MemeHook (Uniswap v4 hook)          | `0xb845b4Dd429684b67eeEa9D484F5e903B28360CC` |
| GraduationExecutor (Uniswap v4)     | `0xFD1114592a066ceeE3979b08557516A161aDAc19` |
| MondayGraduationExecutor            | `0xd655203ca7D5b46fB5cE1e4E0Fce79150E80A53A` |
| LaunchLocker (Uniswap v4 positions) | `0x8A2BDd88169C600c3376495Da5e21D9E76119295` |
| MondayFeeVault (Monday positions)   | `0x50E12ecC1d8138104Da52A67e93a014763B4A540` |

Each launched coin has its own token and curve contracts; the token address is shown under **About** on its page. The factory's modules are sealed: none of them can be swapped for another contract.

## DyorHQ Moments

| Contract                        | Address                                      |
| ------------------------------- | -------------------------------------------- |
| MomentsFactory                  | `0x95eb7F5A88B10D9dF32aC54F48C767927fa80840` |
| MomentCollect                   | `0xe6beb4A10827a2e50B155B7386b1369d504186Cc` |
| MomentVesting                   | `0x6Eb483C1E1Be2b6700AD590ddE326B597a13649A` |
| MomentGraduation                | `0x736dD4c4A09Ef41C508bb2175001eA038A3D5152` |
| MomentLocker                    | `0xe86557E2B44c119B05948c918C9Eb0c1cE5331a0` |
| MomentFeeHook (Uniswap v4 hook) | `0xDa7042CF42B26Be4d6816C9eeB1B0bee8e3Fe0cc` |
| MomentBuyback                   | `0xFAf9Ad081d43F6A1b949DB81A2d7145F19845613` |
| Guardian                        | `0x686C7A2886608082e698E0062EA3E4C408d43845` |

Each Moment has its own coin (ERC-20) and NFT (ERC-721) contracts, shown under **About this Moment**. The NFT's `external_url` points to `https://dyorhq.fun/moments/c4/<id>`; with the DyorHQ app installed it opens the Moment in the app, as its name link does. The guardian can pause and unpause publishing, cancel a queued policy change and hand its role on; it can't move funds or change a published Moment. The platform and treasury wallets are the ones the **Publish** sheet shows; each Moment keeps the wallets it was published with.

## Venues and infrastructure

|                          | Address                                      |
| ------------------------ | -------------------------------------------- |
| Perpl Exchange           | `0x34B6552d57a35a1D042CcAe1951BD1C370112a6F` |
| Uniswap v4 PoolManager   | `0x188d586Ddcf52439676Ca21A244753fA19F9Ea8e` |
| Uniswap Universal Router | `0x0D97Dc33264bfC1c226207428A79b26757fb9dc3` |
| Uniswap v4 Quoter        | `0xa222Dd357A9076d1091Ed6Aa2e16C9742dD26891` |
| Uniswap v4 StateView     | `0x77395F3b2E73aE90843717371294fa97cC419D64` |
| Uniswap v3 SwapRouter02  | `0xfE31F71C1b106EAc32F1A19239c9a9A72ddfb900` |
| Uniswap v3 QuoterV2      | `0x661E93cca42AfacB172121EF892830cA3b70F08d` |
| Permit2                  | `0x000000000022D473030F116dDEE9F6B43aC78BA3` |
| Monday Trade SwapRouter  | `0xFE951b693A2FE54BE5148614B109E316B567632F` |
| Monday Trade QuoterV2    | `0xB97eCD41Aef0F842E773C8F9905919cDE49880C9` |
| Kuru Flow Entrypoint     | `0xb3e6778480b2E488385E8205eA05E20060B813cb` |
| WMON                     | `0x3bd359C1119dA7Da1D913D1C4D2B7c461115433A` |
| USDC                     | `0x754704Bc059F8C67012fEd69BC8A327a5aafb603` |
| AUSD                     | `0x00000000eFE302BEAA2b3e6e1b18d08D69a9012a` |
| aBIL                     | `0x4FC5B9f8933597D3ecf84d0611687E1Dc8DD576f` |

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
