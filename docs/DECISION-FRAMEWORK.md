# Decision Framework

The philosophy behind how Moot makes decisions. Not the enumeration of inputs in priority order — that would expose the structure. The three principles.

## 1. Calibrated confidence over prediction

The system does not try to predict where prices will go. It tries to allocate capital to the positions with the best expected risk-adjusted return *given current information*, knowing the information will be wrong sometimes.

Prediction is the wrong frame because it implies a binary right/wrong outcome per trade. Allocation is the right frame because it implies a distribution of outcomes over many trades, where the question is whether the *process* produces a positive expectancy at the portfolio level over a long enough sample.

A calibrated confidence is one where, across many trades at confidence level X, roughly X percent of them work. The system spends a lot of effort tuning its confidence calibration against actual outcomes. The rest of the decision framework follows from that.

## 2. Regime-aware allocation

What kind of market are we in? The answer to that question dominates which inputs the system listens to and how much. A signal that is gold in a trending market is noise in a chop; a signal that is gold in a low-volatility environment is dangerous in a high-volatility one.

The system reads the regime first, then allocates attention. This is the single biggest reason single-signal trading systems fail — they treat every regime as the same regime, and they get steamrolled by the one in which their input lies.

The regime read is itself probabilistic and updated continuously. The system is wrong about the regime sometimes; the discipline is to act on the current best regime estimate and revisit it, not to anchor on yesterday's read.

## 3. Risk budget as a hard constraint

Risk limits are constants, not preferences. A trade that violates the risk budget does not happen, regardless of how compelling the signal stack looks. Discretionary "this trade is special" overrides are how retail accounts blow up; the framework forbids them by design.

The risk budget is what makes the difference between a system that ships positive risk-adjusted returns over 3 years and a system that ships a great six months followed by a catastrophic seventh. The risk philosophy is published in [RISK-MANAGEMENT.md](RISK-MANAGEMENT.md). The threshold values are closed.

## What the framework forbids

The framework forbids prediction-as-thesis, single-signal trading, position concentration past the cap, correlated positions disguised as diversification, leverage past the cap, "just this once" overrides, and revenge trading after a drawdown. The forbids are the spine of the framework. The permits are everything else.
