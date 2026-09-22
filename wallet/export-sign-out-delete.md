# Export, Sign Out & Delete Account

## Export your wallet

**Where:** Profile → **Manage Wallets** → **Export Wallet**.

{% hint style="info" %}
📸 **Screenshot here:** Export Wallet screen for an imported wallet, key hidden, with the "Reveal Private Key" button and the warning text. Suggested file: `.gitbook/assets/59-export.png`
{% endhint %}

### Imported wallets

Tap **Reveal Private Key**. Face ID (or Touch ID) is required. The key appears on screen; **Copy Private Key** copies it for 90 seconds, after which it's cleared from the clipboard; **Hide** hides it again. The key is hidden automatically whenever the app leaves the foreground.

The screen's warnings are worth repeating:

* *Anyone with this key has full control of your funds. Never share it. DyorHQ support will never ask for it.*
* *Only enter it into a wallet you trust (MetaMask, Rabby, OKX…). A hardware wallet is safest.*

### Email & Password wallets

Export isn't available for Email & Password wallets in this build; the screen reads *"Key export for this wallet type isn't set up in this build yet."* Your wallet is still fully recoverable: the same email and password recreate it on any iPhone.

### Watch-only

Nothing to export: *"You're watching this address, there's no key to export."*

## Sign out

**Where:** Profile → **Sign Out** (or **Stop Watching**).

| Wallet type | What sign-out does |
| --- | --- |
| **Email & Password** | Deletes the key from this iPhone. Log in again with the same email and password to recreate it. |
| **Imported** | Deletes the key from this iPhone. Import it again from your phrase or key. |
| **Watch-only** | Stops showing that address. |

{% hint style="warning" %}
Signing out removes the wallet key from the device. Make sure you have your password (Email & Password) or your recovery phrase / private key (imported) before you sign out.
{% endhint %}

Signing out also forgets the Perpl trading session and social session for that wallet. Signing back in re-binds them.

## Delete account

**Where:** Profile → **Delete Account** (under Sign Out).

{% hint style="info" %}
📸 **Screenshot here:** Delete Account sheet with the "What is deleted" list, the acknowledgement toggle and the "Type DELETE to confirm" field. Suggested file: `.gitbook/assets/60-delete-account.png`
{% endhint %}

### What is deleted

* Your DyorHQ profile, posts, comments, follows and reactions
* Alerts, watchlists and referral codes
* Notification history and this device's push registration
* Every key, session and cache stored on this device
* For Email & Password wallets: the email link, so the same email and password won't log back into a deleted account

### What is kept

*Transactions, tokens and Moments you created stay on the Monad blockchain, nothing can remove them, and images you published for coins or Moments stay online because those tokens point to them.*

**Your funds are not touched.** They stay in the wallet on-chain. Whether you can reach them again depends on your own backup:

| Wallet type | The app's warning |
| --- | --- |
| Email & Password | *This wallet is recreated from your email and password. Removing it deletes the device copy; keep your email and password, there is no reset, and they are the only way back to the funds.* |
| Imported | *This wallet's private key is removed from this device. Keep its recovery phrase or key somewhere safe; it is the only way back to the funds.* |

### Steps

1. Read the list and turn on **"I understand only my own backup can recover my funds"**.
2. Type **DELETE** in the confirmation field.
3. Tap **Delete Account**. Your wallet signs one message so the server can verify it's you, then everything above is removed. *This cannot be undone.*

Server-side deletion runs first; if it fails nothing on your device is touched, so you can safely retry.
