---
area: "[[Homelab]]"
categories:
  - "[[Repos]]"
reviewed: 2026-11-25
summary: The skills more than one agent runs, written once and grouped; each place declares the groups it takes.
topics:
  - "[[Assistant]]"
  - "[[Workshop]]"
url: https://github.com/h-wb/skills
created: 2026-11-25T01:00
---

# skills

The skills agents share, one folder `skills/<name>/SKILL.md` each, in the Agent Skills format: `handbook`, `board`, `tool-gateway`, `orchestrate` and `paseo-workspace-hygiene`. Skills come in groups, `groups/<group>/<name>`, each entry a link to the skill: `core` (`handbook`, `board`, `tool-gateway`) and `workshop` (`orchestrate`, `paseo-workspace-hygiene`). A skill reaches an agent only through a group: each place declares the groups it takes, never single skills. Why skills are kept this way, and who takes which: [Workshop](../Systems/Workshop.md#the-shared-skills).

Agents start with its [AGENTS.md](https://github.com/h-wb/skills/blob/main/AGENTS.md). Its [README.md](https://github.com/h-wb/skills/blob/main/README.md) lists the skills and groups and says how each harness reads them, including a plugin install for a machine without dotfiles.

The machines and the workshop pods take their groups through [dotfiles](dotfiles.md), which follows `main`; the assistant takes its own through a sync job in [home-ops](home-ops.md), at a pinned commit.
