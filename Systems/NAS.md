---
aliases:
  - TrueNAS
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: self
reviewed: 2026-11-24
status:
  - active
summary: Bulk storage, backups and the object store, outside the clusters.
type:
  - platform
created: 2026-11-24T22:00
---

# NAS

The box that holds bulk storage and backups, and the object store the clusters back up to.

## Where its code is

Its containers are deployed from [home-ops](../Repos/home-ops.md), under `docker/truenas`. How they are deployed, how to rebuild the NAS and how to restore the object store: [docker/truenas/README.md](https://github.com/h-wb/home-ops/blob/main/docker/truenas/README.md).

## Related

![[Related.base#Everything]]
