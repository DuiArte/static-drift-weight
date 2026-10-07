# Thesis · Static Drift-Weight 50/30/20

## What it holds

| Sleeve | Weight | Holds | How it trades | Months active (backtest) |
|---|---:|---|---|---:|
| Buy-the-dip ensemble | 50% | SPY, QQQ, EFA (equal weight) | buys pullbacks while price is above a long trend filter; holds cash otherwise | 85.1% |
| Static blend | 30% | SPY, IEF, GLD (equal weight) | always invested | 100% |
| CRT regime-gold | 20% | gold | three-candle range setup, taken only in the direction of the daily 200-day EMA | 63.4% |

Once a month, at month-end, the three sleeves are reset to 50/30/20.
The backtested specification has no regime gating and no kill switch.

## Why the name

The name is historical. The 50/30/20 vector is the drift-state row of an
earlier regime-conditional allocator (published on the site as Ensemble #14), which moved weight
between the same sleeves as its regime label changed. This strategy keeps that one row
permanently and drops the regime switching. "Drift" names the regime the weights came from,
not a rule that lets the weights drift: they are reset every month.

An earlier version of this repository described the strategy as letting weights drift inside
tolerance bands. That was wrong.

## Why it should work

- **Diversification does most of the work.** On its own, the static SPY / IEF / GLD sleeve
  returned 8.55% a year with a −16.49% maximum drawdown over the same
  window, and at a 30% weight it supplied 51.3% of the blend's return.
- **The active sleeves cut the drawdown.** The buy-the-dip sleeve buys only while price is above
  its trend filter and holds cash otherwise; the gold sleeve trades only with gold's long-term
  trend. Together they take the blend's maximum drawdown to −3.92%, against
  −16.49% for the static sleeve alone.
- **Monthly rebalancing is cheap at this turnover.** Raising fees and slippage by 50% moves the
  Sharpe ratio¹ from 1.33 to 1.28.

## What it is not

**A return amplifier.** CAGR 5.06% against SPY's 14.30% over the same window.
The case for it is a much smaller drawdown (−3.92% against −23.93%) and a
higher return-to-volatility ratio; the report itself calls it a risk-reduction product. Matching SPY's CAGR would take about 2.83× leverage, at a −11.1% maximum drawdown.

**Free of selection.** The 50/30/20 weights were inherited from an allocator whose
weights were chosen with knowledge of the same 2010–2026 data. The report discloses
this as latent selection bias.

¹ Return ÷ volatility with no risk-free rate subtracted, as published (see the README).
