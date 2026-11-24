---
id: write-pages
kind: reference
system: handbook
status: draft
summary: The header every page carries, the five kinds of page and their shapes, and where a page lives.
created: 2026-11-24
reviewed: 2026-11-24
---

# How we write pages

## The header

Every page, in every repo, starts with the same header. It is plain YAML, so
the page reads the same on GitHub, in Obsidian (as properties) and in any tool
we move to later.

```yaml
---
id: miroir-timeline          # never changes, survives renames and moves
kind: overview               # overview | how-to | decision | reference | plan
system: miroir               # an id from registry.yaml
status: active               # draft | active | superseded | archived
summary: How a day is rebuilt from screen, browser and messages.
created: 2026-11-24
reviewed: 2026-11-24         # last time someone checked it is still true
---
```

Optional, only when needed:

- `review_every`: days between reviews, when the default for the kind does not fit.
- `owner`: only when it is not obvious who keeps the page true.
- `supersedes`, `superseded_by`: the id of the other page.

Not in the header, on purpose:

- **Last updated.** Git knows it.
- **Stale or not.** It is computed from `reviewed`; see
  [How pages stay true](keep-pages-true.md).
- **Tags.**

The field is `kind`, not `type`, because the vault already uses `type` for
other things and the header must mean the same everywhere.

## The five kinds

| Kind | Shape |
| --- | --- |
| overview | What it is, how it fits, its parts, how to operate it |
| how-to | When to use it, the steps, how to check it worked |
| decision | Context, decision, consequences. One per page, one page at most |
| reference | Facts and tables |
| plan | The goal with its "done when", now, next, open questions |

## Where a page lives

1. Is it about more than one repo, or about how we work? It goes in the handbook.
2. Could a change to one repo's code make it wrong? It goes in that repo.
3. Is it about you (how you use something, what you want from it)? It goes in
   your vault, and nowhere an agent of the general scope can read.

## Rules for whoever writes

- A fact is written on the page of the system that owns it. Other pages link to it.
- Pages name a system by its id and link to its overview. Only `registry.yaml`
  and a system's own overview name repos.
- Links are standard Markdown links, relative inside a repo. No wikilinks and
  no embeds, so a page reads the same everywhere.
- Shorten or delete before appending. Write no page nobody asked for.
- Agent instruction files stay short and are reviewed by a person: commands,
  unusual constraints, links.
