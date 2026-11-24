---
id: decision-handbook-in-git
type: decision
system: handbook
status: active
summary: Pages that span repos live in this repo as plain Markdown; the vault gets a read-only copy; the board is a separate tool.
created: 2026-11-24
---

# Shared pages live in a handbook repo

## Context

Pages were spread over three code repos, a private vault and one agent's
memory. A fresh agent given only a repo could not tell what was in progress.
Pages about how we work, and about systems that span repos, had no home that
was not borrowed from one repo.

Two alternatives were tried or measured on 2026-11-24:

- **Pages in the board tool.** Reading one page through its tool returned it
  twice, as editor blocks and as Markdown: about seven times the size of the
  Markdown alone, and a change meant sending the whole page back. Too costly
  for agents, who read and write most pages.
- **Pages in the private vault.** General agents cannot read it, and a shared
  folder inside it is one misplaced note away from a leak.

## Decision

- This repo holds what spans repos and how we work, as plain Markdown with one
  header ([How we write pages](../how-we-work/write-pages.md)).
- Each code repo keeps the pages a change to its code could make wrong.
- The vault gets a read-only copy of this repo in a folder, written by a job.
  Information only flows from general to private.
- The board stays a separate tool ([decision](0002-orbit-for-the-board.md)).

## Consequences

- Agents read and write pages cheaply and through review.
- You do not edit these pages in the vault: the copy is overwritten. You edit
  on GitHub, in a clone, or through an agent.
- One more repo exists. `registry.yaml` is the only place that lists repos.
