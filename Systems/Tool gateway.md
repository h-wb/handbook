---
aliases:
  - ToolHive
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: self
reviewed: 2026-11-24
status:
  - active
summary: One catalogue of tools, served through one gateway per scope.
type:
  - platform
uses:
  - "[[Cluster]]"
created: 2026-11-24T22:00
---

# Tool gateway

Agents do not connect to tools one by one. They reach one gateway, which serves the tools their scope may use. Today it is ToolHive.

## How it fits

- One gateway per scope: general, private, and one for the [assistant](Assistant.md).
- The general gateway lists only tools that hold nothing private. The private ones serve the whole catalogue, except that they list only the [board](Board.md)'s read-only task tools: it is general, and nothing goes back to it.
- A tool is added once, as an entry in the catalogue, and every agent of that scope gets it.

## Where its code is

[home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/llm/toolhive`: the gateways in `config/`, one folder per tool in `mcp-servers/`. Endpoints, who may reach each gateway and with which key: [README.md](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/README.md) and [docs/wiring.md](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/docs/wiring.md) there. How each agent is configured to reach it: [conf.d/ai/README.md](https://github.com/h-wb/dotfiles/blob/master/conf.d/ai/README.md) in [dotfiles](../Repos/dotfiles.md).

## Related

![[Related.base#Everything]]
