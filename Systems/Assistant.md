---
aliases:
  - Hermes
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: self
reviewed: 2026-11-24
status:
  - active
summary: "The one you talk to: it runs your routines, works on your tasks and notes, and will come to know what is going on."
type:
  - agent
uses:
  - "[[Messaging app]]"
  - "[[Tool gateway]]"
  - "[[Model gateway]]"
  - "[[Agent memory]]"
  - "[[Personal tasks]]"
  - "[[Calendar]]"
  - "[[Notes vault]]"
created: 2026-11-24T22:00
---

# Assistant

The assistant you reach through [messaging](Messaging%20app.md). Today it is Hermes, running in the cluster with no shell of its own. It is private: it only uses models you trust with private data.

## How it fits

- It reads and writes your [tasks](Personal%20tasks.md) and your [notes](Notes%20vault.md), and reads your [calendar](Calendar.md), through the [tool gateway](Tool%20gateway.md). It asks before it writes a note.
- It runs on a clock: a morning briefing, a location review, a midday nudge, an evening check-in, reminders, a weekly review. Coming to know the right moment instead is [The aware assistant](../Plans/The%20aware%20assistant.md).
- It has no shell; everything it does is a named tool, and a write asks first: [decision](../Decisions/2026-11-09%20One%20private%20assistant%20acts%20only%20through%20named%20tools.md).
- Coding work is not its job. It hands that to the [workshop](Workshop.md), and shows you the request first: [decision](../Decisions/2026-11-09%20A%20hand-off%20to%20a%20workshop%20shows%20its%20prompt%20and%20asks.md).
- It does not read the [warehouse](Warehouse.md) yet. Named read tools over it are planned.

## Where its code is

Its standing instructions and its routines are in [home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/llm/hermes`. A routine is a folder there. The mechanics are documented there: deployment, Matrix and credentials in [hermes/README.md](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/hermes/README.md), how it connects in [docs/wiring.md](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/docs/wiring.md#the-assistant), how work moves through it in [docs/flows.md](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/docs/flows.md), routines in [README.md](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/README.md#routines).

## Related

![[Related.base#Everything]]
