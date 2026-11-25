---
aliases:
  - Obsidian
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: external
reviewed: 2026-11-25
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
- A [workflow](Workflow%20runner.md) writes a note into that copy through its own tool server, which may write only `Notes/` and `References/`. The copy's sync uploads it, so no Obsidian app has to run.
- On a workstation the vault is a plain folder. An agent started inside it reads it whatever its scope, so that is your call each time.
- Nothing a general agent must follow lives in the vault: it could not read it. Such rules live in a repo or in this handbook.
- This handbook is meant to appear in it as a read-only copy, so your notes can link to these pages.

## Where its code is

The copy and its tools are an app of their own in [home-ops](../Repos/home-ops.md): [default/obsidian-vault](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/default/obsidian-vault/README.md). The vault's own rules are in the vault.

## Related

![[Related.base#Everything]]
