# 🔔 Notifications & Price Alerts

DyorHQ keeps you posted with iPhone notifications and an in-app notification center. Everything is generated on your device while DyorHQ is open; there's no server watching your wallet, so price alerts and fills can't reach your lock screen while the app is closed.

## Turning notifications on

The app asks for permission the first time you sign in with a wallet that can sign. You can also flip it under Profile → **Notifications**:

| Setting                  | Default | What it covers                                                                                                                                                                                                       |
| ------------------------ | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Enable Notifications** | On      | Master switch. Turning it on requests iOS permission; if iOS refuses, it flips back off.                                                                                                                             |
| **Swaps & Fills**        | On      | Swap complete, and orders sent through One-Click Trading (Order placed / Order filled). Everything else (fills detected on-chain, on-chain orders, sends, deposits, claims, bridges) follows the master switch only. |
| **Price Alerts**         | Off     | Your price alerts (below)                                                                                                                                                                                            |
| **Manage Price Alerts**  | —       | Opens the alert list                                                                                                                                                                                                 |

If notifications are off in iOS Settings the screen tells you: _"Notifications are turned off for DyorHQ in iOS Settings. Enable them there to receive alerts."_ Events are still recorded in the in-app center either way.

## The notification center

Tap the **🔔** on Home. Notifications are grouped by **Today / Yesterday / date**, with an unread dot, filter chips (**All** plus each kind present: **Transactions**, **Swaps**, **Perps**, **Price alerts**, **Moments**, **DyorHQ**) once there's more than one kind, and a menu with **Mark all as read** and **Clear all** (which asks first). Tapping one marks it read and jumps to the relevant tab.

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

Saving an alert turns on Price Alerts and requests permission if needed. Alerts are checked every 45 seconds while DyorHQ is open, fire once, and are then removed. Don't rely on a price alert to protect a position: set a stop-loss on it. Swipe left on an alert to delete it.
