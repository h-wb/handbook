---
aliases:
  - Prefect
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: self
reviewed: 2026-11-24
status:
  - active
summary: Runs a named job with fixed inputs on real data, on a schedule or on request.
type:
  - platform
uses:
  - "[[Cluster]]"
created: 2026-11-24T22:00
---

# Job runner

Where work on real data runs without an agent in the loop. Today it is Prefect.

## How it fits

The [warehouse](Warehouse.md) uses it for every load and every build. A job is defined in the repo of the code it runs.

## Where its code is

Deployed from [home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/automation/prefect`.

## Related

![[Related.base#Everything]]
