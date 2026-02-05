# Trader Performance vs Market Sentiment

Analysis of how Bitcoin market sentiment relates to trading behavior and outcomes on Hyperliquid.

---

## Key Insights

- **Fear days produce higher average PnL**: Mean daily PnL on Fear days ($9,388) is 73% higher than Greed days ($5,415). Median values show a consistent pattern.

- **Traders lean long during fear**: Long/short ratio rises from 1.49 to 2.48 on Fear days, indicating contrarian "buy the dip" positioning.

- **Activity increases during fear**: Trade frequency rises to 85/day during Fear vs 58 during Greed, suggesting opportunistic behavior.

- **Win rate is lower, but gains are larger**: Greed days have slightly higher win rates (34% vs 32%), but Fear days produce larger average gains per winning trade.

## Strategy Implications

1. **Increase exposure during Fear** for traders with positive historical expectancy. The data supports 15-20% larger positions, paired with tighter stops to manage elevated variance.

2. **Reduce per-trade size for frequent traders** on Fear days. High activity combined with higher volatility increases cumulative risk; smaller individual positions offset this.

---

## Project Structure

```
├── data/                  # Source datasets
├── notebooks/
│   └── analysis.ipynb     # Main analysis with interpretations
├── outputs/
│   ├── charts/            # Generated visualizations
│   └── *.csv              # Processed data
├── summary.md             # Detailed findings
├── requirements.txt
└── README.md
```

## Setup

```bash
pip install -r requirements.txt
jupyter notebook notebooks/analysis.ipynb
```

## Data Summary

| Dataset | Records | Coverage |
|---------|---------|----------|
| Fear/Greed Index | 2,644 days | 2018–2025 |
| Hyperliquid Trades | 211,225 | — |
| Analysis Set | 530 trader-days | Aligned overlap |

---

See [summary.md](summary.md) for detailed findings and methodology.
