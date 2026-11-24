---
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: external
reviewed: 2026-11-24
status:
  - active
summary: What the handbook is, where a page lives, how systems and repos are named once, and how pages stay true.
type:
  - work
upkeep: low
created: 2026-11-24T21:00
---

# Handbook

This repo. Plain Markdown with the vault's own properties, so a page reads the same in Obsidian, on GitHub and to an agent. How to write one: [Write a page](../Resources/Write%20a%20page.md).

## Where a page lives

1. About more than one repo, or about how things run: here.
2. A change to one repo's code could make it wrong: in that repo, with the same properties.
3. About you, how you use something, what you want from it: the vault.

A replaced or dropped page moves to `Archives/`, with `superseded_by` when another page replaces it. Same move as in the vault, and the only one.


## Roles and aliases

A system page is named for the role, and the product that fills it today is an alias: [Board](Board.md) is also known as Orbit. Other pages say "the board" and link to that page. When the product changes, one page changes.

Systems and repos are different things: a system is a role, a repo is where code lives, and one system can span several repos. Each repo has one page in [Repos](../Repos/), and that page is the only place that describes it. It names the systems it serves in `topics`, so each system page lists its repos by itself. Adding a repo is adding one page.


## The table of systems

One row per system, from the properties of its page: whether it is in use (`status`), how much you really use it (`use`), how much attention it asks for (`upkeep`), how sure you are it is worth keeping as it is (`confidence`), and when it was last checked (`reviewed`).

It is the view of where things stand: what runs, what you rely on, what costs more than it gives. In Obsidian it is the Systems view of [Pages.base](../Templates/Bases/Pages.base). A blank cell means nobody has judged it yet.

The assistant reads the same properties. A system that is used rarely, asks for a lot, or has low confidence is one to bring up for revision.

## The map

Each system page says what it `uses` and what it `feeds`. [Map](../Map.md) draws that at two levels: the whole thing, and what reaches the warehouse. In Obsidian, the Connections view of [Pages.base](../Templates/Bases/Pages.base) is the same as a table, and the graph view shows it live.

## Staying true

`reviewed` changes only when someone checked the page against reality. An edit does not change it. Git knows when a page was last changed.

A page is due when `reviewed` is older than its interval:

| Category | Interval |
| --- | --- |
| Resources | 90 days |
| Systems | 180 days |
| Plans | 30 days |
| Repos | 180 days |
| Decisions | never. A decision is replaced, not reviewed |

A page with no `reviewed` is not tracked.

Who checks:

- With the work. A task is not done until the pages it made wrong are fixed.
- Once a week, an agent takes the five pages longest without review, checks each against the code or the cluster, and sets `reviewed` or fixes the page.
- You are asked only when a page states something only you know.

In Obsidian, [Pages.base](../Templates/Bases/Pages.base) shows every page with its last review, oldest first.


## Related

![[Related.base#Everything]]
