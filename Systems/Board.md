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

The one list of what is to do for the build, shared with agents. Today it is Orbit, self-hosted, project Homelab: tasks are `HOMEL-<n>`. Agents reach it through the tool gateway. The private side, the [assistant](Assistant.md) and the private workshop, reads it and never writes it: its gateways list the board's read-only task tools only. On trial until 2026-12-08: [decision](../Decisions/2026-11-24%20Orbit%20holds%20the%20build%20board.md). Its setup and what to keep to restore it: [orbit/README.md](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/default/orbit/README.md) in [home-ops](../Repos/home-ops.md).

Personal tasks are not on it, and nothing private is written there.

## A task is an outcome

- The title says what will be true, starting with a verb.
- The description starts with "Done when:" and lists its pull requests.
- Its steps are sub-issues, one level only.

## Who and when

| Shown by | Means |
| --- | --- |
| Assigned to you | Your step. Its description starts with "Your step", which is how the assistant's briefing finds it |
| Not assigned | An agent's step |
| Todo | Can be done now |
| Backlog | Waiting on an earlier step, or parked |
| In Progress | Being worked on. At most three outcomes |

Whoever finishes a step moves the next one to Todo.

## Labels

Six, for what the parent, the assignee and the status do not show. A task carries every label that applies; a parent shows what it serves, so it is never a label.

| Label | Means |
| --- | --- |
| `handbook`, `home-ops`, `miroir`, `dotfiles` | The repo its pull requests land in. A task that touches two carries both |
| `decision` | A choice only you can make |
| `hands-on` | Needs your machine, your accounts or the NAS; an agent cannot do it |

A new label is added only when one of these keeps being wrong. One that is on few tasks after two weeks goes.

## Tasks and pull requests

- The task lists its pull requests.
- A pull request names its task in its description, for example `HOMEL-1`.
- The agent that opens or merges a pull request updates the step.
- A task is closed after a reviewed merge or after you accept it, never because an agent thinks it is done.

## Tasks and pages

A page that states something a task will change names the task beside it: "does not read the warehouse today (HOMEL-49)". That makes the pages a task touches findable.

- Before closing a task, search its number in every repo and bring each line up to date, in the same pull request where possible:

  ```sh
  grep -rn --include='*.md' 'HOMEL-49\b' handbook home-ops miroir dotfiles
  ```

- The line then states the new fact and drops the number. A closed task's number in a page is a page left stale.
- Once a week the review agent lists the numbers that pages still name while their task is Done, and fixes them. It is the net, not the method: the agent that did the work knows what changed.

## Working documents

An audit, an investigation, the plan of one outcome: these belong to the task, not to a repo. Short ones go in the description, longer ones in a document linked from it. When the task closes, what lasts goes into a final page and the working document is deleted. See [Handbook](Handbook.md#where-a-page-lives).

## Ideas

A new idea becomes one task in Backlog with a title and one line. It is not started, split or scheduled until it is pulled into Todo.

## Related

![[Related.base#Everything]]
