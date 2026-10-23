<sub>**DuiArte** · quantitative research · [methodology](https://github.com/DuiArte/ltcma-methodology) · [strategies](https://github.com/DuiArte/static-drift-weight) · [framework](https://github.com/DuiArte/signallib-framework)</sub>

# Static Drift-Weight 50/30/20

**Three sleeves held at fixed 50/30/20 weights and rebalanced monthly: the thesis, the published backtest, and its caveats.**

![status](https://img.shields.io/badge/status-research-blue) ![license](https://img.shields.io/badge/license-CC--BY--NC--4.0-green) ![backtest](https://img.shields.io/badge/backtest-2010--03%20to%202026--04-lightgrey)

---

**What it is.** 50% buy-the-dip ensemble (SPY, QQQ, EFA), 30% static equal-weight
SPY / IEF / GLD, and 20% CRT regime-gold (gold, traded only in the direction of its
200-day trend). The three weights are reset to 50/30/20 every month;
they do not drift within bands. The name is historical: see
[why the name](thesis/thesis.md#why-the-name).

**Status.** The site's backtest verdict is *Deployable — GFC-tested (cleaner than the now-demoted Ensemble #14)*. This repository reports
that backtest only; it does not report live trading, positions or live results.

## Published backtest

2010-03-31 → 2026-04-30, 194 months. Source: the site's [full report](https://duiarte.github.io/ltcma/bt_static_drift_weights.html), dated
2026-05-30.

| Metric | Static 50/30/20 | SPY, same window |
|---|---:|---:|
| CAGR | 5.06% | 14.30% |
| Volatility (ann.) | 3.77% | 14.48% |
| Sharpe ratio¹ | 1.33 | 1.00 |
| Max drawdown | −3.92% | −23.93% |
| Sortino (ann.) | 2.68 |  |
| MAR | 1.28 |  |
| Hit rate (months > 0) | 62.9% |  |
| Deflated Sharpe (DSR) | 0.9999 |  |
| PBO, structural / perturbation | 0.33 / 0.48 (bar: < 0.30) |  |
| Held-out 2025+ Sharpe ratio¹ | 1.95 (hit 81.3%, 16 mo) |  |

¹ As published, the Sharpe ratio is the annualised mean monthly return divided by the annualised volatility, with **no risk-free rate subtracted**: 5.06% CAGR at 3.77% volatility reproduces 1.33 on that definition, and SPY's 14.30% at 14.48% reproduces 1.00. It is a return-to-volatility ratio; subtracting Treasury-bill returns would lower both figures.

**Not a return amplifier.** CAGR 5.06% against SPY's 14.30%; maximum
drawdown −3.92% against −23.93%. Matching SPY's CAGR would take about 2.83× leverage, at a −11.1% maximum drawdown.

**2008.** The window above starts after the 2008 crisis, and the report says so. A follow-up test
published in the site's backtest catalog (evaluated 2026-05-31) rebuilt the sleeves back to
2005-01-03, with 2008 included: the worst monthly drawdown in the crisis window was
−9.85%, inside the 10% bar (headroom 15 bp). On daily data it was
−11.7% with a daily CRT-gold proxy (outside the 10% bar) and −9.81% with a
volatility-matched proxy (inside the 10% bar).

**Survival bar.** 11 of 12 criteria pass. The criterion that does not, PBO < 0.30,
fails on a strict reading (structural 0.33, perturbation
0.48); the site publishes the strategy under a stated carve-out for
blends of correlated sleeves.

## What's here

- [`thesis/thesis.md`](thesis/thesis.md): what the strategy holds, why the name, why it should
  work, and what it is not.
- [`thesis/design_decisions.md`](thesis/design_decisions.md): each design choice and its
  trade-off.
- [`reports/backtest_summary.md`](reports/backtest_summary.md): the full published figures, from
  the survival bar and sleeve attribution to walk-forward, cost shock, the 2008 test and the
  gold-dependence check.
- [`SOURCE.md`](SOURCE.md): the public site outputs this repository is generated from.
- [`data/oos_replay.csv`](data/oos_replay.csv): the out-of-sample replay series the site publishes (122 rows, 2026-04-30 → 2026-10-22).

## License

[CC BY-NC 4.0](LICENSE). Research, not investment advice.

## Related

Every backtest the site publishes is summarised in
[backtests-archive](https://github.com/DuiArte/backtests-archive); the capital-market
assumptions behind the site are in
[ltcma-methodology](https://github.com/DuiArte/ltcma-methodology).
