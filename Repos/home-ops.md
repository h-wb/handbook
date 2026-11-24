---
area: "[[Homelab]]"
categories:
  - "[[Repos]]"
reviewed: 2026-11-24
summary: "Everything that is deployed: both clusters, the NAS containers, and the pages about them."
topics:
  - "[[Assistant]]"
  - "[[Board]]"
  - "[[Cluster]]"
  - "[[Device collector]]"
  - "[[Dashboards]]"
  - "[[Home hub]]"
  - "[[Job runner]]"
  - "[[Agent memory]]"
  - "[[Messaging app]]"
  - "[[Model gateway]]"
  - "[[NAS]]"
  - "[[Notes vault]]"
  - "[[Tool gateway]]"
  - "[[Warehouse]]"
  - "[[Workshop]]"
url: https://github.com/h-wb/home-ops
created: 2026-11-24T21:00
---

# home-ops

The GitOps repo. What is in it runs: Flux applies it to both clusters, and the NAS containers follow it.

Agents start with its [AGENTS.md](https://github.com/h-wb/home-ops/blob/main/AGENTS.md). Its [README.md](https://github.com/h-wb/home-ops/blob/main/README.md) gives the stack and the layout; pages about one app sit next to that app, and what spans the cluster is in [docs/](https://github.com/h-wb/home-ops/tree/main/docs).
