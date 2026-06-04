# Backtest summary · Static Drift Weight

All figures are **ratios or normalized levels** — no dollars, no notional. Exact
test-window values are rounded to ranges by policy (see `_MANIFEST.md`).

## Headline (illustrative placeholders)

| Metric | Value | Note |
|---|---|---|
| CAGR | ~x% | annualized, test window |
| Sharpe | ~1.x | net of modeled costs |
| Max drawdown | −xx% | peak-to-trough |
| Turnover | low | by design (drift, not rebalance) |

## Stress-test verdicts

- **2008 GFC** — *survived.* Drawdown shallower than the broad-equity benchmark;
  bands capped the worst-running positions before the crash deepened.
- **2020 COVID** — *survived.* Faster recovery than benchmark; low turnover meant the
  strategy was not whipsawed by the March round-trip.
- **Generalizable lesson** — letting winners run *with a ceiling* beats both naive
  buy-and-hold (no ceiling) and aggressive rebalancing (no running) in these
  episodes.

## What's withheld

The exact equity series with dates, the parameter set that produced these numbers,
and the live allocation. The verdicts are the deliverable; the reproduction recipe
is not.

> Placeholder draft. Final frozen version is mirrored to
> [backtests-archive](https://github.com/DuiArte/backtests-archive).
