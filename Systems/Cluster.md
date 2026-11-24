---
aliases:
  - Talos
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: self
reviewed: 2026-11-24
status:
  - active
summary: "The machines everything runs on: a main cluster of three nodes and an edge cluster of one."
type:
  - platform
uses:
  - "[[NAS]]"
created: 2026-11-24T22:00
---

# Cluster

Two Kubernetes clusters run from one repo. Main: three nodes, with storage on the nodes themselves. Edge: one node, for the [home hub](Home%20hub.md). The repo is applied by Flux: what is merged is what runs.

## Where its code is

[home-ops](../Repos/home-ops.md). Its agent instructions describe the layout, the conventions and the pitfalls.

## Related

![[Related.base#Everything]]
