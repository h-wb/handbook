---
area: "[[Homelab]]"
categories:
  - "[[Decisions]]"
summary: Matrix replaced Telegram and iMessage; the homeserver is ours and federates with Beeper only.
topics:
  - "[[Messaging app]]"
  - "[[Assistant]]"
created: 2026-11-24T15:30
---

# The assistant is reached on Matrix, on our own homeserver

## Context

On 2026-11-09 the [assistant](../Systems/Assistant.md) was to be reached through a messaging app; on 2026-11-10 the choice was Telegram and iMessage. Telegram's bot chats are not end-to-end encrypted, so its servers could read them. iMessage needed a second Apple ID and an always-awake Mac.

## Decision

- [Matrix](../Systems/Messaging%20app.md) only. Messaging and the routines moved there and Telegram was switched off on 2026-11-11.
- The homeserver is our own, Continuwuity, and federates with Beeper only. You talk to the assistant from Beeper, whose account is a Matrix account, or from any Matrix app signed in to our server.
- The chats are end-to-end encrypted, and the assistant answers only the accounts on its allow list.

## Consequences

- The assistant's pod reaches nothing on the internet. The homeserver is public, because Beeper reaches it over federation.
- Its dashboard, on the LAN and tailnet only, is a second way in.
- Setup and accounts: [Hermes](https://github.com/h-wb/home-ops/blob/main/kubernetes/apps/main/llm/hermes/README.md#messaging) in home-ops.
