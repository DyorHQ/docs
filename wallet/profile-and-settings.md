# Profile & Settings

**Where:** tap your avatar on Home, or the profile row at the top of the side menu.

{% hint style="info" %}
📸 **Screenshot here:** Profile screen, full length. Suggested file: `.gitbook/assets/56-profile.png`
{% endhint %}

## Header

Your avatar (or initials), your display name or handle, "Signed in with \<method\>" (or "Watching this address"), and your **Address** with a long-press menu: **Copy Address**, **View on Monadscan**.

## Wallet

| Row | Does |
| --- | --- |
| **Receive** | QR + address sheet |
| **Send** | Send sheet (disabled in watch-only) |
| **Recent Activity** | Chronological list of everything you've done |

## Settings

| Row | What's inside |
| --- | --- |
| **DyorHQ Social** | Your handle, display name, bio and photo. See [DyorHQ Social](dyorhq-social.md). |
| **Manage Wallets** | Address, sign-in method, account label, **View on Monadscan**, **Copy Address**, **Export Wallet**, network details (Chain: Monad mainnet, Chain ID: 143, RPC). Watch-only sessions get **Import an Existing Wallet** here. |
| **Security** | **Passkeys** (shows "Passkeys are not enabled in this build." until they ship) and **App Lock**: **Require Face ID** (or Touch ID). Off by default. When on, every wallet transaction that goes through a confirmation sheet asks for Face ID before signing (One-Click perp orders don't). If no biometrics are enrolled the toggle is replaced by "No biometrics enrolled on this device." |
| **Notifications** | Master switch, Swaps & Fills, Price Alerts, Manage Price Alerts. See [Notifications & Price Alerts](notifications-and-price-alerts.md). |
| **Appearance** | **System / Light / Dark**, plus the colour legend: green = Long / Up, red = Short / Down. |
| **Trading Preferences** | **Default Leverage** (1–50, default 2×; each market still caps it) and **Max Slippage** for perps market orders (0.1% / 0.5% / 1% / 2%, default 0.5%). |
| **Perpl Trading** | Connect, enable one-click trading, reconnect, remove API key. See [One-Click Trading](../perps/one-click-trading.md). |
| **Language** | English. "DyorHQ follows your device language. More languages are coming." |
| **Support** | The Get Help screen. |
| **Terms of Use** | Opens dyorhq.fun/terms. |

{% hint style="info" %}
📸 **Screenshot here:** Trading Preferences screen (Default Leverage stepper and Max Slippage picker). Suggested file: `.gitbook/assets/57-trading-prefs.png`
{% endhint %}

## Network

**Chain**: Monad mainnet · **RPC**: the host the app is talking to (rpc.monad.xyz by default).

## Bottom of the screen

**Sign Out** (or **Stop Watching**) and **Delete Account**. See [Export, Sign Out & Delete Account](export-sign-out-delete.md).

The footer reads: *"DyorHQ \<version\> · The RWA HQ for social trading · Self-custodial."*

## Where settings are stored

Appearance, notification toggles, leverage and slippage are kept on your device and mirrored to DyorHQ's backend under your wallet, so a fresh iPhone picks them up after you sign in. Your device's own change always wins over the backup.
