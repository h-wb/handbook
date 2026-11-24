---
aliases:
  - Orbit
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: self
reviewed: 2026-11-24
status:
  - active
summary: Where the build's tasks live, what a task is, and how ownership and readiness are shown.
type:
  - work
upkeep: medium
uses:
  - "[[Cluster]]"
created: 2026-11-24T21:00
---

# Board

The one list of what is to do for the build, shared with agents. Today it is Orbit, self-hosted, project Homelab: tasks are `HOMEL-<n>`. Agents reach it through the tool gateway. On trial until 2026-12-08: [decision](../Decisions/2026-11-24%20Orbit%20holds%20the%20build%20board.md).

Personal tasks are not on it, and nothing private is written there.

## A task is an outcome

- The title says what will be true, starting with a verb.
- The description starts with "Done when:" and lists its pull requests.
- Its steps are sub-issues, one level only.

## Who and when

| Shown by | Means |
| --- | --- |
| Assigned to you | Your step |
| Not assigned | An agent's step |
| Todo | Can be done now |
| Backlog | Waiting on an earlier step, or parked |
| In Progress | Being worked on. At most three outcomes |

Whoever finishes a step moves the next one to Todo.

## Tasks and pull requests

- The task lists its pull requests.
- A pull request names its task in its description, for example `HOMEL-1`.
- The agent that opens or merges a pull request updates the step.
- A task is closed after a reviewed merge or after you accept it, never because an agent thinks it is done.

## Ideas

A new idea becomes one task in Backlog with a title and one line. It is not started, split or scheduled until it is pulled into Todo.

## Related

![[Related.base#Everything]]
