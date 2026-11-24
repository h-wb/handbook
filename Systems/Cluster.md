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

[home-ops](../Repos/home-ops.md). Its agent instructions describe the layout, the conventions and the pitfalls. Pages there: databases in [the CNPG Components](https://github.com/h-wb/home-ops/blob/main/kubernetes/components/cnpg/README.md), with [point-in-time recovery](https://github.com/h-wb/home-ops/blob/main/kubernetes/components/cnpg/RECOVERY.md); sign-in in [Kanidm](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/security/kanidm/app/README.md); what is backed up and how it comes back in [backups](https://github.com/h-wb/home-ops/blob/main/docs/backups.md); secrets in [External Secrets](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/external-secrets/external-secrets/app/README.md); the Mac under the edge cluster in [hosts/edge-mac](https://github.com/h-wb/home-ops/blob/main/hosts/edge-mac/README.md); how a dependency upgrade is reviewed in [the Renovate rule](https://github.com/h-wb/home-ops/blob/main/.kritika/renovate.md).

## Related

![[Related.base#Everything]]
