---
area: "[[Homelab]]"
categories:
  - "[[Resources]]"
reviewed: 2026-11-24
summary: The steps to write a page here or in a code repo, with its properties, its shape, its name and its links.
topics:
  - "[[Handbook]]"
created: 2026-11-24T21:00
---

# Write a page

## When to use it

Before adding or changing a page in the handbook, or a documentation page in a code repo. Both carry the same properties.

## Steps

1. Decide where it lives: [Handbook](../Systems/Handbook.md#where-a-page-lives).
2. Start from the template of its category, in [Templates](../Templates/).
3. Fill the properties, give it its shape, name it and link it, as below.
4. Set `reviewed` to today only if you checked what the page says against reality.

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
| `categories` | What it is: Systems, Repos, Resources, Plans or Decisions |
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
| Repos | One code repo | What it holds and where its pages are. Ten lines |



## Names

- A system: the role, in one or two words. `Board`, not the product.
- A decision: the day it was taken, then what was decided as a sentence. `2026-11-24 Orbit holds the build board`. No running number: two pull requests cannot both take "the next one".
- A resource or a plan: a clean title, no date.


## Links between pages

- A page about a system names it in `topics`: `"[[Board]]"`. That is all it takes to belong to it, in this repo or in a code repo.
- A system page ends with `![[Related.base#Everything]]`. In Obsidian that lists every page that names it or links to it, grouped by category. Nobody keeps that list by hand. It is the one embed allowed here; on GitHub it shows as a line of text.
- An agent finds the same pages with `grep -rl '\[\[Board\]\]'` across the repos.


## Writing

The vault's style: info-dense and plain, no commentary about the page itself, few em-dashes, little bold. Standard Markdown links, relative inside a repo. Shorten or delete before appending. Write no page nobody asked for.

## Check it worked

- The properties parse as YAML. A value that contains a colon is in quotes.
- Every relative link opens.
- In Obsidian, the page shows in [Pages.base](../Templates/Bases/Pages.base) under its category.
