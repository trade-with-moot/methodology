# trade-with-moot-methodology

**This documents how Moot thinks. It is not Moot.**

Moot is the autonomous AI agent that wrote the trading pipeline, runs the backtest engine, makes the trading decisions, and ships the operational receipts live via a public Telegram channel. The steward is the anonymous human who hosts Moot's compute, holds the brokerage account, and writes the narrative companion essays. See [who-is-Moot.md](who-is-Moot.md) for the explicit split of who does what — and who can override what.

This repository is the methodology companion — what an outside reader needs to understand the architecture, the philosophy, and the published priors, without the parameters that make Moot one specific agent rather than a recipe.

We are running this experiment to answer one question: **can AI really make money on stocks?** We're going to find out over 1,095 days. The trades go out publicly. The methodology lives here.

## Posture: open architecture, closed parameters

The bot is closed-source by design. So are the signals, the weights, the decision-tree structure, the prompts, the thresholds, and the parameter set. What's published is the conceptual architecture, the philosophy, the risk structure (without values), and the receipts.

See [what-is-NOT-here.md](what-is-NOT-here.md) for the explicit list of what's intentionally absent — and why.

## Phased rollout

| Phase | What | Status |
|---|---|---|
| 1 | V3 portfolio — diversified Sharpe-optimal core | **live 2026-05-22** |
| 1.5 | AI-infrastructure sleeve — 20-name conviction book | **live 2026-05-27** |
| 2 | Day-trade pipeline (intraday) | designed; ships Q3 2026 (date TBD) |
| 3 | Options sleeve | designed; ships Q4 2026 (date TBD) |

Phases 2 and 3 are not live and will not be quietly grafted onto the experiment when they ship — each will have its own founding statement and its own inception clock.

## Backtest priors

Validation results published *before* the live run started — so Day 365 and Day 1,095 readers can compare what the system promised in historical regimes against what it actually delivered with real money. Honest reading: **high-beta in growth, brittle in bear.**

Full tables and caveats: [performance/README.md](performance/README.md).

## Reading order

1. [who-is-Moot.md](who-is-Moot.md) — who Moot is, who the steward is, who can override what (start here)
2. [what-is-NOT-here.md](what-is-NOT-here.md) — the explicit closed-posture statement
3. [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) — conceptual data flow
3. [docs/DECISION-FRAMEWORK.md](docs/DECISION-FRAMEWORK.md) — decision philosophy
4. [docs/RISK-MANAGEMENT.md](docs/RISK-MANAGEMENT.md) — risk structure (philosophy, not values)
5. [docs/REPRODUCIBILITY.md](docs/REPRODUCIBILITY.md) — why reproducibility is intentionally bounded
6. [docs/SIGNALS.md](docs/SIGNALS.md) — the closed-parameter posture on signals
7. [docs/PROMPTS.md](docs/PROMPTS.md) — the closed-parameter posture on prompts
8. [essays/](essays/) — long-form methodology essays (source-of-truth mirror of Substack)
9. [performance/](performance/) — published backtest priors + monthly receipts (once they exist)
10. [meta/](meta/) — operational meta-records and the 1,095-day commitment

## Live surfaces

- **Live dashboard (steward-published):** [tradewithmoot.streamlit.app](https://tradewithmoot.streamlit.app) — Alpaca-backed receipts, positions, equity curve, drawdown
- **Telegram (Moot's voice):** [t.me/trade_with_moot](https://t.me/trade_with_moot) — Moot's real-time pipeline receipts (pre-market plan, stop checks, fills, rebalances). Public, read-only.
- **Substack (steward's voice):** [tradewithmoot.substack.com](https://tradewithmoot.substack.com) — monthly essays + biweekly rebalance notes + Sunday journal
- **Instagram:** [@trade_with_moot](https://instagram.com/trade_with_moot)
- **TikTok:** [@tradewithmoot](https://tiktok.com/@tradewithmoot)
- **X:** [@tradewithmoot](https://x.com/tradewithmoot)
- **YouTube:** [@trade-with-moot](https://youtube.com/@trade-with-moot)
- **BMAC (cost-recovery donations only):** [buymeacoffee.com/tradewithmoot](https://buymeacoffee.com/tradewithmoot)

## Cadence

- **Daily close:** 4pm ET Mon–Fri (closing bell, not 5pm)
- **Friday Rebalance Day:** biweekly Fridays at 10am ET — Moot's cron-fired V3 + AI sleeve rebalance, during market hours, autonomous; same-day steward writeup at daily close
- **Sunday Journal:** weekly long-form retrospective
- **Monthly P&L:** within the first 5 days of the following month
- **Day 1,095** (~summer 2029): full retrospective — P&L, methodology evolution, architecture postmortem, whatever the outcome

## Day-1,095 commitment

Whatever the outcome — good, bad, or neutral — the experiment ships a full public retrospective at Day 1,095. A bad outcome is not a reason to bury the experiment; that would defeat its purpose. The retrospective is the contract.

## License

Documentation is CC-BY-SA-4.0. See [LICENSE](LICENSE). The trading bot's source code is NOT in this repository.

## Contribution

Issues open for questions, corrections, and methodology challenges. Pull requests closed — single-author project. See [CONTRIBUTING.md](CONTRIBUTING.md).

## Not advice

Watching this experiment is not investment advice. The experiment may produce positive returns, may produce negative returns, may produce nothing notable. The whole point is finding out.
