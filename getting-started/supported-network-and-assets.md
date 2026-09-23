# Supported Network & Assets

## Network

DyorHQ runs on one chain: **Monad mainnet**.

|              |                                        |
| ------------ | -------------------------------------- |
| Chain ID     | 143                                    |
| Native token | MON                                    |
| Block time   | \~0.4 s                                |
| Explorer     | [monadscan.com](https://monadscan.com) |
| Default RPC  | rpc.monad.xyz                          |

Every transaction link in the app ("View") opens Monadscan.

## Curated token list

The app ships with Monad's official token list (mainnet v2.48). These appear in the Swap picker, Send picker, Top Tokens and price alerts out of the box (the Send picker leaves out WMON and WBTC; Top Tokens and price alerts leave out WMON):

| Symbol | Name                                    | Address                                      |
| ------ | --------------------------------------- | -------------------------------------------- |
| MON    | Monad (native)                          | —                                            |
| WMON   | Wrapped MON                             | `0x3bd359C1119dA7Da1D913D1C4D2B7c461115433A` |
| USDC   | USDC                                    | `0x754704Bc059F8C67012fEd69BC8A327a5aafb603` |
| USDT0  | USDT0                                   | `0xe7cd86e13AC4309349F30B3435a9d337750fC82D` |
| WETH   | Wrapped Ether                           | `0xEE8c0E9f1BFFb4Eb878d8f15f368A02a35481242` |
| WBTC   | Wrapped BTC                             | `0x0555E30da8f98308EdB960aa94C0Db47230d2B9c` |
| cbBTC  | Coinbase Wrapped BTC                    | `0xd18B7EC58Cdf4876f6AFebd3Ed1730e4Ce10414b` |
| gMON   | gMON                                    | `0x8498312A6B3CbD158bf0c93AbdCF29E6e4F55081` |
| sMON   | Kintsu Staked Monad                     | `0xA3227C5969757783154C60bF0bC1944180ed81B9` |
| aprMON | aPriori Monad LST                       | `0x0c65A0BC65a5D819235B71F554D210D3F80E0852` |
| shMON  | ShMonad                                 | `0x1B68626dCa36c7fE922fD2d55E4f631d962dE19c` |
| AUSD   | AUSD                                    | `0x00000000eFE302BEAA2b3e6e1b18d08D69a9012a` |
| aBIL   | SPDR 1-3M T-Bill aStock (tokenized RWA) | `0x4fc5b9f8933597d3ecf84d0611687e1dc8dd576f` |
| USDe   | USDe                                    | `0x5d3a1Ff2b6BAb83b63cd9AD0787074081a52ef34` |
| USD1   | World Liberty Financial USD             | `0x111111d2bf19e43C34263401e0CAd979eD1cdb61` |
| mUSD   | MetaMask USD                            | `0xacA92E438df0B2401fF60dA7E4337B687a2435DA` |
| LBTC   | Lombard Staked Bitcoin                  | `0xecAc9C5F704e954931349Da37F60E39f515c11c1` |
| ezETH  | Renzo Restaked ETH                      | `0x2416092f143378750bb29b79eD961ab195CcEea5` |
| rETH   | Rocket Pool ETH                         | `0xC50f2e735eDd9dCD8Ccd41EcFE9894E679e3195f` |

**Any other ERC-20 on Monad** can be added by pasting its contract address in the Swap picker. See [Adding Any Monad Token](../spot/adding-tokens.md). Tokens you launch, buy on the Launchpad, or receive from a graduated Moment are added to your wallet's list automatically.

## Assets by product

| Product               | Asset                                                    |
| --------------------- | -------------------------------------------------------- |
| Swap                  | Any Monad token; MON ↔ WMON wraps 1:1                    |
| Perps                 | Collateral: AUSD. Markets: BTC, MON, ETH, SOL, HYPE, ZEC |
| Launchpad pair assets | MON, USDC, AUSD, aBIL                                    |
| Moments               | USDC only (collecting, reserve, trading pair)            |

## Prices

Spot prices in the app are read from the deepest on-chain pool for each token (Kuru, Uniswap v4, Uniswap v3, Monday Trade or nad.fun), quoted in USDC, AUSD or WMON and converted to USD, and the 24h change compares against the same pool one day of blocks earlier. USDC and AUSD are pinned to $1. Perps prices come from Perpl's exchange contract and market-data feed.
