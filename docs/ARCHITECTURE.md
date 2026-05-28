# Architecture

The conceptual data flow. No implementation names, no inventory of internals, no parameter values.

## The diagram

```
┌─────────────────┐
│   market data   │  prices, fundamentals, filings, macro, flow
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│     signals     │  multi-source readings of the market state
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│     fusion      │  combined into one calibrated confidence per ticker
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│    strategy     │  regime-aware allocation across sleeves
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│      risk       │  hard caps, drawdown protocol, correlation guard
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│    execution    │  broker order management, scaled exits, stops
└─────────────────┘
```

## How to read this

Each stage is a gate. A trade only happens when **all six** stages agree. The signal layer can light up green and the risk layer can still veto the trade; the strategy layer can want a position the execution layer can't fill without market impact. The architecture is gated by design — gates are how a rule-based system stays rule-based.

## What the diagram does not show

The names of the signals. The math in the fusion stage. The allocation logic in the strategy stage. The threshold values in the risk stage. The order-routing logic in the execution stage. Those are the closed parameters that make this *one specific bot* rather than a recipe.

For why those stay closed, see [../what-is-NOT-here.md](../what-is-NOT-here.md).

## The reproducibility line

A competent AI engineer reading this diagram should be able to **rebuild a similar system** — not the same system, but one with comparable architectural choices. The diagram is the methodology; the parameters are the experiment.

If you tried this and ended up with no system because key information was withheld, that's a documentation bug. File an issue.
