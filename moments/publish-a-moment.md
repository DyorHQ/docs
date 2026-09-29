# 📤 Publish a Moment

**Where:** Moments tab → **Publish** (the + button). You need a wallet that can sign and a little MON for gas. Publishing itself is free.

## The form

### Media

* **Choose Photo or Video** opens your library. The preview shows what you picked; the status line says _"Fingerprint 1a2b3c… goes on-chain."_ once it's processed.
* **Photos** are re-encoded as JPEG (up to 4096 px on the long side). _"This becomes the NFT."_
* **Videos** up to **50 MB** (MP4 or MOV). A cover frame is taken one second in (or at the midpoint of a clip shorter than two seconds); the video plays on OpenSea and the cover frame is the NFT image.
* Or paste an **image link** (`ipfs://` or `https://`) and an optional **video link** instead of uploading.

### Moment

* **Name**: 2–48 characters.
* **Coin ticker**: 2–10 letters or digits, uppercase.
* **Place**: required, up to 64 characters.
* **When**: the date and time it happened (must be in the past).

### Economics

* **Collect price** in USDC (default 1, minimum **0.10**, maximum **1,028.571428**, the price at which a single collect completes the reserve; a higher price is refused).
* **Your allocation**: 0–10% of the 100M coins (default 10).
* **Collect window**: 1 to 30 days.

The footer spells out the live policy, for example: _"Minimum $0.10. About 1029 collects at this price reach the $771.428571 reserve, and the coin graduates at a $2,000 FDV. Up to 10% of the 100M coins is yours, vesting 20% at graduation then 16% a month; anything you leave deepens the pool. Collecting ends at graduation or when the window closes (1 to 30 days)."_

### Preview

Once valid, a summary shows: Collect price · Graduates at ($771.428571 reserve · $2,000 FDV) · Each collect (75% reserve · 20% you · 5% DyorHQ) · Your coins · Collectors + pool (at one price) · NFT royalty 5% · Trading fee after graduation 1.5% (0.2% to you) · Window closes · Liquidity: Locked forever.

## Review and publish

Tap **Review**. The **Publish TICKER** sheet lists the Moment, collect price, graduation terms, your coins and window, then every term your Moment will be published under: **Each collect** (you · DyorHQ · reserve), **Minimum price**, **Most you can keep**, **NFT royalty**, **If it expires**, the **Platform wallet** and **Treasury wallet** (see [Contracts & Addresses](../resources/contracts-and-addresses.md)) and the **Link** its NFT will carry (`dyorhq.fun/moments/c4/<id>`). Last comes how the media is recorded: "photo, fingerprinted · IPFS", "video, fingerprinted · IPFS", "photo, fingerprinted · DyorHQ link, not IPFS" (when IPFS pinning failed and you chose DyorHQ's link) or "link, hashed". Tap **Publish**. It's a single transaction; when it confirms your new Moment page opens.

The terms you review are the terms you get. The transaction carries a fingerprint (hash) of the terms on the sheet, and the Moments contract refuses the publish if its terms changed in the meantime: nothing is published and you review the new terms and publish again. If a change of terms is queued, the form shows what would change and the sheet adds a **Policy change** row.

Publish is unavailable while publishing is paused, or if the app can't verify the contract's terms; the form says which.

## Choosing your settings

* **Price sets the pace.** At $0.10 it takes about 10,286 collects to graduate; at $1 about 1,029; at $10 about 103. A low price is friendlier to casual collectors; a high price graduates with few holders, and the app shows holder counts so buyers can see that.
* **Allocation is your upside, not your income.** Your 20% of every collect is paid regardless. The allocation only becomes coins if the Moment graduates, and it vests over five months.
* **Window.** Short windows create urgency; long windows give a memory time to find its audience. Collecting always ends at graduation whichever comes first.
* **You can't edit anything after publishing.** Check the place, date and spelling.

## Your rights and other people's

Only publish media you have the right to publish. Editions are public, permanent and tradable on OpenSea. Media of other people at private events needs their consent; copyrighted stills and clips can be delisted by marketplaces.
