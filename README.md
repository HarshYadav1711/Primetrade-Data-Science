# Crypto Trader Performance vs Market Sentiment Analysis

Analysis of how Bitcoin market sentiment (Fear/Greed) relates to trader behavior and performance on Hyperliquid.

## Overview

This project explores the relationship between the Bitcoin Fear & Greed Index and the trading patterns/performance of Hyperliquid traders. The goal is to uncover actionable patterns that could inform trading strategies or risk controls.

## Project Structure

```
├── data/
│   ├── fear_greed_index.csv     # Bitcoin Fear/Greed Index data
│   └── historical_data.csv       # Hyperliquid trader data
├── notebooks/
│   └── analysis.ipynb            # Main analysis notebook
├── outputs/
│   ├── charts/                   # Generated visualizations
│   ├── processed_analysis_data.csv
│   └── trader_profiles.csv
├── requirements.txt              # Python dependencies
├── README.md                     # This file
└── summary.md                    # Key findings and recommendations
```

## Setup Instructions

### 1. Install Dependencies

```bash
pip install -r requirements.txt
```

### 2. Data Preparation

Place the following files in the `data/` directory:
- `fear_greed_index.csv` - Bitcoin Fear/Greed Index
- `historical_data.csv` - Hyperliquid historical trades

### 3. Run the Analysis

```bash
cd notebooks
jupyter notebook analysis.ipynb
```

Or run via command line:
```bash
jupyter nbconvert --to notebook --execute notebooks/analysis.ipynb
```

## Methodology

1. **Data Preparation**: Load and clean both datasets, handle missing values and duplicates
2. **Timestamp Alignment**: Convert all timestamps to consistent datetime format and align at daily level
3. **Metric Creation**: Compute daily PnL, win rate, trade frequency, position sizes, and long/short ratios per trader
4. **Sentiment Analysis**: Compare performance and behavior between Fear and Greed days
5. **Segmentation**: Categorize traders by frequency, position size, and consistency
6. **Insights**: Generate evidence-backed findings and actionable recommendations

## Key Metrics Analyzed

| Metric | Description |
|--------|-------------|
| Daily PnL | Sum of closed profit/loss per trader per day |
| Win Rate | Percentage of profitable trades |
| Trade Frequency | Number of trades per day |
| Average Trade Size | Mean position size in USD |
| Long/Short Ratio | Ratio of long to short positions |

## Key Findings

See `summary.md` for detailed findings and strategy recommendations.

## Dependencies

- pandas >= 2.0.0
- numpy >= 1.24.0
- matplotlib >= 3.7.0
- seaborn >= 0.12.0
- scipy >= 1.10.0
- jupyter >= 1.0.0

## Author

Data Science Intern - Primetrade.ai
