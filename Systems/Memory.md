---
aliases:
  - Memini
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
reviewed: 2026-11-24
status:
  - active
summary: What agents remember between sessions, one store per scope.
created: 2026-11-24T22:00
---

# Memory

A store agents write to and recall from across sessions. Today it is Memini, with one store for the general scope and one for the private scope.

## How it fits

It is never the only copy of a plan or a rule. What an agent learns and others need goes on [the board](Board.md) or in a page.

## Where its code is

[home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/llm/memini-general` and `memini-private`.

## Related

![[Related.base#Everything]]
