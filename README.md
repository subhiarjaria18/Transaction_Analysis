
# 🏦 DeFi Credit Scoring for Aave V2

This project uses machine learning to assign a **credit score (0–1000)** to DeFi wallets based on their historical Aave V2 transaction data.
It aims to quantify trustworthiness of wallets in lending/borrowing protocols using only **on-chain behavior**.

---

## 🚀 Features

- Parses complex user-wallet-level JSON from Aave V2
- Engineers robust behavioral features (deposits, loans, repayments, liquidations, etc.)
- Uses unsupervised ML (KMeans + Silhouette Score) to assign credit bands
- PCA-based cluster visualization of wallets
- Credit score range: **0 (worst) to 1000 (best)**
- Wallet inspection + score querying

---

## 📊 Example Credit Score Logic

| Behavior | Feature | Effect on Score |
|----------|---------|------------------|
| ✅ Frequent repayment | `repay_usd`, `repay_borrow_ratio` | Higher score |
| ✅ Net positive deposits | `net_deposit_usd > 0` | Higher score |
| ⚠️ Many liquidations | `liquidationcall_count`, `liquidation_borrow_ratio` | Lower score |
| ⚠️ Borrow but no repay | `repay_borrow_ratio ≈ 0` | Lower score |
| 💤 Inactive wallet | Low `total_actions` or `active_days` | Neutral/low score |

---

## 🧠 Feature List (Engineered)

| Feature | Description |
|--------|-------------|
| `deposit_count` | # of deposits |
| `deposit_usd` | Total USD value deposited |
| `borrow_count` | # of borrow actions |
| `borrow_usd` | Total borrowed value |
| `repay_count` | # of repayments |
| `repay_usd` | Total repaid USD |
| `redeemunderlying_usd` | Value withdrawn from lending |
| `liquidationcall_count` | # of liquidations suffered |
| `net_deposit_usd` | Deposits - Withdrawals |
| `repay_borrow_ratio` | Responsible borrower ratio |
| `frequency_score` | Intensity of activity (actions/day) |
| `active_days` | # of days wallet was active |

---
