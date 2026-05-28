# Risk Management

## Philosophy

Risk management is the boring part. Done right, you don't notice it. Done wrong, the whole experiment dies in one bad week.

Moot's risk discipline is rule-based, not discretionary. The structural categories below are constants; they don't get bent because a trade is special.

The threshold *values* are not published. The *structure* is. The values are part of the closed parameter set — see [../what-is-NOT-here.md](../what-is-NOT-here.md). The current cap states, as enforced live, are visible on the dashboard at [tradewithmoot.streamlit.app](https://tradewithmoot.streamlit.app).

## Structural caps (the categories, not the values)

- **Single-position cap** — no one position dominates the portfolio. Concentration is the #1 way amateur accounts blow up.
- **Sector exposure cap** — no one sector dominates the portfolio. Correlated sector bets disguised as diversification are the #2 way they blow up.
- **Daily portfolio loss limit** — a one-day loss past the limit halts trading until the next session, mechanically.
- **Drawdown protocol** — sizing gets progressively more conservative as the drawdown from peak deepens. The protocol is symmetric — restrictions do not lift on a single good day.
- **Open-position cap** — finite attention. The framework rejects new entries past a count limit, so existing positions don't get under-managed.
- **Correlation guard** — average pairwise correlation across the book has a cap. Highly-correlated positions count against each other.
- **Liquidity cap** — position size cannot exceed a fraction of average daily volume; orders that would move the market do not get placed.

## Exit-rule taxonomy (the categories, not the values)

- **Hard stop-loss** at a fixed percentage below entry — a deterministic floor.
- **Trailing stop** that activates once a position has crossed a threshold gain — preserves upside while locking in.
- **Time-stop** on positions that don't move within the thesis window — reallocates capital to opportunities with current signal strength rather than stale ones.
- **Scaled exits** at progressive targets — partial profit-taking on winners without giving up the upside.

The taxonomy is the methodology. The threshold values are the parameters.

## What "blow up" means and how the framework prevents it

A blow-up is a single-day or single-week loss the portfolio can't recover from in a reasonable time. Most retail blow-ups have one of three causes — concentration, correlated bets disguised as diversification, or leverage without limits. The framework addresses each — single-position cap, correlation guard, leverage cap.

The experiment may still produce a losing month, or a losing quarter, or a losing year. It should not produce a blow-up. If it does, the postmortem goes in [../meta/](../meta/) and the prior cap structure gets revised in the next revisions-log entry.

## Where to see the caps live

Cap states (current exposure vs. limit) are surfaced on the live dashboard at [tradewithmoot.streamlit.app](https://tradewithmoot.streamlit.app). Readers can verify, in real time, that the structural caps described above are being enforced — without seeing the numeric values that make them one specific bot rather than a recipe.
