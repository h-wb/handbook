---
area: "[[Homelab]]"
categories:
  - "[[Decisions]]"
summary: Each cluster runs its own Prometheus with a retention of days, and there is no long-term metrics store.
topics:
  - "[[Cluster]]"
created: 2025-10-12T00:00
---

# Each cluster watches itself and keeps metrics for days

## Context

Two clusters, one of them a single node. Metrics are used to find out what went wrong in the last days, not to study a year. A shared store across clusters (Thanos) was looked at.

## Decision

- Each cluster runs its own Prometheus and alerting, so losing one cluster does not blind the other.
- Retention is short and capped by size: 7 days on main, 3 days on edge.
- No Thanos and no long-term store: it costs more storage than a homelab of this size justifies, and nothing reads metrics that old.
- Uptime of endpoints is checked apart from metrics, by Gatus.

## Consequences

- A question about last month cannot be answered from metrics. Logs have their own store and retention.
- Grafana runs on main and reads main's Prometheus; edge has no dashboards of its own.
- If a year of metrics is ever wanted, VictoriaMetrics is the candidate: it replaces Prometheus in place and holds far more per gigabyte.
- The values are in [home-ops](../Repos/home-ops.md), in each cluster's `observability/kube-prometheus-stack`.
