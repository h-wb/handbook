---
aliases:
  - miroir-collector
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
feeds:
  - "[[Warehouse]]"
hosted: device
reviewed: 2026-11-24
status:
  - active
summary: "On a device: reads local sources, masks what must not leave, and delivers the rest to the warehouse."
type:
  - record
created: 2026-11-24T22:00
---

# Device collector

A small program on each of your machines that feeds the [warehouse](Warehouse.md). It sends rows as they are and never interprets them.

## Where its code is

The program is part of [pipelines](../Repos/pipelines.md): how to install, configure and run it in [collector/README.md](https://github.com/h-wb/pipelines/blob/main/collector/README.md), how it is released in [docs/releases.md](https://github.com/h-wb/pipelines/blob/main/docs/releases.md), why it is built this way in decisions 030 to 039 of [the decisions](https://github.com/h-wb/pipelines/blob/main/docs/miroir/decisions.md). Its settings on your laptop are in [dotfiles](../Repos/dotfiles.md). The always-on Mac does not run it yet; when it does, its settings go in [home-ops](../Repos/home-ops.md), under `hosts/edge-mac`.

## Related

![[Related.base#Everything]]
