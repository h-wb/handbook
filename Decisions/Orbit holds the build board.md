---
area: "[[Homelab]]"
categories:
  - "[[Decisions]]"
summary: A trial of Orbit, self-hosted, as the build board shared with agents, judged on 2026-12-08.
created: 2026-11-24T21:00
---

# Orbit holds the build board

## Context

The build's tasks sat in a personal task app that agents could not read, with "(you)" and "(agents)" written in titles in place of real assignment.

## Decision

Orbit, self-hosted, holds [the board](../Systems/Board.md): one project, Homelab. Agents reach it through the tool gateway. It holds tasks only; pages live in this repo: [decision](Shared%20pages%20live%20in%20the%20handbook.md). Personal tasks do not move.

It is a trial until 2026-12-08. Nothing else about tools changes before then.

## Judged on

- Did you open it?
- Did an agent pick up work from the board without help?
- Did it lose anything, or break on an upgrade?

## Consequences

- Orbit was three weeks old when this was decided. The board can be recreated from pull requests and this handbook if it is lost.
- An agent's token reads everything in its workspace, so nothing private goes there.
- Orbit cannot attach a pull request to an existing task, so tasks and pull requests point at each other by hand.
