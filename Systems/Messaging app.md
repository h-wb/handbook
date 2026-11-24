---
aliases:
  - Matrix
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: self
reviewed: 2026-11-24
status:
  - active
summary: How you reach the assistant, and how it reaches you.
type:
  - service
uses:
  - "[[Cluster]]"
created: 2026-11-24T22:00
---

# Messaging app

The app you talk to the [assistant](Assistant.md) in. Today it is Matrix, on our own homeserver in the cluster, federating with Beeper only: [decision](../Decisions/2026-11-11%20The%20assistant%20is%20reached%20on%20Matrix%2C%20on%20our%20own%20homeserver.md). Its rooms are split by how much they may interrupt: [decision](../Decisions/2026-11-19%20Rooms%20are%20split%20by%20how%20much%20they%20may%20interrupt.md).

## Where its code is

[home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/default/continuwuity`. The assistant's account, rooms and setup: [hermes/README.md](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/hermes/README.md#messaging) there.

## Related

![[Related.base#Everything]]
