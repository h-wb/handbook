---
aliases:
  - miroir-collector
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
reviewed: 2026-11-24
status:
  - active
summary: "On a device: reads local sources, masks what must not leave, and delivers the rest to the warehouse."
created: 2026-11-24T22:00
---

# Collector

A small program on each of your machines that feeds the [warehouse](Warehouse.md). It sends rows as they are and never interprets them.

## Where its code is

The program is part of [pipelines](../Repos/pipelines.md). Its settings on your laptop are in [dotfiles](../Repos/dotfiles.md), and on the always-on Mac in [home-ops](../Repos/home-ops.md), under `hosts/edge-mac`.

## Related

![[Related.base#Everything]]
