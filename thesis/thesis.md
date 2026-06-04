# Thesis · Static Drift Weight

## The idea

Most allocation schemes rebalance aggressively back to fixed targets, which
mechanically sells winners and buys losers. *Static drift weighting* deliberately
lets allocations **drift** within disciplined bands, capturing trend and momentum at
the portfolio level, and only intervenes when drift breaches a band. The "static"
part is the band structure; the "drift" part is the controlled letting-run.

## Why it should work

- **Momentum is persistent** across asset classes over medium horizons; constant
  rebalancing fights it.
- **Turnover is costly**; drifting reduces trade frequency and cost drag.
- **Tail discipline**: bands cap how far any asset can run, so the portfolio keeps a
  risk ceiling even while letting winners breathe.

The economic claim is published in full. What's withheld is the band geometry and the
live weights — i.e. *where* the discipline sits, which is the operating parameter.

## What this repo proves

That the strategy is principled, deployed, and stress-resilient (see
[`../reports/backtest_summary.md`](../reports/backtest_summary.md)). It does **not**
give a reader the current allocation.

> Placeholder draft — economic rationale stands; numbers are illustrative.
