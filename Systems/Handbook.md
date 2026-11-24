---
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
reviewed: 2026-11-24
status:
  - active
summary: How pages are written here, where a page lives, and how pages stay true.
url: https://github.com/h-wb/handbook
created: 2026-11-24T21:00
---

# Handbook

This repo. Plain Markdown with the vault's own properties, so a page reads the same in Obsidian, on GitHub and to an agent.

## Properties

The same keys as the vault, written the same way, in alphabetical order with `created` last.

```yaml
---
aliases:
  - Orbit
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
reviewed: 2026-11-24
status:
  - active
summary: Where the build's tasks live and how we use them.
topics:
  - "[[AI]]"
url: https://github.com/h-wb/home-ops
created: 2026-11-24T21:00
---
```

| Property | Holds |
| --- | --- |
| `categories` | What it is: Systems, Resources, Plans or Decisions |
| `area` | Which part of life. Homelab for most pages here |
| `status` | Only on Systems: `active` or `inactive` |
| `topics` | What it is about, when it helps |
| `aliases` | Other names it is known by: the product that fills a role today |
| `url` | Its repo or its address |
| `summary` | One sentence, so a table or an agent can tell what the page is without opening it |
| `reviewed` | The day someone last checked the page against reality |
| `created` | When it was written, `YYYY-MM-DDTHH:mm` |

`summary` and `reviewed` are the two this handbook adds to the vault's set. No empty properties, no tags.

## What each category is

| Category | Is | Shape |
| --- | --- | --- |
| Systems | A noun: how something runs | What it is, how it fits, how we use it, where its code is |
| Resources | Reference kept: how-tos, fixes | When to use it, the steps, how to check it worked |
| Plans | A plan followed over time | The goal with its "done when", now, next, open questions |
| Decisions | One decision | Context, decision, consequences. One page at most |

Templates for each are in [Templates](../Templates/).

## Roles and aliases

A system page is named for the role, and the product that fills it today is an alias: [Board](Board.md) is also known as Orbit. Other pages say "the board" and link to that page. When the product changes, one page changes.

A system page is the only place that names its repos.

## Links between pages

- A page about a system names it in `topics`: `"[[Board]]"`. That is all it takes to belong to it, in this repo or in a code repo.
- A system page ends with `![[Related.base#Everything]]`. In Obsidian that lists every page that names it or links to it, grouped by category. Nobody keeps that list by hand. It is the one embed allowed here; on GitHub it shows as a line of text.
- A system page's own "Where its code is" stays a short hand-written list of entry points, not an inventory.
- An agent finds the same pages with `grep -rl '\[\[Board\]\]'` across the repos.

## Names

- A system: the role, in one or two words. `Board`, not the product.
- A decision: the day it was taken, then what was decided as a sentence. `2026-11-24 Orbit holds the build board`. No running number: two pull requests cannot both take "the next one".
- A resource or a plan: a clean title, no date.

## Where a page lives

1. About more than one repo, or about how things run: here.
2. A change to one repo's code could make it wrong: in that repo, with the same properties.
3. About you, how you use something, what you want from it: the vault.

A replaced or dropped page moves to `Archives/`, with `superseded_by` when another page replaces it. Same move as in the vault, and the only one.

## Staying true

`reviewed` changes only when someone checked the page against reality. An edit does not change it. Git knows when a page was last changed.

A page is due when `reviewed` is older than its interval:

| Category | Interval |
| --- | --- |
| Resources | 90 days |
| Systems | 180 days |
| Plans | 30 days |
| Decisions | never. A decision is replaced, not reviewed |

A page with no `reviewed` is not tracked.

Who checks:

- With the work. A task is not done until the pages it made wrong are fixed.
- Once a week, an agent takes the five pages longest without review, checks each against the code or the cluster, and sets `reviewed` or fixes the page.
- You are asked only when a page states something only you know.

In Obsidian, [Pages.base](../Templates/Bases/Pages.base) shows every page with its last review, oldest first.

## Writing

The vault's style: info-dense and plain, no commentary about the page itself, few em-dashes, little bold. Standard Markdown links, relative inside a repo. Shorten or delete before appending. Write no page nobody asked for.

## Related

![[Related.base#Everything]]
