---
area: "[[Homelab]]"
categories:
  - "[[Resources]]"
reviewed: 2026-11-24
summary: How the systems connect, at two levels, drawn from what each system page says it uses and feeds.
topics:
  - "[[Handbook]]"
created: 2026-11-24T23:50
---

# Map

The connections are properties of each system page: `uses` (what it needs to run) and `feeds` (where its data goes). The drawings below are made from them, and are checked against them at each review. In Obsidian every box opens its page.

For one system in detail, open its page: the Related table lists everything that points at it, and the local graph shows its neighbours.

## The whole thing

```mermaid
flowchart LR
    subgraph yours[Yours: apps and services you use]
        PT["Personal tasks"]
        CA["Calendar"]
        NV["Notes vault"]
        MA["Messaging app"]
        HH["Home hub"]
    end
    subgraph sources[Sources: what produces data]
        SRC["Screen, browser, messages,<br/>health, music, code, rides"]
        LT["Location tracker"]
    end
    subgraph record[The record]
        DC["Device collector"]
        WH["Warehouse"]
        DA["Dashboards"]
    end
    subgraph agents[Agents]
        AS["Assistant"]
        WS["Workshop"]
    end
    subgraph work[Work]
        BO["Board"]
        HB["Handbook"]
    end
    subgraph platform[Platform]
        MG["Model gateway"]
        TG["Tool gateway"]
        AM["Agent memory"]
        JR["Job runner"]
        WR["Workflow runner"]
        CL["Cluster"]
        NA["NAS"]
    end
    SRC --> DC --> WH --> DA
    SRC --> WH
    WH --> JR
    AS --> MA
    AS --> PT
    AS --> CA
    AS --> NV
    AS -.->|planned| WH
    WS --> BO
    WS --> HB
    AS & WS --> MG & TG & AM
    MG --> CL
    TG --> CL
    AM --> CL
    JR --> CL
    WR --> NV
    WR --> CL
    CL --> NA
    class PT,CA,NV,MA,HH,LT,DC,WH,DA,AS,WS,BO,HB,MG,TG,AM,JR,WR,CL,NA internal-link;
```

A solid arrow is in place today. A dashed one is planned.

## What reaches the warehouse, and what does not

```mermaid
flowchart LR
    subgraph device[On your devices]
        SA["Screen activity"]
        BH["Browser history"]
        ME["Messages"]
        HD["Health data"]
    end
    subgraph services[Services]
        ML["Music listening"]
        CO["Code activity"]
        BR["Bike rides"]
    end
    subgraph notyet[Not in the warehouse]
        LT["Location tracker"]
        PT["Personal tasks"]
        CA["Calendar"]
        NV["Notes vault"]
        HH["Home hub"]
    end
    DC["Device collector"]
    WH["Warehouse"]
    DA["Dashboards"]
    SA --> DC
    BH --> DC
    ME --> DC
    DC --> WH
    HD -->|pushed| WH
    ML -->|fetched| WH
    CO -->|fetched| WH
    BR -->|fetched| WH
    WH --> DA
    class SA,BH,ME,HD,ML,CO,BR,LT,PT,CA,NV,HH,DC,WH,DA internal-link;
```

The location tracker keeps its own record. Nothing loads it into the warehouse.
