---
aliases:
  - Miroir
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: self
reviewed: 2026-11-24
status:
  - active
summary: Every source mirrored into one database and kept for good, with tables built for reading, dashboards and a timeline.
type:
  - record
uses:
  - "[[Job runner]]"
  - "[[NAS]]"
  - "[[Cluster]]"
created: 2026-11-24T22:00
---

# Warehouse

The record of what happened. Today it is Miroir.

## How it fits

- Rows arrive three ways: a [collector](Device%20collector.md) on a device delivers them, a service is fetched on a schedule, or an app pushes an export.
- Raw tables mirror each source. Everything that interprets them is built after each load, by the [job runner](Job%20runner.md).
- You read it through [dashboards](Dashboards.md) and through its timeline, which rebuilds a day.
- It holds private data. Only trusted models read it, and general agents work on its code with made-up data.

## Where its code is

The application is [miroir](../Repos/miroir.md); how data moves through it: [its flows](https://github.com/h-wb/miroir/blob/main/docs/miroir/flows.md). It is deployed from [home-ops](../Repos/home-ops.md): what is deployed, its secrets and how to operate it in [its page](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/automation/miroir/README.md).

## Related

![[Related.base#Everything]]
