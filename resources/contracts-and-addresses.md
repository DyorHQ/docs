# Contracts & Addresses

Everything DyorHQ touches on Monad mainnet (chain ID 143). DyorHQ's own contracts are immutable (no proxies) and source-verified. Always confirm an address here or on [monadscan.com](https://monadscan.com) before interacting with it outside the app.

## DyorHQ Launchpad

| Contract | Address |
| --- | --- |
| LaunchpadFactory | `0x10F34A174d9C393a90aFf94BDED7E1Db185446D7` |
| LaunchAndBuyRouter | `0x3eE688C3b3aCd652914aD49d8Ee5ae1004bF3690` |
| LaunchDeployer | `0x53C2e716bA77F75c5A433292e1017d6b8Af0A445` |
| FeeEscrow | `0xbc70ba9D66F761FFb7647D6B52C8Cf65a49E47fc` |
| HolderFeeSharing | `0x70F8f64c6A4A76A507e322BCef19E6E37abe4eF6` |
| MemeHook (Uniswap v4 hook) | `0x51A240c13164BcDF3FC11053FddEaC626A4160cc` |
| GraduationExecutor (Uniswap v4) | `0x787e49e7d2E1Bb1EF4Ee4A82DF1DE34fe3f745DA` |
| MondayGraduationExecutor | `0x5c83D58228b9Ba133E68ea583f28dddCaf488fEd` |
| LaunchLocker (Uniswap v4 positions) | `0x86d5143A9316d97b11a2A35C2362bf1068518902` |
| MondayFeeVault (Monday positions) | `0x42a1C1c1d6BC2544d3f478E4d42F5b5ec75888De` |

Each launched coin has its own token and curve contracts; the token address is shown under **About** on its page.

## DyorHQ Moments (cohort 2, live)

| Contract | Address |
| --- | --- |
| MomentsFactory | `0xc12B6b6948185cef75F861c5327702c30CB8a581` |
| MomentCollect | `0x8f65ea0236b5fa6351a45Bd48244c3525Fb92493` |
| MomentVesting | `0xe087eff01C567F88a7cb6BDBDBF04B46Fee56C99` |
| MomentGraduation | `0x353F245A2458B994a65116A4c69643cf6608045b` |
| MomentLocker | `0x995735cF317656a10de52b73AB50A2aAdc069a8a` |
| MomentFeeHook (Uniswap v4 hook) | `0x501D703588c4feAbBeE5A9a77408c7FCbD3a20Cc` |
| MomentBuyback | `0xacae95377513C54DA9ff549DFE5cB77001F6c6F5` |

Each Moment has its own coin (ERC-20) and NFT (ERC-721) contracts, shown under **About this Moment**. The NFT's `external_url` points to `https://dyorhq.fun/moments/<id>`.

Policy snapshot on this factory: threshold 771.428571 USDC, minimum price 0.10 USDC, LP fee 0.5%, royalty 5%, expiry share 70% creator. An earlier validation stack (factory `0x64698c7702d85F87f43a6dFF7D495CDD2327C020`, $10 threshold) is retired: publishing is paused there and its Moments are not shown in the app.

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
