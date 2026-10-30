# Quantitative Portfolio Attribution & Markowitz Mean-Variance Optimization

An empirical portfolio performance evaluation and asset allocation optimization model built using Python (`yfinance`, `pandas`, `numpy`, `scipy`).

## Project Overview
This project evaluates a 12-asset global equity portfolio across London Stock Exchange (LSE), NASDAQ, NYSE, and AMEX holdings. It compares risk-adjusted metrics (Sharpe Ratio, Portfolio Beta) against the S&P 500 baseline and implements Markowitz Mean-Variance Optimization to isolate uncompensated concentration risk.

## Quantitative Methodology
- **Log Returns:** $r_t = \ln\left(\frac{P_t}{P_{t-1}}\right)$
- **Annualized Covariance Matrix:** $\Sigma_{annual} = \Sigma_{daily} \times 252$
- **Sharpe Ratio:** $SR = \frac{R_p - R_f}{\sigma_p}$ (Assumed $R_f = 4.0\%$)
- **Optimization Objective:** $\max_w \frac{w^T \mu - R_f}{\sqrt{w^T \Sigma w}} \quad \text{s.t.} \quad \sum w_i = 1, \, w_i \ge 0$

## Key Findings
1. **Overlap Concentration:** High weightings across `VWRA`, `CSPX`, and `VOO` introduced redundant tech exposure without improving diversification.
2. **Beta Dynamics:** Mega-cap semiconductor holdings (`NVDA`, `SMH`) significantly elevated total portfolio variance relative to the benchmark.
