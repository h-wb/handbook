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

It is one of the three things that enforce the privacy rule: a key of the private scope lists trusted models only, so private data cannot reach another model even by mistake. [Every model call goes through it](../Decisions/2026-11-05%20Every%20model%20call%20goes%20through%20one%20gateway.md), with three accepted exceptions; which models are trusted is [a list on the keys](../Decisions/2026-11-09%20Trusted%20models%20decide%20what%20may%20see%20private%20data.md).

## Where its code is

[home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/llm/litellm`. How each client is routed and keyed: [README.md](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/README.md#agent-model-gateway) and [docs/wiring.md](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/docs/wiring.md) there. OpenCode on a workstation and its key: [conf.d/ai/README.md](https://github.com/h-wb/dotfiles/blob/master/conf.d/ai/README.md#opencode-on-a-workstation) in [dotfiles](../Repos/dotfiles.md).

## Related

![[Related.base#Everything]]
