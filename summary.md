# Trader Behavior Under Fear vs Greed Sentiment

## Objective

Determine whether Bitcoin market sentiment (Fear/Greed Index) correlates with measurable differences in trading behavior and outcomes on Hyperliquid, and identify patterns that could inform position sizing or risk controls.

---

## Data Overview

| Dataset | Records | Notes |
|---------|---------|-------|
| Fear/Greed Index | 2,644 days | Binary classification (Fear/Greed) + numeric value (0-100) |
| Hyperliquid Trades | 211,225 | Includes account, side, size, PnL |
| Final Analysis Set | 530 trader-days | Aligned overlap between datasets |

Datasets were aligned at daily granularity to match the Fear/Greed publication frequency. Metrics computed per trader per day: total PnL, win rate, trade count, average position size, and long/short ratio.

---

## Key Findings

### 1. Fear days produce higher average returns

Mean daily PnL on Fear days is $9,388 compared to $5,415 on Greed days — a 73% difference. The median shows a similar pattern ($230 vs $129), indicating this is not driven by outliers alone.

PnL volatility is also higher on Fear days (std dev $50,957 vs $38,165), so the favorable expected return comes with wider dispersion.

### 2. Traders position aggressively long during fear

The long/short ratio increases from 1.49 on Greed days to 2.48 on Fear days — a 66% shift toward long positions. Trade frequency also rises from 58 to 85 trades per day.

This suggests opportunistic accumulation during fear, consistent with "buying the dip" behavior.

### 3. Win rate is lower on fear days, but gains are larger

Win rates are marginally lower during Fear (31.9% vs 34.3%), yet overall PnL is higher. The magnitude of winning trades compensates for the lower hit rate.

### 4. Sentiment intensity adds little beyond the binary classification

Correlations between the raw index value (0-100) and outcomes are near zero. The binary Fear/Greed distinction captures the relevant signal; finer granularity does not improve predictability.

---

## Interpretation

The data suggests that Fear periods create favorable conditions for traders willing to accept higher variance. The contrarian behavior visible in the data — leaning long and trading more actively during fear — appears to pay off on average.

However, the elevated volatility during Fear means that position sizing and risk controls become more important, not less. A trader who increases exposure during Fear without adjusting stops or per-trade limits may experience larger drawdowns despite favorable expected returns.

The lack of correlation between the numeric index value and outcomes implies that sentiment should be treated as a regime indicator rather than a continuous signal. Threshold-based rules (e.g., "Fear vs Greed") are likely more practical than models that incorporate the full index range.

---

## Practical Implications

**1. Increase position sizing during Fear for traders with positive expectancy.**

The data supports a 15-20% increase in position size during Fear periods, paired with tighter stop losses to manage the elevated variance. This recommendation applies most strongly to infrequent traders who take deliberate, higher-conviction positions.

**2. Frequent traders should reduce per-trade size on Fear days.**

Traders who are already highly active (>85 trades/day during Fear) face cumulative variance risk. Reducing per-trade size by 15-20% helps maintain overall exposure while limiting single-trade drawdown. Activity level can remain elevated; per-trade risk should not.

---

## Limitations

- No leverage data available; leverage-based segmentation was not possible
- Daily resolution only; intraday patterns may differ
- Sentiment index is Bitcoin-focused but applied to all traded assets
- Survivorship bias: only accounts with recorded trades are included
