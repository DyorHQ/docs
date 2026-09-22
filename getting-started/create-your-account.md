# Create Your Account

DyorHQ has no "account" in the usual sense. What you create is a **wallet on your iPhone**, and the app is built around it. Three ways in are live today.

| Method | Best for | Can sign transactions? | Where the key lives |
| --- | --- | --- | --- |
| **Email & Password** | New users | Yes | Recreated from your email + password, then stored in the iPhone Keychain |
| **Import a wallet** | People with an existing wallet | Yes | Imported into the iPhone Keychain (this device only) |
| **Watch an address** | Following a wallet without controlling it | No | No key at all |

{% hint style="info" %}
**Coming soon:** Sign in with Apple, Continue with Google, and Passkeys (Face ID, no password, no seed phrase). These are built but switched off until the supporting infrastructure is live. They'll appear on the "Get started" screen under "or continue with" when enabled.
{% endhint %}

{% hint style="info" %}
📸 **Screenshot here:** "Get started" screen. Suggested file: `.gitbook/assets/02-get-started.png`
{% endhint %}

## Email & Password

Tap the **Email & Password** card. The screen has a **Sign Up / Log In** switch at the top.

### How it works

Your wallet is derived deterministically from your email and password (a very slow key-stretching function runs on your phone, then a standard 24-word seed is generated from the result and the wallet's address is derived from it). This means:

* The **same email and password always give the same wallet**, on any iPhone. DyorHQ's backend never holds the key; it only stores a link between your verified email and that wallet address, used to confirm sign-ups and to gate Log In.
* There is **no reset**. A different password produces a different wallet.
* The wallet's security is exactly the strength of your password. Pick a long, unique one.

### Sign Up

1. Enter your **Email**, a **Password** and **Confirm password**.
2. Watch the **Password strength** meter (Weak → Strong). The password must be:
   * At least **12 characters**
   * A mix of **any three** of: uppercase, lowercase, numbers, symbols
   * Not a common password, not built on your email, no repeats or simple sequences ("aaaa", "1234"), and not built on words like "password", "dyorhq", "qwerty", "letmein", "monad", "crypto" or "wallet"
3. Turn on **"I understand my password is the only way back to my wallet"**.
4. Tap **Continue**. We email you a **6-digit code**.
5. Enter the code on the **Verify your email** screen (it submits automatically on the sixth digit). Use **Send a new code** if it didn't arrive, or **Change details** to go back.

Once verified, your wallet is created and you're signed in. The code proves the email is yours, so nobody can register a wallet against an email they don't own.

{% hint style="info" %}
📸 **Screenshot here:** Sign Up form with the password strength meter and the acknowledgement toggle. Suggested file: `.gitbook/assets/05-signup.png`
{% endhint %}

### Log In

Switch to **Log In**, enter the same email and password, tap **Log In**. No code is needed. Your wallet is recreated on this iPhone and, if it matches a verified sign-up, you're in.

If you see "We couldn't find a verified account for that email and password", either the password is different (which means a different wallet) or that email never completed sign-up.

### Forgot password?

Tap **Forgot password?** on the Log In screen, enter your email and a **new** password, then confirm the emailed code.

{% hint style="danger" %}
**Resetting your password creates a new, empty wallet.** Your email is re-linked to the new wallet, but the old wallet's funds still need the old password. If you had funds, keep trying to recall the old password, or use the old wallet's exported key if you saved one.
{% endhint %}

## Import a wallet

Tap **Import a wallet** (or, when watching an address, Profile → Manage Wallets → **Import an Existing Wallet**).

1. Pick **Recovery Phrase** or **Private Key** at the top.
2. Paste or type it. Use **Paste** to read from the clipboard and **Reveal / Hide** to check what you typed.
   * Recovery phrase: 12 or 24 words (15, 18 and 21-word phrases are also accepted), separated by spaces. DyorHQ derives the first account on the standard Ethereum path, the same one MetaMask, Rabby and OKX use.
   * Private key: 64 hex characters, with or without the `0x` prefix.
3. When the input is valid, a **Wallet found** row shows the address. Check it's the one you expect.
4. Tap **Import Wallet**.

The key is stored only on this iPhone, in the Keychain, and never synced to iCloud or sent anywhere. DyorHQ cannot recover it, so keep your original backup. After import the app clears your clipboard if it still holds the secret.

{% hint style="info" %}
📸 **Screenshot here:** Import Wallet screen with "Recovery Phrase / Private Key" switch and the "Wallet found" preview. Suggested file: `.gitbook/assets/06-import.png`
{% endhint %}

## Watch an address

Tap **Watch an address**, paste any 42-character Monad address (starting with `0x`), and tap **Watch**.

You'll see balances, positions, launches and Moments for that address. Nothing can be signed: Send is disabled, every trade button says "Sign in to trade", and there's no key to export. An eye icon in the header reminds you you're watching. To leave, go to Profile → **Stop Watching**.

## Switching wallets

Only one wallet is active at a time. Signing in with a new method replaces the previous one (Profile → **Sign Out** first). See [Export, Sign Out & Delete Account](../wallet/export-sign-out-delete.md) for what sign-out does to each wallet type before you switch.

{% hint style="warning" %}
For **Email & Password** and **imported** wallets, signing out deletes the key from this iPhone. You'll need your password or your backup phrase/key to get back in.
{% endhint %}
