---
aliases:
  - Paseo
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: self
reviewed: 2026-11-24
status:
  - active
summary: Where coding agents work, the rules they follow, and how those rules reach each repo without being copied.
type:
  - agent
upkeep: medium
uses:
  - "[[Model gateway]]"
  - "[[Tool gateway]]"
  - "[[Agent memory]]"
  - "[[Board]]"
  - "[[Handbook]]"
created: 2026-11-24T21:00
---

# Workshop

Where agents with a shell work on the repos, through pull requests. Today it is Paseo, one workshop per scope: [decision](../Decisions/2026-11-07%20Each%20scope%20runs%20in%20its%20own%20hardened%20pods.md). How it is deployed and wired is in [home-ops](../Repos/home-ops.md), in [paseo/README.md](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/paseo/README.md): pods, config, profiles, credentials, volumes.

dotfiles defines what an agent is (its tool and memory servers, keys and skills, written once and rendered per scope: [conf.d/ai/README.md](https://github.com/h-wb/dotfiles/blob/master/conf.d/ai/README.md)) and what a workshop pod installs ([conf.d/paseo/README.md](https://github.com/h-wb/dotfiles/blob/master/conf.d/paseo/README.md)); home-ops defines where it runs, which models it uses and what it can reach. A new harness or machine picks a scope; it does not get its own config. In the general workshop the strongest model plans and cheaper ones work: [decision](../Decisions/2026-11-10%20The%20strongest%20model%20plans%20and%20cheaper%20ones%20do%20the%20work.md).

## The rules

1. Start from the record. Read [the handbook](../README.md) and [the board](Board.md) before doing anything. What is not on the board or in a page is not known to you.
2. Respect the scope. A general agent never reads private data. Checks on the warehouse are counts and shapes, never contents.
3. Branch and pull request. Never the main branch. Someone other than the author reviews what changes behaviour.
4. Spend with care. Name a cheap model for every helper, one or two at a time. Do not step up to a dearer model without asking.
5. Write little. Follow [Write a page](../Resources/Write%20a%20page.md).
6. Finish by updating the record: the task and its steps, and any page your change made wrong. Search the task's number in the repos to find them: [tasks and pages](Board.md#tasks-and-pages).
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

## Helping a cheaper model

In order of effect:

1. Fewer tools in view, with short descriptions. Fix a tool's description before writing a skill about it.
2. Anything that must happen the same way every time is a named tool or a job, not prose.
3. One skill, one job: exact tool names, the order, and how to check it worked.
4. A stronger model plans and reviews; a cheaper one does the work.
5. When an agent stumbles twice on the same thing, change the tool description or the skill, not the prompt.

## Related

![[Related.base#Everything]]
