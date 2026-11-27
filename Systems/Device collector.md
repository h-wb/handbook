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

The program is part of [miroir](../Repos/miroir.md): [collector/README.md](https://github.com/h-wb/miroir/blob/main/collector/README.md). Its settings on your laptop are in [dotfiles](../Repos/dotfiles.md): [conf.d/macos/README.md](https://github.com/h-wb/dotfiles/blob/master/conf.d/macos/README.md#the-collector). The always-on Mac does not run it today (HOMEL-2); its settings will be in [home-ops](../Repos/home-ops.md), under `hosts/edge-mac`.

## Related

![[Related.base#Everything]]
