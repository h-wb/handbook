---
area: "[[Homelab]]"
categories:
  - "[[Repos]]"
reviewed: 2026-11-24
summary: Every machine's setup and every agent's configuration, applied with one command.
topics:
  - "[[Agent memory]]"
  - "[[Device collector]]"
  - "[[Model gateway]]"
  - "[[Notes vault]]"
  - "[[Tool gateway]]"
  - "[[Workshop]]"
url: https://github.com/h-wb/dotfiles
created: 2026-11-24T21:00
---

# dotfiles

What runs on your own machines and in the workshop pods: tools, settings, the collector's configuration, the tool and memory servers and keys each agent gets, per scope, and which [skills](skills.md) each machine and pod declares. mise applies it all, from one bootstrap for every machine.

Agents start with its [AGENTS.md](https://github.com/h-wb/dotfiles/blob/master/AGENTS.md). Its [README.md](https://github.com/h-wb/dotfiles/blob/master/README.md) lists the machines and links each machine's page; how it uses mise is [docs/mise.md](https://github.com/h-wb/dotfiles/blob/master/docs/mise.md), agent configuration is [conf.d/ai/README.md](https://github.com/h-wb/dotfiles/blob/master/conf.d/ai/README.md), and Proton Pass sessions and vaults are [conf.d/proton-pass/README.md](https://github.com/h-wb/dotfiles/blob/master/conf.d/proton-pass/README.md).

The pods it configures are deployed from home-ops.
