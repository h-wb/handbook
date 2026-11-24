---
aliases:
  - Paseo
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
reviewed: 2026-11-24
status:
  - active
summary: Where coding agents work, the rules they follow, and how those rules reach each repo without being copied.
url: https://github.com/h-wb/home-ops
created: 2026-11-24T21:00
---

# Workshop

Where agents with a shell work on the repos, through pull requests. Today it is Paseo, one workshop per scope. How it is deployed and wired: `kubernetes/apps/main/llm/paseo` in home-ops.

## The rules

1. Start from the record. Read [the handbook](../README.md) and [the board](Board.md) before doing anything. What is not on the board or in a page is not known to you.
2. Respect the scope. A general agent never reads private data. Checks on the warehouse are counts and shapes, never contents.
3. Branch and pull request. Never the main branch. Someone other than the author reviews what changes behaviour.
4. Spend with care. Name a cheap model for every helper, one or two at a time. Do not step up to a dearer model without asking.
5. Write little. Follow [Handbook](Handbook.md).
6. Finish by updating the record: the task and its steps, and any page your change made wrong.
7. Park ideas. A new idea is one line in the backlog, not more work now.

## How the rules reach everything

Written once, here. Everything else points at them.

| Place | Holds |
| --- | --- |
| Each repo's agent instructions | How to build and test that repo, what must not break, the scope rule in one paragraph, a link to the handbook |
| Skills | The steps of one procedure, with links here for the rules |
| The assistant's standing instructions | Its own behaviour, and a link to the handbook |
| The vault | A read-only copy of this handbook, so notes can link to it |

The scope rule is the one thing repeated in each repo, because an agent must see it before it has read anything else.

## Related

![[Related.base#Everything]]
