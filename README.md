<sub>**DuiArte** · quantitative research · [methodology](https://github.com/DuiArte/ltcma-methodology) · [strategies](https://github.com/DuiArte/static-drift-weight) · [framework](https://github.com/DuiArte/signallib-framework)</sub>

# Static Drift Weight

**A deployed allocation strategy that lets winners run within disciplined bands — the thesis and the stress-tested results, without the live weights.**

![status](https://img.shields.io/badge/status-active-blue) ![license](https://img.shields.io/badge/license-CC--BY--NC--4.0-green) ![updated](https://img.shields.io/badge/updated-2026--06-lightgrey)

---

This repository explains the economic rationale behind *static drift weighting* and
publishes a summary of how it holds up under stress. It demonstrates that the
strategy exists and survives — it does not publish the live weight vector, the
notional, or the parameters that would let it be reproduced.

## What's here

- **`thesis/thesis.md`** — the economic rationale: why static drift weighting, and
  what it's designed to capture.
- **`thesis/design_decisions.md`** — the key choices and their trade-offs.
- **`reports/backtest_summary.md`** — headline statistics (as ratios) and the GFC /
  COVID stress-test verdicts.
- **`data/sample_equity_curve.csv`** — an equity curve indexed to 100 (no real
  notional).

## What's deliberately *not* here

The live weight vector, real AUM / notional, the rebalancing thresholds, and the
parameter values that were searched. You learn that the strategy is real and
stress-resilient — not how to clone its current allocation. See
[`_MANIFEST.md`](_MANIFEST.md).

## Headline (illustrative until reviewed)

| Metric | Value |
|---|---|
| Sharpe (test window) | ~1.x |
| Max drawdown | −xx% |
| 2008 GFC verdict | survived, shallower DD than benchmark |
| 2020 COVID verdict | survived, faster recovery than benchmark |

## License

[CC BY-NC 4.0](LICENSE).

## Related

Backtest evidence is archived in
[backtests-archive](https://github.com/DuiArte/backtests-archive); the signal
plumbing is in [signallib-framework](https://github.com/DuiArte/signallib-framework).
