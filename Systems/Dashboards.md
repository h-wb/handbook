---
aliases:
  - Metabase
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: self
reviewed: 2026-11-24
status:
  - active
summary: Charts over the warehouse, one collection per source.
type:
  - record
uses:
  - "[[Warehouse]]"
created: 2026-11-24T22:00
---

# Dashboards

Where you look at the [warehouse](Warehouse.md) in charts. Today it is Metabase. The dashboards read the schemas the warehouse's analyses build: [which packages build what](https://github.com/h-wb/pipelines/blob/main/docs/miroir/analyses.md).

## Where its code is

Deployed from [home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/automation/metabase`.

## Related

![[Related.base#Everything]]
