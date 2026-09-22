# Glossary

**aBIL** — Anchored's tokenized SPDR 1-3M T-Bill "aStock" on Monad. A transferable ERC-20 with liquidity on Monday Trade. One of the Launchpad's pair assets.

**AUSD** — The stablecoin Perpl uses as collateral. Also a Launchpad pair asset.

**Bonding curve** — The pricing mechanism a Launchpad coin trades on before graduation. Price rises as the curve fills and falls as it empties.

**Buyback-and-LP** — Moments mechanism where 0.5% of the USDC side of every trade buys the coin and adds it, paired with USDC, to the locked pool so depth grows with volume.

**Collect** — Paying the collect price in USDC for one or more editions of a Moment.

**Collect window** — The 1–30 day period during which a Moment can be collected. Ends early at graduation.

**Creator tax** — An optional 0–10% fee a Launchpad creator sets on curve trades (and Uniswap v4 pool swaps), paid to the creator or shared with holders.

**Curve fee** — The 1% fee on every Launchpad curve trade.

**Developer buy** — A creator's own purchase made in the same transaction as the launch. The creator's wallet is always exempt from the early-buy tax.

**DyorHQ Social** — Your handle, display name, bio and photo, attached to your wallet.

**Early-buy tax (snipe tax)** — The 98% / 25% / 3% / 0.3% tax on Launchpad buys in seconds 0–3 after launch.

**Edition** — One numbered NFT of a Moment (#1, #2, …). Editions are ERC-721 tokens that show on OpenSea.

**Entitlement** — The coins a collector is owed if a Moment graduates, recorded for the collecting wallet.

**Expire** — Winding down a Moment whose window closed below the threshold. No coin is created; the reserve splits 70% creator / 30% treasury.

**FDV (fully diluted valuation)** — Price × total supply. Moments graduate at a $2,000 FDV; Launchpad coins at about 10× their launch valuation.

**Fee sharing** — Launchpad mode where the creator's fee share goes pro-rata to holders instead of the creator.

**Graduation** — The moment a Launchpad coin or a Moment coin leaves its curve or collect phase and gets a locked liquidity pool.

**Hook** — A Uniswap v4 contract attached to a pool. DyorHQ's hooks charge the Launchpad pool fee and the Moments 1% fee.

**Isolated margin** — Each perps position has its own margin; a loss on one can't drain another. Perpl only offers this.

**Kuru Flow** — A swap aggregator on Monad that routes across Kuru order books and pools.

**Launch fee** — 5 MON, paid when launching a coin.

**Locker** — A contract that owns a liquidity position and has no function to withdraw it. The Launchpad locker also holds the 10% of supply that never enters the pool.

**MON** — Monad's native token. Pays gas on every transaction.

**Monday Trade** — A Monad DEX with concentrated-liquidity spot pools. One of the three swap venues and an optional Launchpad graduation venue.

**One-Click Trading** — A device-generated trading key authorised by your wallet that lets Perpl's keeper forward your orders. Required for TP/SL and trade history.

**Pair asset** — The asset a Launchpad coin is priced in and raises: MON, USDC, AUSD or aBIL.

**Permit2** — Uniswap's shared approval contract. Used for Uniswap v4 swaps and Moment collects.

**Perpl** — The fully on-chain perpetuals order book on Monad that powers the Perps tab.

**Post-only** — A limit order that must add liquidity; it's rejected rather than crossing the book.

**Price impact** — How much your own trade moves a venue's price.

**Reduce-only** — An order that can only shrink an existing position.

**Refund mode** — A Launchpad state the owner can trigger after 7 days of failed graduations: buys close, sells are fee-free.

**Reserve** — 75% of every Moment collect, held until graduation seeds the pool (or expiry splits it).

**Slippage tolerance** — The maximum the price may move against you before a swap or market order cancels.

**Threshold** — The amount a curve or reserve must raise to graduate.

**Vesting** — The schedule on which graduated Moment coins unlock: collectors 60/20/20 over two months, creators 20% then 16% a month over five.

**Watch-only** — Following an address without its key. Read everything, sign nothing.

**WMON** — Wrapped MON, the ERC-20 form of MON. Swap wraps and unwraps 1:1.
