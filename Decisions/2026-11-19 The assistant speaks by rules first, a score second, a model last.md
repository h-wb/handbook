---
area: "[[Homelab]]"
categories:
  - "[[Decisions]]"
summary: Whether to speak is decided by plain rules, then a score, and a model writes only for a strong candidate.
topics:
  - "[[Assistant]]"
  - "[[Home hub]]"
  - "[[Model gateway]]"
created: 2026-11-24T15:30
---

# The assistant speaks by rules first, a score second, a model last

## Context

A badly timed [assistant](../Systems/Assistant.md) gets muted, and then it is worth nothing. Every wake-up of a model is a paid call on the trusted provider.

## Decision

One loop, started by an event, ends in one message or in silence.

- The gate is plain rules, no model: quiet hours, focus mode, a meeting, driving, twenty minutes of typing, a daily budget, a minimum gap, a back-off after ignored prompts. It cannot be talked out of a rule.
- The score needs no model either: the chance you act now, times how much it matters, minus what interrupting costs now. The chances come from the log of past prompts.
- A model runs only for a strong candidate. It gets the snapshot and the candidate, and writes one message or declines.
- Each step is a question with a fixed answer type (yes or no, one of a list, a probability), so a decision model could answer the same questions later. Jev was looked at and not adopted: it is hosted only, by a company outside the trusted list; nothing says it learns from one person's outcomes; and it is reported weak on dates and arithmetic, so it would never replace the gate.

## Consequences

- Every decision is logged with its snapshot and its outcome, so the log can be replayed through a candidate model to see whether it predicts what you did.
- An open decision model on our own hardware needs a model server that exposes token probabilities, on a machine that stays awake.
- The work: [The aware assistant](../Plans/The%20aware%20assistant.md).
