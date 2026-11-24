---
aliases:
  - LiteLLM
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: self
reviewed: 2026-11-24
status:
  - active
summary: The only path to any model. Each client's key lists the models it may use.
type:
  - platform
uses:
  - "[[Cluster]]"
created: 2026-11-24T22:00
---

# Model gateway

Every agent and every tool reaches a model through this gateway and nothing else. Today it is LiteLLM.

## How it fits

It is one of the three things that enforce the privacy rule: a key of the private scope lists trusted models only, so private data cannot reach another model even by mistake.

## Where its code is

[home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/llm/litellm`.

## Related

![[Related.base#Everything]]
