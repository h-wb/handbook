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

The application is [pipelines](../Repos/pipelines.md):

- what Miroir is and how its parts work: [docs/miroir/README.md](https://github.com/h-wb/pipelines/blob/main/docs/miroir/README.md), with configuration, runs, analyses, media, the timeline and the API on the pages beside it;
- why it is built this way: [its numbered decisions](https://github.com/h-wb/pipelines/blob/main/docs/miroir/decisions.md);
- one page per source: [the index](https://github.com/h-wb/pipelines/blob/main/docs/README.md#sources);
- how a stopped source is noticed: [observability](https://github.com/h-wb/pipelines/blob/main/docs/observability.md).

It is deployed from [home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/automation/miroir`: what is deployed, its secrets and how to operate it in [README.md](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/automation/miroir/README.md), how data moves in [docs/flows.md](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/automation/miroir/docs/flows.md).

## Related

![[Related.base#Everything]]
