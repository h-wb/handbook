---
aliases:
  - Obsidian
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: external
reviewed: 2026-11-24
status:
  - active
summary: "Your own knowledge, private: the vault."
type:
  - service
created: 2026-11-24T22:00
---

# Notes vault

Your vault. Private: only you and agents of the private scope read it.

## How it fits

- The vault's own sync carries it to every device. A headless copy in the cluster is one more device, synced both ways.
- The [tool gateway](Tool%20gateway.md) serves that copy to private agents through two servers: one reads everything, one writes only in `Notes/`, `AI/` and `Archives/`. Only the private gateways list them.
- The [assistant](Assistant.md) asks before every write, and reads the vault's own rules first. What a model writes goes to `AI/`.
- A [workflow](Workflow%20runner.md) writes a note through an Obsidian that runs in the cluster, not by dropping a file on the share: a file written by another pod is never noticed, so it never syncs.
- On a workstation the vault is a plain folder. An agent started inside it reads it whatever its scope, so that is your call each time.
- Nothing a general agent must follow lives in the vault: it could not read it. Such rules live in a repo or in this handbook.
- This handbook is meant to appear in it as a read-only copy, so your notes can link to these pages.

## Where its code is

The copy and its tools are in [home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/llm/toolhive/mcp-servers/vault`. The Obsidian a workflow writes through runs on the neko desktop: [conf.d/neko/README.md](https://github.com/h-wb/dotfiles/blob/master/conf.d/neko/README.md#obsidian) in [dotfiles](../Repos/dotfiles.md). The vault's own rules are in the vault.

## Related

![[Related.base#Everything]]
