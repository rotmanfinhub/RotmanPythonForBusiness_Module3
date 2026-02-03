# Module 3: Statistics

**Python for Business | FinHub | Rotman School of Management**

---

## Overview

This module introduces regression analysis using scikit-learn. You'll calculate correlations, estimate stock betas, and learn a central lesson in finance: **stock returns are hard to predict**.

## What You'll Learn

| Skill | Example |
|-------|--------|
| Calculate correlation | "How do AAPL and MSFT move together?" → 0.63 |
| Run a regression | Predict NVDA returns from market returns |
| Interpret results | "NVDA has beta = 2.0 (moves 2x the market)" |
| Evaluate model fit | R² = 0.58 means market explains 58% of variance |

## Key Concepts

### The Market Model

$$R_{stock} = \alpha + \beta \cdot R_{market} + \epsilon$$

- **Alpha (α):** Stock's return when market is flat
- **Beta (β):** How much the stock moves when the market moves 1%
  - β = 1: Moves with market
  - β > 1: More volatile than market (aggressive)
  - β < 1: Less volatile than market (defensive)

### Correlation

- **+1:** Perfect positive (both go up together)
- **0:** No relationship
- **-1:** Perfect negative (one up, other down)

## The Punchline

When we try to predict tomorrow's return using today's information, R² ≈ 0.4%. The model explains almost nothing.

> **If we can't fit historical data, we have no hope of forecasting future returns.**

This is a central lesson in finance: markets are efficient. Simple patterns get arbitraged away.

## Files

| File | Description |
|------|-------------|
| `module3_statistics.ipynb` | Main notebook with regression analysis and exercises |

## Quick Reference

```python
from sklearn.linear_model import LinearRegression
from sklearn.metrics import r2_score

model = LinearRegression()
model.fit(X, y)
y_pred = model.predict(X)

print(f"Alpha: {model.intercept_}")
print(f"Beta: {model.coef_[0]}")
print(f"R²: {r2_score(y, y_pred)}")
```

## Exercises

1. **Exercise 3.1:** Calculate NVDA's rolling 60-day beta and plot how it changes over time
2. **Exercise 3.2:** Add more features to the prediction model (lagged returns, moving averages)
3. **Exercise 3.3:** Commit your work to GitHub

---

**Next:** Module 4 — Machine Learning
