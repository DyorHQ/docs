# Collect a Moment

Collecting mints you an NFT edition of the Moment and, if the Moment ever graduates, a claim on its coin.

**Where:** Moments tab → tap a Moment → **Collect** section (visible while the Moment is Collecting). You need **USDC** for the price and **MON** for gas.

{% hint style="info" %}
📸 **Screenshot here:** A Moment page with the Collect section: Editions stepper, You pay / You get rows and the "Collect N Editions" button. Suggested file: `.gitbook/assets/43-collect.png`
{% endhint %}

## The Moment page

* **Header**: the media, name, $TICKER, state badge ("Collecting · 2d 3h left"), place and date. The share button (top right) shares the Moment's OpenSea page (edition #1).
* **Progress**: the Graduation gauge, **Reserve** ($x of $771.428571), **Still needed** ($x · about N collects) and **Window closes**.
* **Stats**: Per edition, Graduation FDV, Editions, Collects (or Coin price, FDV and Since open after graduation).
* **Collect** (below).
* **Your Position**: your edition numbers with **View #N on OpenSea** links, coins owed, and after graduation claimable / claimed / vested.
* **Holders**: edition holders and the largest holder; after graduation also coin holders, the top wallet's share and how much sits in the pool.
* **About this Moment**: creator, published date, window, split, allocation, royalty, supply, minted so far, media hash, **View on OpenSea**, **Open media**, and the coin and NFT contract addresses.

## Collect

1. Set **Editions** (1 to 20).
2. Check **You pay** (price × editions, in USDC) and **You get** ("N editions · X $TICKER" coins owed).
3. Check **Your USDC**; it turns red if you don't have enough.
4. Tap **Collect N Editions**.
5. The **Collect TICKER** sheet lists Moment, Editions, You pay, Coins owed and "Your NFT: On OpenSea once it settles". Tap **Collect**.

Steps: **Approve USDC for Permit2** (once, skipped afterwards) then the collect itself, which carries a signed Permit2 transfer for up to price × editions (valid 30 minutes). The contract pulls only the quoted USDC.

Afterwards your editions show under **Your Position**, on OpenSea, on **Home → My Holdings → Moments**, and in **My Moments**.

## The collect that graduates the Moment

If your collect would push the reserve over the threshold, the button changes to **Collect and Graduate** and a notice explains: *"This collect completes the Moment: it takes only what the reserve still needs ($x for N editions) and graduates the coin in the same transaction."* You're charged only the accepted amount, you get the corresponding editions, and the pool is created in your transaction (it needs a bit more gas than a normal collect). The confirmation shows "Graduates: Yes, in this transaction".

## What each edition is

* A transferable **ERC-721 NFT** in a per-Moment collection, numbered in mint order. Metadata (image or video, place, date, creator, rank) is served on-chain.
* It **renders on OpenSea** with no extra step and can be listed or sold there. A 5% creator royalty is set on-chain.
* It carries a **coin entitlement** recorded for the wallet that collected. That entitlement is what vests if the Moment graduates. Selling the NFT does not move the entitlement; it stays with the collecting wallet.

## Messages you might see

| Message | Meaning |
| --- | --- |
| The collect window has closed. | The deadline passed; the Moment may be expired or wound down. |
| This Moment is no longer collecting. | Graduated, expired or pending graduation. |
| Choose between 1 and 20 editions. | Batch limit. |
| Sign in to collect. / You are watching this address. Sign in to collect. | Watch-only or signed out. |
| Sign in with a wallet that can sign to collect. | The active wallet type can't sign the Permit2 message. |

## Before you collect

Every collect is paid in USDC and split 75% reserve, 20% creator, 5% DyorHQ, as the footer under the button says. The coin, if it ever exists, is a financial asset that can lose value, may be taxable when sold, and starts with a pool only as deep as the reserve. Check the **Holders** section: a Moment collected by one wallet reads very differently from one collected by hundreds.
