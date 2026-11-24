---
aliases:
  - Obsidian
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
reviewed: 2026-11-24
status:
  - active
summary: "Your own knowledge, private: the vault."
created: 2026-11-24T22:00
---

# Notes

Your vault. Private: only you and agents of the private scope read it.

## How it fits

- A copy in the cluster stays in sync, and the [tool gateway](Tool%20gateway.md) serves it to private agents.
- The [assistant](Assistant.md) writes only in its own folders, and asks first.
- This handbook is meant to appear in it as a read-only copy, so your notes can link to these pages.

## Where its code is

The copy and its tools are in [home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/llm/toolhive/mcp-servers/vault`. The vault's own rules are in the vault.

## Related

![[Related.base#Everything]]
