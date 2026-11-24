---
aliases:
  - Memini
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: self
reviewed: 2026-11-24
status:
  - active
summary: What agents remember between sessions, one store per scope.
type:
  - platform
uses:
  - "[[Cluster]]"
created: 2026-11-24T22:00
---

# Agent memory

A store agents write to and recall from across sessions. Today it is Memini, with one store for the general scope and one for the private scope.

## How it fits

It is never the only copy of a plan or a rule. What an agent learns and others need goes on [the board](Board.md) or in a page. Each agent records into its own scope's store, and private agents only read the general one: [decision](../Decisions/2026-11-09%20Each%20agent%20remembers%20in%20the%20store%20of%20its%20scope.md).

## Where its code is

[home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/llm/memini-general` and `memini-private`. Client keys and the names kept from before: [README.md](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/README.md#preserved-identities) there. How each agent is configured to reach its store: [conf.d/ai/README.md](https://github.com/h-wb/dotfiles/blob/master/conf.d/ai/README.md) in [dotfiles](../Repos/dotfiles.md).

## Related

![[Related.base#Everything]]
