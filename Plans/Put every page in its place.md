---
area: "[[Homelab]]"
categories:
  - "[[Plans]]"
reviewed: 2026-11-24
summary: Where each existing page of home-ops, pipelines, dotfiles and the vault's homelab notes ends up, in which order, and what is left for later.
topics:
  - "[[Handbook]]"
created: 2026-11-24T23:00
---

# Put every page in its place

## Goal

Done when a fresh agent given only a repo finds the handbook, the board and the rules on its own; every page is where the handbook says it belongs and carries its properties; and no fact is kept true in two places.

Two agents read every documentation page on 2026-11-24: 27 in home-ops, 23 in pipelines, 5 in dotfiles. Their finding in one line: most pages mix what a code change could make wrong with what spans repos. Splitting all of them at once would be a rewrite, so the order below does the cheap and certain part first.

## Now

1. Every page gets the properties, where it is. No page moves, so nothing breaks. One pull request per repo.
2. The old map in home-ops is retired: this handbook replaces it.
3. The agent instructions of home-ops are cut to what an agent needs to work there, with the scope rule and a link here.
4. Statements found out of date are fixed where the fix is a line or two.

## Next

5. The vault's homelab notes that describe systems go to home-ops, rewritten without private details: the NAS shares, the secret-store certificate incident, the monitoring choices, a dataset setting. Three hub notes in the vault are cut down to pointers.
6. The agent instructions of pipelines and of dotfiles are cut the same way. The one in dotfiles is 657 lines.
7. The handbook gets a read-only copy in the vault.
8. An agent reviews the five pages longest without a check, each week.

## Later

These pages are mostly about how things run across repos, and belong here in the end. Each is long, so each moves as short pages, not whole:

| Page today | Becomes |
| --- | --- |
| The AI setup's design, in home-ops | The scope rule as one page, a decision per choice, the rest onto the system pages |
| The assistant's design, in home-ops | A plan here, and decisions |
| The flows of the AI setup and of the warehouse, in home-ops | Stay until then. They show deployed wiring, which a change to home-ops can make wrong |
| The warehouse's product plan, in pipelines | What is still open comes here. What is done is archived there |

## Decided

- Decisions already written in pipelines stay in their one numbered file. Code and pages cite them by number, and that keeps working. The file takes no new decision: a new one gets its own page, named by its day, in the repo it concerns or here if it spans repos.
- Routines and skills are instructions an agent runs, not pages. They get no properties.
- A page gets `reviewed` only when someone checked it. Adding the properties is not a check, so these pages start untracked and enter the weekly review one by one.

- A repo holds final pages only. A working document of a project lives with its task on the board and is deleted when the project closes. The security audit in home-ops moved there on 2026-11-24.
- This page is itself the plan of one task. It is removed when that task closes.

## Open

- Whether the self-hosted apps each get a page, so the table of systems also answers "do I use this".
