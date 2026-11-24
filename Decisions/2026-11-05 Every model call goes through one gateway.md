---
area: "[[Homelab]]"
categories:
  - "[[Decisions]]"
summary: LiteLLM is the only path to a model, each client on its own key, with two accepted exceptions.
topics:
  - "[[Model gateway]]"
  - "[[Workshop]]"
  - "[[Assistant]]"
created: 2026-11-24T15:30
---

# Every model call goes through one gateway

## Context

Agents, workshops and services each held their own provider keys. Which models a client could reach was set in each client, so the privacy rule on models could not be enforced in one place.

## Decision

- One [model gateway](../Systems/Model%20gateway.md), LiteLLM. Each client has its own key, and the key lists the models it may use.
- On 2026-11-09: every model call goes through it, OpenCode's included.
- Accepted exceptions, same day: agents on a workstation call their vendors directly, because the gateway is in-cluster only; and the general workshop holds a key for OpenCode's own hosted models.
- Codex is not a workshop agent. OpenCode reaches the same ChatGPT models through the gateway; Codex would add its own sign-in and a path around it, for the same models on the same quota.

## Consequences

- Who may see private data is a model list on each key: [trusted models](2026-11-09%20Trusted%20models%20decide%20what%20may%20see%20private%20data.md).
- The gateway holds no Anthropic key. Subscriptions are forwarded, so a request without a subscription login fails instead of being billed.
- How each client is routed: [Models, tools and memory](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/README.md#agent-model-gateway) in home-ops.
