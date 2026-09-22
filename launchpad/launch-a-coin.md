# Launch a Coin

**Where:** Launch tab → **New Launch** (the + button). You need a wallet that can sign, at least **5 MON** for the launch fee plus gas, and a little more if you add a developer buy.

{% hint style="info" %}
📸 **Screenshot here:** "Launch a Coin" form with the Image, Coin, Links and Pairing sections visible. Suggested file: `.gitbook/assets/31-launch-form.png`
{% endhint %}

## The form

### Image

Tap **Choose Image** and pick an image from your photos (square looks best). It's resized (max 640 px) and uploaded, and the link is written on-chain as the coin's logo. Uploading needs your DyorHQ Social connection, which happens automatically the first time (one signature, no fee).

### Your Coin (preview)

Once the form is valid, a live card shows your name, $TICKER, a **New** badge and "Pairs with \<PAIR\>".

### Coin

* **Name**: at least 2 characters.
* **Ticker**: 2–10 letters or digits, uppercase.
* **Description**: optional.

### Links

**Website**, **X profile**, **Telegram** (all optional). They're stored on-chain and shown in the coin's About section.

### Pairing

* **Paired with**: MON, USDC, AUSD or aBIL. Only pairs approved on the factory are listed.
* **Graduates on**: **Uniswap v4** (default) or **Monday Trade**. aBIL coins graduate on Monday Trade only, so the picker locks for that pair.
* The footer tells you the live terms: *"Graduates to a locked \<VENUE\> pool once the curve raises \<THRESHOLD\> \<PAIR\>. Launch fee 5 MON."* (for aBIL it adds *"aBIL coins graduate on Monday Trade."*)

### Developer Buy (Optional)

Buy your own coin in the same transaction as the launch. The developer buy is **exempt from the early-buy tax**. Enter an amount in the pair asset; for an ERC-20 pair the confirmation adds an "Approve developer buy" step.

### Advanced

* **Creator tax**: 0% to the maximum (10%) in 0.25% steps. Charged on curve trades and paid to you, or to holders if fee sharing is on.
* **Share fees with holders**: on by default. When on, your share of curve fees, the creator tax and (after a Uniswap v4 graduation) pool fees are split pro-rata among holders instead of going to you.

The creator's fee recipient is the launching wallet.

## Review and launch

Tap **Review**. The confirmation sheet, titled **Launch TICKER**, lists:

| Row | |
| --- | --- |
| Coin | name ($TICKER) |
| Paired with | pair asset |
| Graduation | threshold in the pair asset |
| Graduation venue | Uniswap v4 or Monday Trade |
| Creator tax | your setting |
| Fee sharing | On / Off |
| Launch fee | 5 MON |
| Developer buy | amount, if set |

Tap **Launch TICKER**. The launch fee is paid in MON on top of any developer buy. Right before sending, the app reads the factory's current terms and embeds their hash in the transaction; if DyorHQ changed anything between your review and the transaction landing, it reverts rather than launching on different terms.

When it confirms, tap **View** to open your coin's page. "Launched $TICKER" appears in Recent Activity and in **My Launchpad → Launches**.

{% hint style="info" %}
📸 **Screenshot here:** The "Launch $TICKER" confirmation sheet. Suggested file: `.gitbook/assets/32-launch-confirm.png`
{% endhint %}

## Tips for creators

* **Fee sharing is the community option.** It's on by default. Turn it off only if you want fees paid to your wallet, and say so in the description.
* **Only your launching wallet (including its developer buy) is exempt from the early-buy tax.** Everyone else pays 98% in second 0.
* **Square images look best**, as the form says.
* **Nothing can be edited after launch**: name, ticker, image, links, pair, venue, tax and fee mode are all permanent.

{% hint style="warning" %}
Coins you launch are tradeable by anyone, on a public chain, immediately. You can't pause, delist or recall them.
{% endhint %}
