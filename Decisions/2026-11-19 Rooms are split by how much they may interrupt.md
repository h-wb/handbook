---
area: "[[Homelab]]"
categories:
  - "[[Decisions]]"
summary: The assistant's rooms differ by how much they may interrupt, not by topic, so muting per room does the work.
topics:
  - "[[Assistant]]"
  - "[[Messaging app]]"
created: 2026-11-24T15:30
---

# Rooms are split by how much they may interrupt

## Context

The [messaging app](../Systems/Messaging%20app.md) mutes per room. Rooms split by topic make a reminder and a weekly review buzz the same way.

## Decision

| Room | What lands there | Phone notification |
| --- | --- | --- |
| Now | Something starting soon, one well-timed prompt, a question it is blocked on | On: the only room that buzzes |
| Daily | Briefing, midday, evening check-in, weekly review, what it changed on its own | Off |
| Chat | Conversations you start | Replies only |
| Homelab | Alerts and cluster talk | Off |

## Consequences

- Every room talks to the same assistant, with the same instructions, tools and memory, but each is its own conversation. What it knows therefore lives outside the chats, in the stores every room reads.
- Today the rooms are Inbox, Chat and Homelab, and every routine delivers to Inbox. Building Now and Daily is the first step of [The aware assistant](../Plans/The%20aware%20assistant.md).
