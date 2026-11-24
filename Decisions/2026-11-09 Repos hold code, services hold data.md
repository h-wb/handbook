---
area: "[[Homelab]]"
categories:
  - "[[Decisions]]"
summary: A repo is general unless it holds private data; real data stays in services and the private workshop.
topics:
  - "[[Workshop]]"
  - "[[Assistant]]"
created: 2026-11-24T15:30
---

# Repos hold code, services hold data

## Context

Some repos kept data files and personal notes beside the code, so a general agent opening them could read private data.

## Decision

- Repos hold code; services hold data (the location service, the vault, databases, private memory).
- A repo with no private data in it is general. Any agent may write it in the general [workshop](../Systems/Workshop.md); the private workshop clones it and runs it against the real data.
- A repo that holds private data is private, and is only opened in the private workshop.
- The private workshop's GitHub credential reads general repos and writes only private ones. General credentials cannot read private repos.
- A bug that only shows on real data is reproduced in the private workshop. What part of it goes to the general side is your call.

## Consequences

- Personal notes beside code move to the vault.
- The private workshop has no GitHub credential yet, and that general credentials cannot read private repos is still to verify: both on the board.
- How code and data move: [flow F](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/docs/flows.md#f-code-in-general-data-in-private) in home-ops.
