---
area: "[[Homelab]]"
categories:
  - "[[Decisions]]"
summary: There is one assistant, in the private scope, with no shell; reads are free, writes ask, and jobs are tools.
topics:
  - "[[Assistant]]"
  - "[[Tool gateway]]"
  - "[[Job runner]]"
  - "[[Workshop]]"
created: 2026-11-24T15:30
---

# One private assistant acts only through named tools

## Context

A general and a private assistant both ran. The [assistant](../Systems/Assistant.md) reads untrusted text, such as mail and clipped web pages, next to private data.

## Decision

- One assistant, private only. The general one was removed: an assistant without private data is what the general workshop already is.
- It has no shell and no repo checkouts. Everything it does is a call to a named tool on its tool gateway, so what exists there is what it can do.
- Reads are free. A write runs after you say yes in the messaging app; a yes covers one call, the rest of the chat, or that tool for good.
- Work on private data that used to be a script becomes a named job with fixed inputs, run by the [job runner](../Systems/Job%20runner.md). The assistant can start it; it cannot improvise a command.
- Left out: the assistant as its own workbench, with a shell and repo checkouts in its pod. It works, but puts a shell next to the agent that reads untrusted mail, and gives up the workshop's app for private work.

## Consequences

- Each overlap with the [workshop](../Systems/Workshop.md) has one owner: personal routines run on the assistant's scheduler; anything that needs a shell or a repo goes to a workshop in the scope of the data it touches, through a [hand-off](2026-11-09%20A%20hand-off%20to%20a%20workshop%20shows%20its%20prompt%20and%20asks.md); repo routines such as dependency sweeps are workshop schedules.
- A scheduled run has nobody to ask, so it can only read and use tools approved for good.
- The job tools are not built yet: on the board.
