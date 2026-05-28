# Meta

Operational meta-records about the experiment itself — what it IS, what it ISN'T, and the contract that ties it together.

## What this experiment IS

A 1,095-day public test of whether constrained AI agency, applied to a real brokerage account, produces calibrated risk-adjusted returns over a horizon long enough that luck washes out. The trades go out publicly. The methodology goes here. The receipts are at [tradewithmoot.streamlit.app](https://tradewithmoot.streamlit.app).

The horizon — 1,095 days, ~3 years — was chosen because that is roughly the shortest window in which a quantitative claim about an investment strategy stops being noise. Anything shorter is a story; this is meant to be a test.

## What this experiment ISN'T

- It isn't a managed account. The capital is the operator's; followers do not contribute capital, do not receive trade signals, and do not have an account at any entity connected to the experiment.
- It isn't a signals product. There is no subscription, no paid tier, no merch, no course, no sponsorship.
- It isn't financial advice. The publisher posture (Lowe v. SEC; FINRA Rule 2210) is the operating principle.
- It isn't open-source. The bot's code, signals, parameters, and prompts stay closed. The architecture and philosophy are public. See [../what-is-NOT-here.md](../what-is-NOT-here.md).
- It isn't a backtest. Backtest priors are published as a sanity check; the actual experiment is the forward test, live, with real money, on a public dashboard.

## Contents (filled in as the experiment runs)

- `commitment.md` — the public 1,095-day commitment text and operator signature
- `governance.md` — how methodology-change decisions are made (the answer is: rarely, with revision-log entries)
- `transparency-fund.md` — cost-recovery donation accounting, surplus disposition
- `revisions.md` — log of every methodology change during the experiment
- `incidents.md` — operational incidents (outages, data-quality issues, errors)

## Why these meta-records matter

A 1,095-day experiment needs operational records, not just methodology docs. The records answer:

- What changed mid-experiment, and why
- Where operational discipline broke down (transparent record)
- What the actual cost structure was
- What was promised at Day 0 versus what was delivered

These records are the difference between "an experiment ran" and "an experiment with verifiable provenance ran." The Day-1,095 retrospective draws from this directory.

## Status

This directory is mostly scaffolding right now. Commitment text and governance docs land in the first week post-launch. The revisions log appends as changes happen. The incidents log appends when incidents happen.
