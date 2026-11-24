---
area: "[[Homelab]]"
categories:
  - "[[Decisions]]"
summary: Pages that span repos live in this repo as plain Markdown with the vault's properties; the vault gets a read-only copy.
topics:
  - "[[Handbook]]"
created: 2026-11-24T21:00
---

# Shared pages live in the handbook

## Context

Pages were spread over three code repos, a private vault and one agent's memory. A fresh agent given only a repo could not tell what was in progress. Pages about how things run, and about systems that span repos, had no home that was not borrowed from one repo.

Two alternatives were tried or measured on 2026-11-24:

- Pages in the board tool. Reading one page through its tool returned it twice, as editor blocks and as Markdown: about seven times the size of the Markdown alone, and a change meant sending the whole page back. Too costly for agents, who read and write most pages.
- Pages in the private vault. General agents cannot read it, and a shared folder inside it is one misplaced note away from a leak.

## Decision

- This repo holds what spans repos and how things run, as plain Markdown with the vault's own properties: [Handbook](../Systems/Handbook.md).
- Each code repo keeps the pages a change to its code could make wrong.
- The vault gets a read-only copy of this repo, written by a job. Information only flows from general to private.
- The board stays a separate tool: [decision](2026-11-24%20Orbit%20holds%20the%20build%20board.md).

## Consequences

- Agents read and write pages cheaply and through review.
- The copy in the vault is overwritten on each run. Pages are edited in this repo.
- One vocabulary for the vault and the handbook, so the same tables and the same review dates work in both.
