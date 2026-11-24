---
area: "[[Homelab]]"
categories:
  - "[[Decisions]]"
summary: The assistant starts a workshop agent only after you approve the exact prompt, one call at a time.
topics:
  - "[[Assistant]]"
  - "[[Workshop]]"
created: 2026-11-24T15:30
---

# A hand-off to a workshop shows its prompt and asks

## Context

Handing a coding request from the [assistant](../Systems/Assistant.md) to the general [workshop](../Systems/Workshop.md) is the one place private data could reach a model outside the trusted set.

## Decision

- The assistant drafts the prompt, shows it exactly, and starts the agent only after your yes. It is never automatic.
- On 2026-11-10: the assistant starts agents in either workshop, and every start asks, one call at a time, with no yes for good. Into the private workshop nothing crosses a boundary, but it starts an agent with a shell.
- Results coming back need no guard. You can also skip the assistant and start the agent yourself in the workshop's app.

## Consequences

- One tap for every prompt sent through the assistant.
- How it is wired, and what the approval card shows: [wiring](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/docs/wiring.md#the-assistant) and [flow D](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/docs/flows.md#d-a-coding-job-for-the-general-workshop) in home-ops.
