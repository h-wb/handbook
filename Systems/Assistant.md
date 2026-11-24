---
aliases:
  - Hermes
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
reviewed: 2026-11-24
status:
  - active
summary: "The one you talk to: it runs your routines, works on your tasks and notes, and will come to know what is going on."
created: 2026-11-24T22:00
---

# Assistant

The assistant you reach through [messaging](Messaging.md). Today it is Hermes, running in the cluster with no shell of its own. It is private: it only uses models you trust with private data.

## How it fits

- It reads and writes your [tasks](Tasks.md) and your [notes](Notes.md), and reads your [calendar](Calendar.md), through the [tool gateway](Tool%20gateway.md). It asks before it writes a note.
- It runs on a clock: a morning briefing, a midday nudge, an evening check-in, reminders, a weekly review.
- Coding work is not its job. It hands that to the [workshop](Workshop.md), and shows you the request first.
- It does not read the [warehouse](Warehouse.md) yet. Named read tools over it are planned.

## Where its code is

Its standing instructions and its routines are in [home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/llm/hermes`. A routine is a folder there.

## Related

![[Related.base#Everything]]
