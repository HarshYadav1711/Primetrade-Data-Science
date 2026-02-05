# Analysis Summary: Trader Performance vs Market Sentiment

## Methodology

### Data Sources
1. **Bitcoin Fear & Greed Index**: 2,644 daily observations (2018-2025)
2. **Hyperliquid Trader Data**: ~211,000 trade records across multiple accounts

### Analysis Period
After alignment: **530 trader-day observations** with sentiment data (340 Greed days, 190 Fear days)

### Approach
- Aligned datasets at daily granularity (Fear/Greed Index is daily)
- Created per-trader-per-day metrics: PnL, win rate, trade count, position size, long/short ratio
- Segmented traders into groups (frequent/infrequent, large/small positions, consistent/inconsistent)
- Applied Mann-Whitney U tests for statistical validation

---

## Key Insights

### Insight 1: Counter-Intuitive Fear Day Performance

**Finding**: Traders achieve **higher mean PnL on Fear days** ($9,388 vs $5,415 on Greed days).

| Metric | Fear Days | Greed Days |
|--------|-----------|------------|
| Mean Daily PnL | $9,387.50 | $5,415.24 |
| Median Daily PnL | $229.99 | $128.64 |
| PnL Std Dev | $50,957 | $38,165 |

**Implication**: Fear days, despite negative market sentiment, present profitable opportunities — but with higher variance. This suggests either contrarian strategies work, or volatility during fear creates larger profit potential for skilled traders.

---

### Insight 2: Aggressive Long Bias During Fear

**Finding**: Traders maintain a **higher long/short ratio during Fear (2.48) vs Greed (1.49)**.

| Metric | Fear Days | Greed Days |
|--------|-----------|------------|
| Long/Short Ratio | 2.48 | 1.49 |
| Trade Frequency | 85.2/day | 57.9/day |

**Implication**: This is a contrarian signal — traders are buying the dip during fear periods. The higher trade frequency on Fear days confirms increased activity, possibly opportunistic accumulation.

---

### Insight 3: Win Rate Slightly Favors Greed Days

**Finding**: Win rate is marginally higher during Greed (34.3% vs 31.9%).

**Implication**: While Greed days have better hit rates, the higher PnL on Fear days suggests larger wins compensate for lower win rates. Risk-adjusted return matters more than win rate alone.

---

### Insight 4: Low Correlation Between Sentiment and Outcomes

**Finding**: Sentiment index value shows near-zero correlation with both PnL (-0.006) and win rate (0.061).

**Implication**: The binary Fear/Greed classification reveals patterns that the raw index value obscures. Traders should focus on categorical sentiment states rather than fine-grained index readings.

---

## Strategy Recommendations

### Recommendation 1: Opportunistic Fear Day Participation

**Rule**: Increase position sizing by 10-20% during Fear periods for traders with proven positive expectancy.

**Rationale**: Higher mean and median PnL on Fear days suggests favorable risk/reward. The contrarian long bias already in the data indicates smart money is buying fear.

**Risk Control**: Set tighter stops (e.g., reduce max loss threshold by 15%) to manage the higher variance.

---

### Recommendation 2: Frequency-Based Risk Adjustment

**Rule**: 
- **Frequent traders**: Reduce average position size by 20% during Fear days (already high activity = higher cumulative risk)
- **Infrequent traders**: Slightly increase position sizes on Fear days (fewer bets should be larger when odds favor)

| Trader Type | Fear Day Adjustment | Greed Day Adjustment |
|-------------|--------------------|--------------------|
| Frequent (>85 trades/day) | -20% size, maintain frequency | Normal sizing |
| Infrequent (<58 trades/day) | +15% size, higher selectivity | Normal sizing |

**Rationale**: The data shows frequent traders are already very active during Fear periods (85 trades/day). Position sizing adjustments prevent over-exposure while capturing the favorable conditions.

---

## Limitations

1. **No leverage data** — cannot segment by leverage usage
2. **Daily granularity** — intraday patterns are masked
3. **Bitcoin-focused sentiment** — applied to all traded assets
4. **Survivorship bias** — only accounts with recorded trades analyzed

## Next Steps

1. Implement proposed rules in a backtesting framework
2. Add intraday sentiment data for higher-frequency signals
3. Test lagged effects (does yesterday's sentiment predict today's performance?)
