# Monte Carlo Portfolio Simulation

A Monte Carlo simulation that estimates the probability of an investment
portfolio reaching a target value over a multi-year horizon, and quantifies
the full range of possible outcomes. Built in Python.

Runs 10,000 simulated paths, reports the probability of hitting a target, and
produces P10/P50/P90 outcome bands, a probability cone, and a terminal-value
distribution.

## Example

Starting with $100,000, an expected return of 7%/yr, volatility of 15%/yr,
over 10 years, targeting $200,000:

| Metric | Value |
|---|---|
| Probability of reaching $200k | 40% |
| P10 (pessimistic) | $102,000 |
| P50 (median) | $177,000 |
| P90 (optimistic) | $317,000 |

## Method

- **10,000 simulated paths** of annual portfolio growth.
- **Lognormal return model** - growth factors are always positive, so portfolio
  value can never go negative, and multiplicative compounding is handled
  correctly. This is the standard model for asset prices.
- **Probability of attainment** — the fraction of paths finishing at or above
  the target.
- **Percentile bands (P10 / P50 / P90)** describing the spread of outcomes.
- **Reproducible** via a fixed random seed.

The outcome distribution is right-skewed: the mean sits above the median because
a few high-growth paths pull the average up, typical of compounding returns.

## Tech
Python, NumPy, Matplotlib. (Excel export and an interactive version planned.)

Built by Naumenko Analytics LLC
