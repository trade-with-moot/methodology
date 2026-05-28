# Prompts

## The closed-parameter posture

Prompt templates are not published. The shapes, structures, parameter slots, and routing decisions inside the agentic layer are part of the proprietary methodology and stay closed for the experiment's duration.

This is intentional. The recipe is closed; the architecture is open. See [../what-is-NOT-here.md](../what-is-NOT-here.md).

## Why this category specifically

A prompt's structure can carry as much of the methodology as the parameter values do. The default posture during the experiment is to keep the shapes closed alongside the values — publishing the structure and redacting the numbers risks exposing the framework while pretending it doesn't.

The same principle applies to skill / subagent / routing inventories. The list of decision tasks the system routes through LLM reasoning is itself part of the proprietary methodology — it tells you what shape of work the system splits into LLM steps versus deterministic steps.

## What about the architecture diagram?

The architecture diagram in [ARCHITECTURE.md](ARCHITECTURE.md) is a single-page conceptual flow at the layer above prompts. It shows the gates a trade has to pass; it does not show the internal decomposition of the agentic layer, the specific routing decisions, or the prompts themselves. The diagram is the bounded reveal.

## What may be published, and when

The door is intentionally left open for sanitized prompt samples at the operator's discretion — most plausibly as part of the Day-1,095 retrospective, with parameter slots empty and the structure clearly marked as one *instance* of how this work was decomposed. The decision on what to release is made at Day 1,095, not promised earlier and not foreclosed earlier.
