---
reviewed: 2026-11-24
summary: What this is for, where each kind of thing lives, the one privacy rule, and how to pick up the work.
created: 2026-11-24T21:00
---

# Handbook

How things run here, and where everything is. For you after a week away, and for any agent that starts with no context.

It is built like the vault: a note's properties say what it is, and tables come from the properties. How pages are written: [Handbook](Systems/Handbook.md).

## What it is for

A second brain: something that knows what is going on, so you can spend your time well and be present. It is a tool, not the project of your life.

## Where each kind of thing lives

| Home | The single home for | Who writes |
| --- | --- | --- |
| This handbook | What spans repos, and how things run | Agents, through pull requests; you |
| Each code repo | Code, and pages a change to that code could make wrong | Agents, in the same pull request |
| [The board](Systems/Board.md) | What is to do for the build, and who has it | You and agents |
| The vault | Your own knowledge, private | You; the assistant in its own folder |
| The task app | Personal tasks, private | You and the assistant |

A thing is written once. Everywhere else links to it.

## The one rule

Private data only reaches models you trust with it. Notes, mail, calendar, personal tasks, location and health are private. Code, the homelab, the board and this handbook are general. Information goes from general to private, never back. Nothing private is written here, on the board or in a code repo.

## Picking up the work

1. Read this page, then the page of the system you will touch, in [Systems](Systems/).
2. Read [the board](Systems/Board.md). In progress holds at most three outcomes.
3. Work in a branch and a pull request. Someone other than the author reviews what changes behaviour. Rules for agents: [Workshop](Systems/Workshop.md).
4. Finish by updating the record: the task, and any page your change made wrong.

## Keeping it small

- Three outcomes in progress at most. A new idea goes to the backlog.
- Every outcome has a "done when".
- Building happens in its blocks: three of 90 minutes a week.

## Browse

- [Systems](Systems/): one page per thing that runs.
- [Repos](Repos/): one page per code repo.
- [Decisions](Decisions/): one page per decision.
- In Obsidian: [Pages.base](Templates/Bases/Pages.base) lists every page, the longest unreviewed first.
