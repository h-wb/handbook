---
id: agent-rules
type: reference
system: handbook
status: draft
summary: The rules every agent follows, and how they reach each repo, each skill and the assistant without being copied.
created: 2026-11-24
reviewed: 2026-11-24
---

# How agents work here

## The rules

1. **Start from the record.** Read [Start here](../README.md) and the board
   before doing anything. What is not on the board or in a page is not known to you.
2. **Respect the scope.** A general agent never reads private data. Checks on
   the warehouse are counts and shapes, never contents.
3. **Branch and pull request.** Never the main branch. Someone other than the
   author reviews what changes behaviour.
4. **Spend with care.** Name a cheap model for every helper, one or two at a
   time. Do not step up to a dearer model without asking.
5. **Write little.** Follow [How we write pages](write-pages.md).
6. **Finish by updating the record.** The task and its steps, and any page your
   change made wrong.
7. **Park ideas.** A new idea is one line in Backlog, not more work now.

## How the rules reach everything

The rules are written once, here. Everything else points at them.

| Place | Holds |
| --- | --- |
| Each repo's agent instructions | How to build and test that repo, what must not break, the scope rule in one paragraph, and a link to Start here |
| Skills | The steps of one procedure, with links here for the rules |
| The assistant's standing instructions | Its own behaviour, and a link to Start here |
| Your vault | A read-only copy of this handbook, so your notes can link to it |

The scope rule is the one thing repeated in each repo, because an agent must
see it before it has read anything else.
