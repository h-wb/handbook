---
area: "[[Homelab]]"
categories:
  - "[[Decisions]]"
summary: Feeds stay in the warehouse and a thin live path; the assistant reads a small current picture through named tools.
topics:
  - "[[Assistant]]"
  - "[[Warehouse]]"
  - "[[Home hub]]"
  - "[[Job runner]]"
created: 2026-11-24T15:30
---

# The assistant reads a small picture, not every feed

## Context

The trusted models are the weakest part of the setup, and no prompt can hold a life. The [assistant](../Systems/Assistant.md) has to know what is going on without being fed everything.

## Decision

- Raw feeds are turned into a small, current picture underneath the assistant: a snapshot of now, a timeline per day, open loops, notes on your systems. It reads them through named read tools; it never gets a database connection or free-form SQL.
- The feeds belong in the [warehouse](../Systems/Warehouse.md), not in a store of the assistant's own. Its typed tables stay the record.
- On 2026-11-20: real time is a second, thin path beside the record, with the [home hub](../Systems/Home%20hub.md) at its centre. It holds a handful of values and can be thrown away.
- Turning rows into episodes and open loops is jobs on the [job runner](../Systems/Job%20runner.md), on trusted models, with no tools. They read raw text; the assistant reads only their results.

## Consequences

- Two paths: the record answers what happened, within a minute to an hour; the live path answers whether now is a good moment, within seconds.
- Each feed is declared once: who keeps its record, and whether it has a live signal.
- How devices and sources reach the warehouse is decided in miroir, in `docs/miroir/decisions.md` (030, 033, 038, 040, 042).
- The work: [The aware assistant](../Plans/The%20aware%20assistant.md).
