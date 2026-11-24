---
aliases:
  - n8n
area: "[[Homelab]]"
categories:
  - "[[Systems]]"
hosted: self
reviewed: 2026-11-24
status:
  - active
summary: Glue between services, such as when this arrives there, write that here; built by hand in its interface.
type:
  - platform
upkeep: medium
uses:
  - "[[Cluster]]"
  - "[[Notes vault]]"
created: 2026-11-24T19:30
---

# Workflow runner

Connects one service to another when something happens or on a clock. Today it is n8n.

## How it fits

- Its workflows are built and kept in its own interface, not in git. Read the list there; no page copies it.
- It writes notes into the [vault](Notes%20vault.md) through an Obsidian running in the cluster, so the change syncs to every device.
- It is not where work on your data runs: that is the [job runner](Job%20runner.md). It is not what talks to you: that is the [assistant](Assistant.md).

## How we use it

Where a new automation goes:

| It is | It goes to |
| --- | --- |
| Glue between two services, or a webhook | A workflow here |
| A job on data, with inputs and a result to keep | A deployment on the [job runner](Job%20runner.md), in the repo of its code |
| Something for you to read or answer | A routine of the [assistant](Assistant.md) |

A workflow is named `Source → Destination: Action`, carries one domain tag, and sets the shared error workflow, which notifies you when a scheduled run fails.

## Where its code is

Deployed from [home-ops](../Repos/home-ops.md), under `kubernetes/apps/main/automation/n8n`. The workflows themselves are in n8n.

## Related

![[Related.base#Everything]]
