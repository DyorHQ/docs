# DyorHQ Social

DyorHQ Social is your public identity inside the app: a handle, display name, bio and photo attached to your wallet. It's what other people see on your Launchpad and Moments profiles, and it's what lets you upload images for coins and Moments.

**Where:** Profile → **DyorHQ Social**.

{% hint style="info" %}
📸 **Screenshot here:** DyorHQ Social screen with avatar, handle, display name and bio filled in. Suggested file: `.gitbook/assets/58-social.png`
{% endhint %}

## Connecting

Any wallet that can sign connects automatically the first time you sign in: the app asks your wallet to sign a short message (no transaction, no fee) and that signature opens a session with DyorHQ's backend. If you ever see **Connect to DyorHQ Social**, tap it; the footer explains: *"You'll sign a short message with your wallet to prove it's you — no transaction, no fees."*

Watch-only sessions can't connect: *"Sign in with a wallet to join DyorHQ social."*

## Your profile

| Field | Rule |
| --- | --- |
| **Photo** | Add Photo / Change Photo. A square image works best; it's resized to 512 px. |
| **Handle** (@) | Lowercase letters, numbers and underscores, 3–20 characters. |
| **Display name** | Free text. |
| **Bio** | A few lines. |

Tap **Save Profile**. "Saved to DyorHQ." confirms it.

## Where it shows

* Your name and avatar on **Profile**, the **side menu**, **My Launchpad** and **My Moments**.
* The "@handle" next to **DyorHQ Social** in Settings.
* Creator identity on the coins and Moments you publish.

## What the backend stores

Your profile, sign-in sessions (for analytics), activity log, notification history, price alerts and settings, all keyed by your wallet address and protected so only a session signed by your wallet can read or write them. Media you publish for coins and Moments is stored publicly because the tokens on-chain point to it. See [Export, Sign Out & Delete Account](export-sign-out-delete.md) for what deletion removes.
