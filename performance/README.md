# Performance

The receipts directory. Published backtest priors live here, monthly P&L reports land here once they exist, and every claim here is reproducible against the live dashboard.

## Live dashboard (canonical)

[tradewithmoot.streamlit.app](https://tradewithmoot.streamlit.app) — Alpaca-backed, real-time. Cumulative P&L, equity curve, drawdown from peak, position book, structural-cap states. If anything in this directory disagrees with the dashboard, **trust the dashboard** and file an issue.

## Published backtest priors

These are the validation results on the table *before* the public run started. The point is to let Day 365 and Day 1,095 readers compare what the system promised in historical regimes to what it actually delivered with real money.

### V3 strategy — out-of-sample Sharpe by historical regime

| Regime | OOS Sharpe |
|---|---|
| 2018 Q4 selloff | 1.78 |
| 2020 COVID + recovery | 4.68 (full window: 6.95) |
| 2022 bear | ~0 |
| 2026 YTD validation | 1.44 |

### AI sleeve — total return vs SPY across 5 regimes

| Regime | AI sleeve | SPY | Δ |
|---|---|---|---|
| 2008 GFC | −32.5% | −38.5% | +6.0% |
| 2018 Q4 | −19.4% | −18.6% | −0.8% |
| 2020 COVID | +12.7% | −3.6% | +16.3% |
| 2022 bear | −34.9% | −18.7% | −16.2% |
| 2025-26 rally | +113.0% | +20.1% | +92.9% |

Honest reading: **high-beta in growth, brittle in bear.** Standard caveats apply — survivorship bias, small-sample limits, and the meta-objection that backtest Sharpes do not transfer to live trading at face value. The priors are a sanity check against "is this random," not a prediction of "this will work."

## Monthly P&L summaries (forward-looking)

Once the first full calendar month closes, monthly summaries land here as `YYYY-MM-summary.md` and contain:

- Cumulative P&L (since inception per sleeve)
- Monthly P&L (both sleeves and total)
- Max drawdown from peak (intra-month)
- Trading Sharpe (running, since inception per sleeve)
- Trade count
- Win rate at the trade level
- Cap utilization (highest exposure observed against each structural cap)

What is *not* in the monthly summary, by design: per-signal attribution, parameter values, prompt revisions. Per-signal attribution may appear in sanitized form at Day 1,095 — see [../what-is-NOT-here.md](../what-is-NOT-here.md).

## Cross-references per monthly summary

Each monthly summary cross-links to:

- The corresponding Substack essay for that month
- A dashboard snapshot at the time of publication (PNG; the dashboard is canonical, the snapshot is the receipt that the report was honest at the time)
- Any [../meta/](../meta/) revisions or incidents that closed during the month

## Inception dates (for the record)

- **V3 portfolio (Phase 1):** 2026-05-22
- **AI-infrastructure sleeve (Phase 1.5):** 2026-05-27
- **Public launch (Day 0):** 2026-05-28

## Status

Backtest priors above are canonical from launch. Monthly P&L summaries land starting June 2026. Day-1,095 retrospective ships ~summer 2029.
