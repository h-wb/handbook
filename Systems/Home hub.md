---
aliases:
  - Home Assistant
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: self
reviewed: 2026-11-24
status:
  - active
summary: Home automation, on the edge cluster.
type:
  - service
uses:
  - "[[Cluster]]"
created: 2026-11-24T22:00
---

# Home hub

Runs the house's automations. It gives the [assistant](Assistant.md) no live signals today (HOMEL-47).

## Where its code is

[home-ops](../Repos/home-ops.md), under `kubernetes/apps/edge/home-automation`. The edge cluster runs as a VM on a Mac with the Zigbee dongle passed through: [hosts/edge-mac](https://github.com/h-wb/home-ops/blob/main/hosts/edge-mac/README.md).

## Related

![[Related.base#Everything]]
