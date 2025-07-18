#  Wallet Credit Scoring – Aave V2

This project builds a machine learning pipeline that assigns a **credit score (0–1000)** to wallets based on their Aave V2 transaction history. The score reflects responsible vs. risky behavior.

## 🔧 Features Used
- Total transactions
- Deposit & borrow volume (USD)
- Repay-to-borrow ratio
- Liquidation frequency
- Asset diversity
- Avg. time gap between actions

## ⚙️ ML Pipeline
- JSON Flattening
- Feature Engineering
- KMeans Clustering (unsupervised)
- Score Scaling to 0–1000
- `analysis.md` generated with insights

## 📈 Output
- Credit score per wallet
- Score distribution plots
- Cluster visualizations
- Score behavior insights

## ▶️ Run
```bash
python analysis.py
