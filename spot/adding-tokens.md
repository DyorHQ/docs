# Adding Any Monad Token

The Swap picker starts with the curated Monad token list, but any ERC-20 on Monad can be swapped.

## The token picker

Tap either token on the Swap screen to open **Choose a Token**. The search field accepts a **symbol, name or address**.

* Tokens you hold float to the top of the list.
* As you type, matches from the Uniswap and Monday venue lists appear under **More Monad tokens**; after two or more characters Kuru's token directory is searched too.
* Paste a full contract address and the app reads its symbol, name and decimals on-chain and shows it under **By address**. Tap it to use it.

If nothing matches you'll see: _"No token matches. Paste a contract address to add any Monad token."_

## Tokens remembered for you

Any token you pick, launch, buy on the Launchpad, swap into or hold shows up in your wallet's own token list afterwards, in the Swap picker, Home holdings and price alerts. Tokens discovered on-chain in your wallet are added automatically the first time the app scans it.

## Coins from the Launchpad and Moments

* **Graduated Launchpad coins** trade through the pool their curve migrated into (Uniswap v4 or Monday Trade). The **Swap SYM on …** button on the coin's page opens Swap with the pair preselected.
* **Graduated Moment coins** trade on Uniswap v4 against USDC at a 1.5% all-in fee. The **Trade $SYM** button on the Moment page opens Swap with USDC → coin.
* Coins **still on their curve** are bought and sold on the Launch tab, not in Swap.

## A word of caution

DyorHQ shows on-chain metadata as-is. Anyone can deploy a token with any name and symbol. Check the address against an official source before swapping into an unfamiliar token, and watch the price impact figure.
