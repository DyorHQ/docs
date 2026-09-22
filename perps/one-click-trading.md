# One-Click Trading

Plain orders go straight to Perpl's exchange contract as on-chain transactions from your wallet. **One-Click Trading** adds a second path: a trading key generated on your iPhone, authorised once by your wallet, that lets Perpl's keeper forward your signed orders. It unlocks several features.

## What it unlocks

| Feature | Without One-Click | With One-Click |
| --- | --- | --- |
| Market and limit orders | ✅ On-chain, signed per order | ✅ Signed by your trading key and forwarded instantly |
| Take Profit / Stop Loss | ❌ "TP/SL: Needs one-click trading, not placed" | ✅ Placed as keeper-managed trigger orders |
| Trade History tab | ❌ "Connect Perpl trading in Profile to see your history." | ✅ (needs the trading key from step 2; forwarding not required) |
| Perps Portfolio history (fills, closed positions, fees) | ❌ | ✅ (same: trading key) |
| Perps figures in your DyorHQ Portfolio | Zeros, with a note | ✅ (same: trading key) |

## Set it up

**Where:** Profile → **Perpl Trading**.

{% hint style="info" %}
📸 **Screenshot here:** Perpl Trading settings screen showing Status, the Connection section and "Enable One-Click Trading". Suggested file: `.gitbook/assets/22-one-click.png`
{% endhint %}

1. Make sure you've made your first deposit (the app needs a Perpl account to enrol against).
2. Tap **Connect Perpl Trading**. The app generates a trading key on your device and asks your wallet to sign Perpl's authorisation message once. The key is stored in the Keychain, device-only, never synced.
3. Tap **Enable One-Click Trading**. This is one on-chain transaction ("Enable one-click trading") that lets Perpl's keeper forward orders signed by your key.
4. **Status** shows **Ready** and the Connection section reads **Ready to trade**. On Profile, the Perpl Trading row now shows **Connected**.

Statuses you'll see along the way: Not connected → Enrolled → Connecting… → Enable one-click → Ready. **Reconnect** and **Try Again** appear if the connection drops; **Disconnect** closes the live session; **Remove API Key** (red) deletes the key from this device so you can enrol a fresh one.

The footer explains it in one line: *"Your trading key is generated on this device and authorized once by your wallet."*

## Good to know

* Orders forwarded by your trading key are signed by that key, not your wallet, so they don't go through the wallet confirmation sheet and aren't gated by **Require Face ID**. The one-time "Enable one-click trading" transaction is sent directly as well.
* Perpl allows **4 trading connections per wallet**, shared with the Perpl web app. If you hit the cap, the app tells you to close other Perpl sessions or wait a minute.
* The connection drops while the app is in the background and reconnects the moment you return, so TP/SL orders placed from the ticket are ready without waiting.
* If Perpl rejects the key (it can happen after a long absence), use **Remove API Key** and connect again.
* Signing out or switching wallets forgets the trading session for that wallet; a fresh sign-in re-binds it.

The **New to Perpl?** section links to Perpl's own web app for people who want a Perpl account outside DyorHQ. In DyorHQ itself, your first AUSD deposit creates the account for you.
