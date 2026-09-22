# Send, Receive & Transfer

## Receive

**Where:** Home → **Deposit**, or Profile → **Receive**.

The Receive sheet shows a QR code of your address, the full address, and **Copy** / **Share** buttons. The line under it says it all: *"Send MON or any Monad token to this address."* Only send assets on the **Monad** network.

{% hint style="info" %}
📸 **Screenshot here:** Receive sheet. Suggested file: `.gitbook/assets/03-receive.png`
{% endhint %}

## Send

**Where:** Home → **Withdraw**, or Profile → **Send**. In watch-only mode the Profile row is disabled ("Sign in to send from this address."); from Home the sheet opens but can't be confirmed.

1. **To**: paste or type a 42-character Monad address. **Paste** reads the clipboard.
2. **Amount**: pick the token (MON and the curated list; wrapped tokens other than WETH are hidden here) and enter an amount, or tap **Max**. The footer shows *"Available: X SYM"*.
3. Tap **Review**. The **Send SYM** sheet lists **To**, **Amount** and **Network: Monad**.
4. Tap **Send**. With **Require Face ID** on, confirm with Face ID first.

The transfer is recorded as "Sent SYM" in Recent Activity. Gas is paid in MON; no other fee applies.

{% hint style="warning" %}
Sends on Monad are final. Check the address (and that the recipient is on Monad) before you tap Send.
{% endhint %}

{% hint style="info" %}
📸 **Screenshot here:** Send sheet with an address, token picker and amount. Suggested file: `.gitbook/assets/52-send.png`
{% endhint %}

## Transfer (Spot ↔ Perps)

**Where:** Home → **Transfer**.

Moves AUSD between your spot wallet and your Perpl account. **Spot → Perps** deposits (and can swap MON → AUSD for you if you're short); **Perps → Spot** withdraws up to your free balance. The first deposit opens your Perpl account and must be at least 10 AUSD. Full details in [Deposit & Withdraw Collateral](../perps/deposit-and-withdraw.md).

## Address book and copying

Your own address is one tap away everywhere: the **Address** row on Profile and Manage Wallets has **Copy Address** and **View on Monadscan** in its context menu, and the side menu shows the short form under your name.
