# Trader Performance vs Market Sentiment

An analysis of how Bitcoin market sentiment relates to trading behavior and outcomes on Hyperliquid.

## Key Insights

- **Fear days are more profitable**: Mean daily PnL on Fear days ($9,388) exceeds Greed days ($5,415) by 73%, though with higher variance.
- **Traders lean long during fear**: The long/short ratio increases from 1.49 on Greed days to 2.48 on Fear days, indicating contrarian positioning.
- **Activity spikes during fear**: Trade frequency rises to 85 trades/day during Fear vs 58 during Greed, suggesting opportunistic behavior.
- **Win rate favors greed, but magnitude favors fear**: Greed days show slightly higher win rates (34% vs 32%), but Fear days produce larger gains per winning trade.

## Strategy Implications

1. **Position sizing should increase during Fear periods** for traders with positive historical expectancy. The data suggests Fear creates favorable asymmetry — higher potential returns despite lower win rates.

2. **Frequent traders should reduce per-trade size on Fear days** to manage cumulative variance. High activity combined with elevated volatility increases drawdown risk.

## Project Structure

```
├── data/
│   ├── fear_greed_index.csv     # Bitcoin Fear/Greed Index (2,644 days)
│   └── historical_data.csv       # Hyperliquid trades (~211,000 records)
├── notebooks/
│   └── analysis.ipynb            # Main analysis notebook
├── outputs/
│   ├── charts/                   # Generated visualizations
│   └── *.csv                     # Processed datasets
├── summary.md                    # Detailed findings
├── requirements.txt
└── README.md
```

## Setup

```bash
pip install -r requirements.txt
jupyter notebook notebooks/analysis.ipynb
```

## Methodology

1. Aligned Fear/Greed Index with trade data at daily granularity
2. Computed per-trader metrics: PnL, win rate, trade frequency, position size, long/short ratio
3. Segmented traders by activity level, position size, and consistency
4. Compared performance and behavior across sentiment conditions

## Data Summary

| Dataset | Records | Date Range |
|---------|---------|------------|
| Fear/Greed Index | 2,644 days | 2018–2025 |
| Hyperliquid Trades | 211,225 | Aligned overlap |
| Final Analysis Set | 530 trader-days | — |

---

See [summary.md](summary.md) for detailed findings and methodology notes.
