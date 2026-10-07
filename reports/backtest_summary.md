# Backtest summary · Static Drift-Weight 50/30/20

Published figures from the site's [full report](https://duiarte.github.io/ltcma/bt_static_drift_weights.html) (dated 2026-05-30) and its
backtest catalog. Ratios and percentages only.

## Headline metrics (2010-03-31 → 2026-04-30, 194 months)

| Metric | Value |
|---|---:|
| n_months | 194 (16.2 y) |
| CAGR | 5.06% |
| Vol (ann.) | 3.77% |
| Sharpe (ann.) | 1.33 |
| Sortino (ann.) | 2.68 |
| Max drawdown | −3.92% |
| MAR | 1.28 |
| Hit rate (months > 0) | 62.9% |
| Deflated Sharpe (DSR) | 0.9999 |
| PBO (perturbation, 25) | 0.48 |
| PBO (structural, 6) | 0.33 (vs 0.30 bar) |
| MC P(MaxDD < 10 %) | 0.998 |
| MC CAGR p5/p50/p95 | 3.67 / 5.06 / 6.53% |
| MC MaxDD p5/p50/p95 | −6.49 / −3.98 / −2.62% |
| OOS 2025+ Sharpe | 1.95 (hit 81.3%, 16 mo) |
| Cost-shock (+50 %) | Sharpe 1.28, DSR 0.9999 |

SPY over the same window: CAGR 14.30% · Sharpe ratio¹ 1.00 · maximum drawdown −23.93%.

## Survival bar (12 criteria)

| # | Criterion | Threshold | Observed | Pass |
|---:|---|---|---|:---:|
| 1 | Backtest window | ≥ 10 y | 16.2 y | yes |
| 2 | Max drawdown | < 10% | −3.92% | yes |
| 3 | Deflated Sharpe Ratio | > 0.5 | 0.9999 | yes |
| 4 | PBO | < 0.30 | 0.48 perturbation / 0.33 structural — both above 0.30 bar | no |
| 5 | Walk-forward sign coherence | ≥ 4/6, no fold < −0.5 | 5/5 same-sign, min OS Sharpe 1.01 | yes |
| 6 | Held-out 2025+ Sharpe | ≥ 0.5, sign matches | 1.95, sign matches IS | yes |
| 7 | Beats SPY on ≥ 1 axis | a, b, or c | Axis B: 2.83× lev matches SPY CAGR at −11.1% DD vs SPY −23.9% | yes |
| 8 | Net of costs | embedded | All sleeves include realistic costs | yes |
| 9 | Monte Carlo P(MaxDD < 10 %) | > 0.5 | 0.998 | yes |
| 10 | Cost-shock +50 % → DSR > 0.3 | > 0.3 | DSR 0.9999 | yes |
| 11 | Sizing 1 % fixed-fractional | enforced | Sleeves natively sized | yes |
| 12 | No single-trend dependency | qualitative | 3 sleeves across equity / bonds / gold; no single-asset bet | yes |

11 of 12 pass. The PBO criterion fails on a strict reading; the site publishes the
strategy under a carve-out for blends of correlated sleeves, whose candidate sets are
correlated by construction.

## Sleeve attribution

| Sleeve | Weight | Months active | Annual contribution | Share of CAGR | Sharpe alone¹ |
|---|---:|---:|---:|---:|---:|
| Buy-the-dip ensemble | 50% | 85.1% | 1.54% | 30.7% | 1.23 |
| Static SPY/IEF/GLD | 30% | 100% | 2.57% | 51.3% | 1.03 |
| CRT-Gold daily 3R | 20% | 63.4% | 0.90% | 18.0% | 0.67 |

## Compared with the alternatives

| Strategy | Months | CAGR | Volatility | Sharpe¹ | Max drawdown |
|---|---:|---:|---:|---:|---:|
| Static 50/30/20 (this) | 194 | 5.06% | 3.77% | 1.33 | −3.92% |
| Static 50/30/20 renormalized (alt interpretation) | 194 | 5.34% | 3.97% | 1.33 | −3.92% |
| Ensemble #14 (gated) | 194 | 6.04% | 4.76% | 1.26 | −4.91% |
| Buy-the-dip ensemble alone | 194 | 3.10% | 2.51% | 1.23 | −2.73% |
| Static SPY/IEF/GLD alone | 194 | 8.55% | 8.30% | 1.03 | −16.49% |
| CRT regime-Gold alone | 123 | 6.77% | 10.67% | 0.67 | −16.97% |
| SPY buy & hold | 194 | 14.30% | 14.48% | 1.00 | −23.93% |
| SPY scaled to 10 % DD (0.42× de-levered) | 194 | 6.03% | 6.05% | 1.00 | −10.37% |
| Static 50/30/20 scaled to 10 % DD (2.55× lev) | 194 | 13.06% | 9.62% | 1.33 | −10.00% |

