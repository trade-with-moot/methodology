# Evolution

Moot is designed to learn. The pipeline that fires the 10 am Friday rebalance today is not the pipeline that will fire it on Day 1,095. The 3-year clock is long enough for the methodology itself to change shape — and the experiment's integrity depends on documenting those changes honestly.

## What changes, and how the change gets disclosed

| Type of change | Frequency | Disclosure |
|---|---|---|
| **Inside-the-loop relearning** — walk-forward refits, parameter recalibration on rolling windows, threshold drift adaptation | Continuous, automated | None per change — that's noise, not signal |
| **Methodology shifts** — signals added or retired, risk caps adjusted, prompt or agent topology revised | Occasional, deliberate | Disclosed in the next monthly retrospective |
| **Architecture revisions** — pipeline restructured, sleeve added, sleeve retired | Rare | Standalone postmortem essay shipped before the change goes live |
| **Sleeve retirement or replacement** | Very rare | 30-day forward notice + announcement essay |

The asymmetry of disclosure is deliberate: too much logging is also a way to hide things. We log the changes that are decisions, not the recalibrations that are bookkeeping.

## Lessons already shipped (pre-launch examples)

The methodology repo isn't a manual — it's an honest log of how the experiment is changing shape. A few examples from before public launch that illustrate the kind of lesson the experiment intends to produce. None of these reveal a parameter value; they reveal a *trap*, which is the part worth sharing.

### Signal correlation fix

- **The thing that broke**: an early signal stack treated multiple sentiment signals as independent inputs.
- **What we found**: the correlation matrix across the signals had a dominant first principal component — six of eight signals were sharing the same factor.
- **The fix**: orthogonalized the inputs and dropped the redundant ones. Effective signal count went down; effective signal *quality* went up.
- **The lesson**: signal count is not signal strength. A stack of highly correlated signals is one signal with extra steps.

### Survivorship bias fix

- **The thing that broke**: backtests anchored on the current S&P 500 constituent list.
- **What we found**: companies that fell out of the index over the backtest window had materially worse returns than the survivors. The backtest had effectively trained on the universe that didn't die.
- **The fix**: switched to a point-in-time universe pulled from historical index membership.
- **The lesson**: the universe you backtest on is the universe whose deaths you ignored.

### Slippage realism fix

- **The thing that broke**: backtest assumed a flat 5 basis points of slippage per fill.
- **What we found**: at-market-open fills on smaller-cap names regularly cost 15–25 bps in live paper trading. The 5-bp assumption made marginal trades look profitable that weren't.
- **The fix**: a liquidity filter on the universe + a short post-open delay before entry orders fire + a name-specific slippage estimate based on observed bid-ask spreads.
- **The lesson**: backtest fills assume a liquidity that frequently isn't there at the exact moments you most want it.

## What this log does NOT contain

- Specific parameter values, weights, thresholds
- The current list of signals in the live stack
- The prompt structure of the agentic layer
- Per-trade attribution

That's intentional — see [what-is-NOT-here.md](what-is-NOT-here.md). The log is honest about *that something changed and why*, not about *what the closed-source layer looks like now*.

## Cadence going forward

- **Inside-the-loop**: continuous, automated, no announcement per change
- **Methodology shifts**: bundled into the monthly retrospective at the start of the following month
- **Architecture revisions**: standalone postmortem essay before the change goes live
- **Sleeve retirement / replacement**: 30-day forward notice + announcement essay
- **Day-1,095 retrospective**: full evolution timeline shipped at end-of-experiment

## Why this matters

A 3-year public experiment with a frozen pipeline would be a different experiment — and a less interesting one. The question isn't only *can AI make money on stocks?* but also *can AI learn to make money on stocks better over time, with the receipts honest enough that the learning is visible?* That second question is the one the evolution log is trying to answer.
