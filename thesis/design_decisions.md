# Design decisions

Each choice as backtested and published, with its trade-off.

| Decision | Choice | Trade-off |
|---|---|---|
| Sleeve weights | Fixed 50/30/20 | Simple and stable. The vector was inherited from an earlier regime-conditional allocator chosen on the same data, a latent selection bias the report discloses. |
| Rebalancing | Monthly, at month-end, back to 50/30/20 | Low turnover and little timing noise. Costs are embedded, and a +50% cost shock lowers the Sharpe ratio¹ only from 1.33 to 1.28. |
| Regime gating | None | One fewer moving part. The gated predecessor (Ensemble #14) had a lower Sharpe ratio¹ (1.26 vs 1.33) and a deeper maximum drawdown (−4.91% vs −3.92%) over the same window. |
| Kill switch | None in the backtest | Nothing to verify or tune; the sleeves' own trend filters do the defending in stress. |
| Instruments | SPY, QQQ, EFA, IEF, GLD, XAUUSD | Liquid ETFs and gold; no single-asset bet. |
| Position sizing | 1% fixed-fractional risk per trade inside the active sleeves | Ratios do not depend on account size; the published returns are unlevered. |

¹ Return ÷ volatility with no risk-free rate subtracted, as published (see the README).
