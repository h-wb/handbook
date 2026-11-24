---
area: "[[Homelab]]"
categories:
  - "[[Decisions]]"
summary: The privacy rule is about which models are trusted, not cloud against local, and three layers enforce it.
topics:
  - "[[Model gateway]]"
  - "[[Tool gateway]]"
  - "[[Agent memory]]"
  - "[[Assistant]]"
  - "[[Workshop]]"
created: 2026-11-24T15:30
---

# Trusted models decide what may see private data

## Context

The first split was cloud against local. What decides the risk is which provider sees the data, and a provider can be trusted whether it runs here or not.

## Decision

- [The one rule](../README.md#the-one-rule) is about trusted models. Which models are trusted is a list on the keys, not part of the design. On the day of this decision: the models served by Mistral's API, GLM models included, and local models; Claude and ChatGPT worked on general data only. The list as it stands is in home-ops, in [Models, tools and memory](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/README.md), and nowhere else.
- Home Assistant is private.
- "Scope" is the only term, not tier or segment.
- Three layers enforce it, and nothing else is relied on: each client's model key lists its models, with trusted ones only on a private key; one [tool gateway](../Systems/Tool%20gateway.md) per scope, with a network rule that admits only that scope; one [memory store](../Systems/Agent%20memory.md) per scope.
- The split is about which models see the data, not about limiting tools: private agents get the whole catalogue.

## Consequences

- Moving a model from one list to the other is one change, to the model lists on the keys.
- Pasted text is not covered, and an administrator of the general scope can still reach private workloads. The boundary guards normal work, not an administrator.
- The lists and the layers as deployed: [Models, tools and memory](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/README.md) in home-ops.
