# Reproducibility

## The bounded reveal

Reproducibility is intentionally bounded for the duration of the experiment.

The bounded reveal is the architecture diagram in [ARCHITECTURE.md](ARCHITECTURE.md). That is the methodology. The rest — signals, weights, fusion math, prompts, threshold values, the agentic layer's internal decomposition — is closed.

The experiment's value depends on the bot being one specific bot, not a recipe anyone can fork. Cloning the recipe and observing receipts for the clone is a different experiment, and a much less interesting one. The closed parameters are the isolation chamber that makes the receipts mean something.

## Why this is *not* a posture of secrecy-for-its-own-sake

A retail audience reading "we use signal X with weight Y above threshold Z" reliably mistakes the recipe for the system. The recipe is a tiny fraction of what makes a trading system work. The rest is calibration against actual outcomes, regime-aware tuning, operational discipline, and 1,095 days of *not* modifying the methodology in response to a bad month.

If the published material were the recipe, the experiment would mostly be teaching people to footgun themselves. The published material is the architecture and the philosophy, because those are the parts a reader can actually take something useful from.

## What a competent engineer can do with what's here

A competent AI engineer reading this repository should be able to **rebuild a similar system** — same architecture, comparable decision framework, similar risk philosophy. Not the same system, because the parameters are closed. A *similar* system.

If you tried this and ended up with a different architecture, that's fine — there's no claim of optimality. If you ended up with no architecture because key information was withheld, that's a documentation bug. File an issue.

## What the receipts make verifiable

The published priors (in `../performance/` and the [README](../README.md)) and the live dashboard at [tradewithmoot.streamlit.app](https://tradewithmoot.streamlit.app) together make the following independently verifiable:

- That the V3 portfolio and the AI sleeve exist and trade real money
- That the structural caps are being enforced live
- That the cumulative P&L, drawdown, and trade history are reported faithfully against the brokerage record
- That the inception dates are what the founding essay says they are

What is *not* independently verifiable — at least until Day 1,095 — is the *attribution* of returns to specific signals or specific decisions. That is the closed parameter set.

## The Day-1,095 contract

Day 1,095 (~summer 2029): a full retrospective ships. It will include cumulative P&L, methodology evolution, what worked, what didn't, what's next. Source code stays closed even then.

Whether the closed parameters get opened in the retrospective is decided at Day 1,095, not earlier. The default is closed; opening is the exception, not the rule.
