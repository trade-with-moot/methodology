# What is intentionally NOT in this repository

The bot is closed-source by design. This page exists so visitors don't have to guess what's missing.

## Not here, never will be (during the 3-year experiment)

- Source code for the trading bot
- Names of the specific signals the bot reads
- Signal categories, enumerations, or taxonomies at a level that lets the system be reconstructed
- Signal weights, fusion math, or Bayesian priors
- Decision-tree structure beyond the high-level conceptual diagram
- Risk threshold *values* (the *structure* is published in [docs/RISK-MANAGEMENT.md](docs/RISK-MANAGEMENT.md); the values are closed)
- Position sizing formulas
- Stop-loss and exit-rule code
- LLM prompts, prompt templates, prompt shapes, or sanitized prompt samples
- Skill / agent / subagent inventory
- Tool counts or tool names from the underlying engine
- Hyperparameters, calibration data, ranking criteria
- The signal-attribution feedback loop's implementation
- Per-signal attribution tables in monthly receipts

## Why these are closed

The experiment's value depends on the bot being one specific bot, not a recipe anyone can fork.

If the recipe were public, the experiment becomes "watch the open-source bot's clones perform across N hands" — which is a different and much less interesting experiment. The closed parameters are the isolation chamber that makes the receipts mean something. They are the reason a 1,095-day Sharpe number is information rather than noise.

There is also a softer reason. A retail audience reading "we use signal X with weight Y above threshold Z" reliably mistakes the recipe for the system. The recipe is a tiny fraction of what makes a trading system work — the rest is calibration, discipline, regime-awareness, and operational endurance. Publishing the recipe would do more harm than good, because the recipe without the rest is a footgun.

## What IS here

- Conceptual architecture diagram (data → signals → fusion → strategy → risk → execution)
- Decision philosophy (calibrated confidence over prediction; regime-aware allocation; risk budget as hard constraint)
- Risk philosophy and risk *structure* (caps, drawdown protocol, exit-rule taxonomy — without values)
- The publisher-exemption framing (Lowe v. SEC; FINRA Rule 2210)
- Published backtest priors — V3 OOS Sharpes by historical regime; AI sleeve total return vs SPY across five regimes
- The Day-1,095 retrospective contract
- Live performance receipts — see [tradewithmoot.streamlit.app](https://tradewithmoot.streamlit.app)
- The 1,095-day public commitment
- Operational meta-records (governance, transparency-fund accounting, revisions log, incidents log)

## What MIGHT be here at Day 1,095

Day 1,095 (~summer 2029): a full retrospective ships in `retrospective-2029/`. The retrospective will include cumulative P&L, methodology evolution, what worked, what didn't, what's next.

Source code remains closed even then. Methodology details — sanitized prompt samples, per-signal attribution arcs, the fusion calibration story — *may* be opened in the retrospective, based on whether the experiment is still running or being deprecated. The decision will be made at Day 1,095, not earlier and not promised earlier.

## If you think something here is inconsistent with this posture

Open an issue. The closed-source posture is firm, but the documentation is not yet perfect. Methodology corrections are welcome — the receipts shouldn't be ambiguous about what's open and what's closed.
