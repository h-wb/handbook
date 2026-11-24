---
area: "[[Homelab]]"
categories:
  - "[[Decisions]]"
summary: Agents work in hardened pods, one place per scope, rather than in per-task sandboxes.
topics:
  - "[[Workshop]]"
  - "[[Assistant]]"
  - "[[Cluster]]"
created: 2026-11-24T15:30
---

# Each scope runs in its own hardened pods

## Context

An agent with a shell can read everything its process can. The [workshop](../Systems/Workshop.md) runs every agent as the daemon's user and keeps all transcripts in the daemon's home, so its tool restrictions are no boundary for an agent with a shell.

## Decision

- Hardened pods, not OpenShell sandboxes.
- On 2026-11-09: one workshop daemon per scope, general and private, both in the `llm` namespace. A place (a filesystem, its credentials, its network reach) has exactly one scope and holds only that scope's credentials.
- Left out: one workshop for both scopes; a sandbox per task (Kubernetes agent-sandbox, gVisor, hosted sandboxes), which neither Paseo nor Hermes can launch into natively, while a place per scope gives the same guarantee for two fixed scopes with far fewer parts; the sandboxes coding agents ship with, useful as a second layer inside a place but not the boundary, since each harness configures its own.

## Consequences

- The two workshops are one product: one app with two hosts, one release definition with two sets of values.
- Adding a place (another machine, a per-task sandbox) means picking its scope. It gets that scope's model key, tool gateway and memory, and nothing else changes.
- The places today and their network reach: [Places](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/README.md#places) in home-ops.
