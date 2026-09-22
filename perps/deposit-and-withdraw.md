# Deposit & Withdraw Collateral

Perpl uses **AUSD** as collateral. Your collateral lives in your own Perpl account inside the exchange contract, separate from your spot balance. There are two places to move it.

## Option A: the Transfer sheet (Home)

On **Home**, tap **Transfer**. This is the easiest route because it can top up AUSD from MON for you.

{% hint style="info" %}
📸 **Screenshot here:** Transfer sheet, "Spot → Perps" selected, with the "In wallet" and "Free on Perpl" footers. Suggested file: `.gitbook/assets/21-transfer.png`
{% endhint %}

1. Choose **Spot → Perps** (deposit) or **Perps → Spot** (withdraw).
2. Enter an amount in AUSD, or tap **Max**.
3. Read the footer: *In wallet: X AUSD · Y MON* and *Free on Perpl: Z AUSD*.
4. Tap **Review**, check the sheet, then **Transfer** (or **Withdraw**).

**Short on AUSD?** If your wallet doesn't hold enough AUSD but holds MON, the sheet says *"Uses X AUSD from your wallet and swaps ≈ Y MON → AUSD on \<venue\> for the rest."* The swap runs at the best venue with 1% headroom in the same run, then the deposit follows. Your Max Slippage setting applies to that swap.

**First deposit:** the header reads **Open your Perpl account** and the confirmation is titled **Create Trading Account** with an *Account: Opens a new trading account* row. The first deposit must be **at least 10 AUSD**.

## Option B: the Perps screen

Perps → **⋯** menu → **Deposit AUSD** / **Withdraw AUSD** (Withdraw is disabled until you have an account). The **+** next to "Available" on the order ticket also opens Deposit.

* Deposit steps: **Approve AUSD** → **Open Perpl account** (first time) or **Deposit AUSD**.
* Withdraw step: **Withdraw AUSD**. You can withdraw up to your balance minus the margin locked in open positions and orders.

## Messages you might see

| Message | Meaning |
| --- | --- |
| The first deposit opens your Perpl account and must be at least 10 AUSD. (Transfer sheet) / The first deposit must be at least 10 AUSD. (Perps screen) | Increase the amount. |
| Not enough AUSD in your wallet. / Not enough AUSD, and no MON to convert. | Fund your wallet with AUSD (or MON, via Transfer). |
| Not enough MON to cover the difference. / MON on hand does not cover the difference at today's price. | Your MON isn't enough for the top-up swap. |
| No venue can price MON → AUSD right now. / The MON → AUSD price moved; try again. | Retry in a moment. |
| More than your available balance. / More than the balance free on Perpl. | You're trying to withdraw locked margin. Close or reduce positions first. |

## Where to see your balances

* **Home** hero card: **In Use** = your Perpl equity (balance + unrealized P&L). The Spot / Perps split row shows it too.
* **Perps → Assets tab**: Total balance, In use (margin), Available, Unrealized.
* **Perps → ⋯ → Portfolio**: account value, available, unrealized, all-time volume, realized P&L, win rate, trade count and fees (history needs Perpl Trading connected; see [One-Click Trading](one-click-trading.md)).

Deposits and withdrawals are recorded in Recent Activity ("Transferred to Perps" / "Withdrawn to Spot" from the Transfer sheet; "Deposited to Perps" / "Withdrew from Perps" / "Opened trading account" from the Perps screen). They are not counted as trading volume in your Portfolio.
