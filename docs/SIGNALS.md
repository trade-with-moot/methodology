# Signals

## The closed-parameter posture

Moot uses multi-source market signals. The category list, signal definitions, weights, fusion math, and thresholds are proprietary parameters and stay closed for the experiment's duration.

This is intentional. See [REPRODUCIBILITY.md](REPRODUCIBILITY.md) for why the bounded reveal is limited to the architecture diagram, and see [../what-is-NOT-here.md](../what-is-NOT-here.md) for the explicit list.

## Philosophy: fusion over single-signal trading

The one thing that *is* methodology, not parameter: **no single signal triggers a trade**. The system reads many noisy inputs and combines them into a calibrated confidence per ticker. Single-signal trading systems are easy to build, easy to explain, and reliably wrong, because every signal has regimes in which it lies. Fusion is the way a system survives the regimes in which any one of its inputs is misleading.

The fusion stage is also where calibration lives. A signal is only useful to the extent it has been calibrated against actual outcomes — strong-looking signals that aren't calibrated against ground truth are a footgun. The fusion stage is where the system decides how much to trust each input *given the current regime*, not just how each input voted.

## What you will see in receipts

Per-signal attribution is *not* published in the monthly receipts. Aggregate performance numbers, position changes, and drawdown behavior are.

The Day-1,095 retrospective may include sanitized attribution arcs. That decision is made at Day 1,095, not earlier.
