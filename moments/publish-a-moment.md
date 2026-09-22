# Publish a Moment

**Where:** Moments tab → **Publish** (the + button). You need a wallet that can sign and a little MON for gas. Publishing itself is free.

{% hint style="info" %}
📸 **Screenshot here:** "Publish a Moment" form with a photo chosen and the Media, Moment and Economics sections. Suggested file: `.gitbook/assets/41-publish.png`
{% endhint %}

## The form

### Media

* **Choose Photo or Video** opens your library. The preview shows what you picked; the status line says *"Fingerprint 1a2b3c… goes on-chain."* once it's processed.
* **Photos** are re-encoded as JPEG (up to 4096 px on the long side). *"This becomes the NFT."*
* **Videos** up to **50 MB** (MP4 or MOV). A cover frame is taken one second in (or at the midpoint of a clip shorter than two seconds); the video plays on OpenSea and the cover frame is the NFT image.
* Or paste an **image link** (`ipfs://` or `https://`) and an optional **video link** instead of uploading.

What happens to your file: it's uploaded to DyorHQ's media storage, pinned to **IPFS**, and the `ipfs://` link is written on-chain as the Moment's media pointer (the app falls back to the direct link if pinning is unavailable). The file's keccak-256 fingerprint is stored on-chain too, so anyone can verify the media hasn't been swapped. Uploading requires your DyorHQ Social connection, which connects automatically with one signature.

### Moment

* **Name**: 2–48 characters.
* **Coin ticker**: 2–10 letters or digits, uppercase.
* **Place**: required, up to 64 characters.
* **When**: the date and time it happened (must be in the past).

### Economics

* **Collect price** in USDC (default 1, minimum **0.10**).
* **Your allocation**: 0–10% of the 100M coins (default 10).
* **Collect window**: 1 to 30 days.

The footer spells out the live policy, for example: *"Minimum $0.10. About 1029 collects at this price reach the $771.428571 reserve, and the coin graduates at a $2,000 FDV. Up to 10% of the 100M coins is yours, vesting 20% at graduation then 16% a month; anything you leave deepens the pool. Collecting ends at graduation or when the window closes (1 to 30 days)."*

### Preview

Once valid, a summary shows: Collect price · Graduates at ($771.428571 reserve · $2,000 FDV) · Each collect (75% reserve · 20% you · 5% DyorHQ) · Your coins · Collectors + pool (at one price) · NFT royalty 5% · Trading fee after graduation 1.5% (0.2% to you) · Window closes · Liquidity: Locked forever.

## Review and publish

Tap **Review**. The **Publish TICKER** sheet lists the Moment, collect price, graduation terms, your coins, window and how the media is recorded ("photo, fingerprinted" / "video, fingerprinted" / "link, hashed"). Tap **Publish**. It's a single transaction; when it confirms your new Moment page opens.

{% hint style="info" %}
📸 **Screenshot here:** The "Publish TICKER" confirmation sheet. Suggested file: `.gitbook/assets/42-publish-confirm.png`
{% endhint %}

## Choosing your settings

* **Price sets the pace.** At $0.10 it takes about 10,286 collects to graduate; at $1 about 1,029; at $10 about 103. A low price is friendlier to casual collectors; a high price graduates with few holders, and the app shows holder counts so buyers can see that.
* **Allocation is your upside, not your income.** Your 20% of every collect is paid regardless. The allocation only becomes coins if the Moment graduates, and it vests over five months.
* **Window.** Short windows create urgency; long windows give a memory time to find its audience. Collecting always ends at graduation whichever comes first.
* **You can't edit anything after publishing.** Check the place, date and spelling.

## Your rights and other people's

Only publish media you have the right to publish. Editions are public, permanent and tradable on OpenSea. Media of other people at private events needs their consent; copyrighted stills and clips can be delisted by marketplaces.
