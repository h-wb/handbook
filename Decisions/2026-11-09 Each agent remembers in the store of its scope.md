---
area: "[[Homelab]]"
categories:
  - "[[Decisions]]"
summary: Agents record their conversations into their own scope's memory; private agents only read the general store.
topics:
  - "[[Agent memory]]"
  - "[[Assistant]]"
  - "[[Workshop]]"
created: 2026-11-24T15:30
---

# Each agent remembers in the store of its scope

## Context

Agents learn as they work, and what they record can carry the data they worked on.

## Decision

- Agents record conversations by themselves, each into its own scope's [memory](../Systems/Agent%20memory.md) store.
- Private agents never write to general memory or to the general skills folder: either would carry private facts to the general side. They read general memory with a read-only key.
- Skills the assistant learns stay private until you promote one into git by hand.

## Consequences

- The question a private agent asks the general store is logged there, so it must not carry private detail.
- A memory key does not restrict which namespaces it reads, so separation is by store, not by namespace.
- Keys and stores as deployed: [Models, tools and memory](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/README.md) in home-ops.