## Walk-forward (5 expanding-window folds)

| Fold | In-sample | Out-of-sample | IS Sharpe¹ | OOS Sharpe¹ | IS CAGR | OOS CAGR | IS max DD | OOS max DD |
|---:|---|---|---:|---:|---:|---:|---:|---:|
| 1 | 2010-03 → 2012-10 | 2012-11 → 2015-06 | 1.48 | 1.01 | 4.64% | 2.68% | −1.68% | −2.56% |
| 2 | 2010-03 → 2015-06 | 2015-07 → 2018-02 | 1.26 | 1.26 | 3.65% | 4.02% | −2.56% | −1.48% |
| 3 | 2010-03 → 2018-02 | 2018-03 → 2020-10 | 1.27 | 1.16 | 3.78% | 5.39% | −2.56% | −2.56% |
| 4 | 2010-03 → 2020-10 | 2020-11 → 2023-06 | 1.21 | 1.25 | 4.18% | 6.04% | −2.56% | −3.92% |
| 5 | 2010-03 → 2023-06 | 2023-07 → 2026-02 | 1.21 | 2.23 | 4.55% | 8.50% | −3.92% | −2.38% |

## Cost shock (+50% fees and slippage)

| Metric | Baseline | +50% costs | Change |
|---|---:|---:|---:|
| CAGR | 5.06% | 4.85% | −0.21 pp |
| Sharpe | 1.33 | 1.28 | −0.05 |
| MaxDD | −3.92% | −4.09% | −0.17 pp |
| DSR | 0.9999 | 0.9999 | −0.00 |

## 2008 crisis test

The main window starts in 2010. A follow-up test in the site's catalog rebuilt the sleeves
over a longer window that includes 2008:

| Measure | Value |
|---|---:|
| Window | 2005-01-03 → 2026-05-26 (21.4 years) |
| Worst monthly drawdown, 2008 crisis window | −9.85% (headroom 15 bp to the 10% bar) |
| Worst daily drawdown, daily CRT-gold proxy | −11.70% |
| Worst daily drawdown, volatility-matched CRT-gold proxy | −9.81% |
| Full-window Sharpe ratio¹ | 1.06 |
| Full-window MAR | 0.51 |
| Passes the 10% bar on monthly data | 3/3 CRT sensitivities |
| Passes the 10% bar on daily data | 2/3 CRT sensitivities |
| Evaluated | 2026-05-31 |

## Gold dependence

Returns are genuinely consistent. Gold does NOT save the strategy. Strip all gold from the strategy: CAGR drops 3bps to 5.03%, Sharpe falls 8bps to 1.25, MaxDD widens from −3.92% to −8.69% but still clears the 10% survival bar, beta to GLD drops from 0.13 to 0.04.

| Variant | CAGR | Sharpe¹ | Max drawdown | Beta to GLD |
|---|---:|---:|---:|---:|
| As published (with gold) | 5.06% | 1.33 | −3.92% | 0.13 |
| No GLD in the static sleeve | 4.94% | 1.30 | −5.35% | 0.04 |
| CRT-gold sleeve removed | 5.18% | 1.31 | −7.33% | 0.15 |
| No gold anywhere | 5.03% | 1.25 | −8.69% | 0.04 |

## Caveats published with the backtest

- The main window starts in 2010; 2008 is covered only by the separate crisis test above.
- The CRT-gold sleeve has trades in 63.4% of months; when it has none, its 20% earns
  nothing (it is treated as zero return, not cash).
- The 50/30/20 weights were chosen with knowledge of the same data (latent
  selection bias).
- The held-out 2025+ Sharpe ratio (1.95) partly reflects strong gold and SPY returns,
  not only the strategy.
- PBO is above the 0.30 bar on both readings.

¹ As published, the Sharpe ratio is the annualised mean monthly return divided by the annualised volatility, with **no risk-free rate subtracted**: 5.06% CAGR at 3.77% volatility reproduces 1.33 on that definition, and SPY's 14.30% at 14.48% reproduces 1.00. It is a return-to-volatility ratio; subtracting Treasury-bill returns would lower both figures.
