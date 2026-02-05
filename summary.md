# Trader Behavior & Performance Under Different Sentiment Regimes

## Overview

This analysis examines whether Bitcoin market sentiment (as measured by the Fear & Greed Index) correlates with measurable differences in trading behavior and outcomes on Hyperliquid. The goal is to identify patterns that could inform position sizing, risk controls, or participation decisions.

The analysis uses 211,225 trade records aligned with 2,644 days of sentiment data, yielding 530 trader-day observations across the overlapping period.

---

## Methodology

**Data alignment**: Both datasets were aligned at daily granularity. This is the natural resolution for the Fear/Greed Index and allows direct comparison of aggregate behavior across sentiment conditions.

**Metric construction**: For each trader-day, the following metrics were computed:
- Total PnL (sum of closed positions)
- Win rate (fraction of profitable trades)
- Trade count
- Average position size
- Long/short ratio

**Segmentation**: Traders were grouped by activity level (frequent vs infrequent), position size (large vs small), and consistency (low vs high PnL variance). These segments allow us to test whether sentiment effects differ across trader profiles.

**Statistical validation**: Differences between Fear and Greed conditions were tested using Mann-Whitney U tests, which are appropriate for non-normally distributed financial data.

---

## Findings

### 1. Fear days produce higher average PnL

Traders earned a mean daily PnL of $9,388 on Fear days, compared to $5,415 on Greed days — a 73% difference. The median shows a similar pattern ($230 vs $129), suggesting this is not purely driven by outliers.

However, PnL volatility is also higher on Fear days (standard deviation of $50,957 vs $38,165). This indicates that while the expected return is better, the dispersion of outcomes is wider.

**Interpretation**: Fear periods may present favorable entry points for traders willing to accept higher variance. The contrarian nature of buying during fear appears to pay off on average, but with meaningful risk.

### 2. Traders position aggressively long during fear

The long/short ratio rises from 1.49 on Greed days to 2.48 on Fear days. This is a nearly 70% increase in relative long exposure.

At the same time, trade frequency increases from 58 to 85 trades per day on Fear days. Traders are not only leaning long — they are trading more actively.

**Interpretation**: This behavior is consistent with opportunistic accumulation. Traders appear to view fear as a buying opportunity rather than a signal to reduce exposure. The elevated activity suggests conviction, not just positioning.

### 3. Win rate is slightly lower on fear days, but gains are larger

Win rates are marginally lower during Fear (31.9%) compared to Greed (34.3%). However, this does not translate into worse overall performance.

The higher mean and median PnL on Fear days implies that winning trades are larger, compensating for the lower hit rate. This is consistent with a volatility-driven return profile: when prices move more, correct bets pay better.

**Interpretation**: Evaluating traders purely by win rate would understate their Fear-day performance. Risk-adjusted metrics that account for magnitude are more appropriate.

### 4. Sentiment intensity matters less than category

Correlations between the raw Fear/Greed index value and performance metrics are near zero (PnL: -0.006, win rate: 0.061). The binary Fear/Greed classification reveals patterns that the continuous index obscures.

**Interpretation**: For practical use, sentiment should be treated as a regime indicator (Fear vs Greed) rather than a continuous signal. Threshold-based rules are likely more effective than linear models.

---

## Practical Implications

### Recommendation 1: Increase exposure during Fear

For traders with demonstrated positive expectancy, Fear periods offer a favorable risk/reward tradeoff. The data supports increasing position sizes by 15–20% during Fear, with tighter stops to manage the elevated variance.

This recommendation applies most strongly to infrequent traders, who take fewer but more deliberate positions.

### Recommendation 2: Frequent traders should reduce per-trade size on Fear days

High-frequency traders already increase their activity during Fear (85 vs 58 trades/day). The cumulative risk from this elevated activity, combined with higher per-trade variance, warrants reducing individual position sizes.

A 15–20% reduction in per-trade size would help maintain overall risk exposure while still participating in favorable conditions.

---

## Limitations

- **No leverage data available**: Segmentation by leverage usage was not possible.
- **Daily resolution only**: Intraday patterns may differ and are not captured here.
- **Sentiment index is Bitcoin-focused**: Applied uniformly to all traded assets.
- **Survivorship bias**: Only accounts with recorded trades were included.

---

## Next Steps

1. Test the proposed sizing rules in a backtesting framework with realistic transaction costs.
2. Explore lagged sentiment effects — does today's Fear/Greed predict tomorrow's performance?
3. Incorporate intraday sentiment data when available for higher-frequency signal generation.
