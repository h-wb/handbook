---
area: "[[Homelab]]"
categories:
  - "[[Decisions]]"
summary: In the general workshop the strongest model plans and decides, and starts cheaper agents to read, build and review.
topics:
  - "[[Workshop]]"
  - "[[Model gateway]]"
created: 2026-11-24T15:30
---

# The strongest model plans and cheaper ones do the work

## Context

A change costs what its agents read, times the turns they take. Reading code, editing and running checks take many turns; planning and deciding take few.

## Decision

In the general [workshop](../Systems/Workshop.md) the strongest model only plans, writes the spec, starts the others and decides. Cheaper agents explore, build and review.

- The spec is the hand-off: the goal, the files, what not to touch, and the check that must pass. A cheaper model goes wrong on an unclear task more than on the edit.
- The check runs before any review. It costs no tokens.
- One more round, then stop. A builder that fails twice is not asked a third time.
- A small change is not delegated: a worker starts cold, so the hand-off costs more than the edit.
- The reviewer is another model family than the builder, and reads the diff without the orchestrator's reasoning.

## Consequences

- More tokens in total, most of them cheap, and the strong model's context stays small, which matters when it is on a subscription window.
- It is an instruction, not a lock: nothing stops the orchestrator from doing all the work on the strong model.
- In the private workshop no agent starts another, so you pick the profiles.
- The profiles: [Paseo environments](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/paseo/README.md#profiles) in home-ops. The order is the `orchestrate` skill in dotfiles.
