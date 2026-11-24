---
aliases:
  - Miroir
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
reviewed: 2026-11-24
status:
  - active
summary: Every source mirrored into one database and kept for good, with tables built for reading, dashboards and a timeline.
created: 2026-11-24T22:00
---

# Warehouse

The record of what happened. Today it is Miroir.

## How it fits

- Rows arrive three ways: a [collector](Collector.md) on a device delivers them, a service is fetched on a schedule, or an app pushes an export.
- Raw tables mirror each source. Everything that interprets them is built after each load, by the [job runner](Job%20runner.md).
- You read it through [dashboards](Dashboards.md) and through its timeline, which rebuilds a day.
- It holds private data. Only trusted models read it, and general agents work on its code with made-up data.

## Where its code is

The application is [pipelines](../Repos/pipelines.md). It is deployed from [home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/automation/miroir`, where its page says what is deployed and how data flows.

## Related

![[Related.base#Everything]]
