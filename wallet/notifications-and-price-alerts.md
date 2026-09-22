# Notifications & Price Alerts

DyorHQ keeps you posted with iPhone notifications and an in-app notification center. Everything is generated on your device; there's no server watching your wallet.

## Turning notifications on

The app asks for permission the first time you sign in with a wallet that can sign. You can also flip it under Profile → **Notifications**:

| Setting | Default | What it covers |
| --- | --- | --- |
| **Enable Notifications** | On | Master switch. Turning it on requests iOS permission; if iOS refuses, it flips back off. |
| **Swaps & Fills** | On | Swap complete, and orders sent through One-Click Trading (Order placed / Order filled). Everything else (fills detected on-chain, on-chain orders, sends, deposits, claims, bridges) follows the master switch only. |
| **Price Alerts** | Off | Your price alerts (below) |
| **Manage Price Alerts** | — | Opens the alert list |

If notifications are off in iOS Settings the screen tells you: *"Notifications are turned off for DyorHQ in iOS Settings. Enable them there to receive alerts."* Events are still recorded in the in-app center either way.

## The notification center

Tap the **🔔** on Home. Notifications are grouped by **Today / Yesterday / date**, with an unread dot, filter chips (**All** plus each kind present: **Transactions**, **Swaps**, **Perps**, **Price alerts**, **Moments**, **DyorHQ**) once there's more than one kind, and a menu with **Mark all as read** and **Clear all** (which asks first). Tapping one marks it read and jumps to the relevant tab.

{% hint style="info" %}
📸 **Screenshot here:** Notification center with a few entries and the kind filter chips. Suggested file: `.gitbook/assets/54-notifications.png`
{% endhint %}

Examples of what you'll see:

* **Swap complete**: "Swapped 10 MON → 0.26 USDC"
* **Order filled** / **Order placed**: "Long BTC-PERP"
* **Bridge complete**: "50 USDC bridged from Base to Monad."
* **Price alert: MON**: "MON is now 0.025, above your 0.024 target."

## Price alerts

**Where:** Profile → Notifications → **Manage Price Alerts** → **Add**.

1. Pick a **Token** (any token in your list; MON by default). The sheet shows its **Current price**.
2. Choose **Rises above** or **Falls below**.
3. Enter a **Target** in USD and tap **Add**.

Saving an alert turns on Price Alerts (and the master switch) and requests permission if needed. Alerts are checked every 45 seconds **while the app is open**, fire once, and are then removed. Swipe left on an alert to delete it.

{% hint style="info" %}
📸 **Screenshot here:** "New Alert" sheet with token, Rises above / Falls below and Target. Suggested file: `.gitbook/assets/55-price-alert.png`
{% endhint %}

{% hint style="warning" %}
Because there's no push server yet, price alerts only fire while DyorHQ is running in the foreground. Alerts that would have triggered while the app was closed fire the next time you open it, if the condition still holds.
{% endhint %}

## Synced across devices

Your notification history, alerts and settings are backed up to DyorHQ's backend under your wallet (protected by a session your wallet signs) and restored when you sign in on a new iPhone, as long as the new device doesn't already have its own.
