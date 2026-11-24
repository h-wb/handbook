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

The [warehouse](Warehouse.md) uses it for every load and every build: [how](https://github.com/h-wb/pipelines/blob/main/docs/miroir/runs.md#prefect). A job is defined in the repo of the code it runs. The assistant cannot start jobs through it today (HOMEL-56): [decision](../Decisions/2026-11-09%20One%20private%20assistant%20acts%20only%20through%20named%20tools.md).

## Where its code is

Deployed from [home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/automation/prefect`.

## Related

![[Related.base#Everything]]
