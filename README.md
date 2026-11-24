---
id: start-here
type: overview
system: handbook
status: draft
summary: What the whole thing is for, where each kind of thing lives, the one privacy rule, and how to pick up the work.
created: 2026-11-24
reviewed: 2026-11-24
review_every: 30
---

# Start here

For you after a week away, and for any agent that starts with no context.

## What it is for

A second brain: something that knows what is going on, so you can spend your
time well and be present. It is a tool, not the project of your life.

## Where each kind of thing lives

| Home | The single home for | Who writes |
| --- | --- | --- |
| This handbook | What spans repos, and how we work | Agents, through pull requests; you |
| Each code repo | Code, and pages a change to that code could make wrong | Agents, in the same pull request |
| The board | What is to do for the build, and who has it | You and agents |
| Your vault | Your own knowledge, private | You; the assistant in its own folder |
| Your task app | Personal tasks, private | You and the assistant |

A thing is written once. Everywhere else links to it.

The systems and the repos are listed once, in [registry.yaml](registry.yaml).
Every page is listed in [INDEX.md](INDEX.md), which is generated.

## The one rule

Private data only reaches models you trust with it. Notes, mail, calendar,
personal tasks, location and health are private. Code, the homelab, the board
and this handbook are general. Information goes from general to private, never
back. Nothing private is written here, on the board or in a code repo.

## Picking up the work

1. Read this page, then the overview of the system you will touch, in
   [systems/](systems/).
2. Read the board. "In Progress" holds at most three outcomes.
3. Work in a branch and a pull request. Someone other than the author reviews
   what changes behaviour.
4. Finish by updating the record: the task, and any page your change made wrong.

## Keeping it small

- Three outcomes in progress at most. A new idea goes to Backlog.
- Every outcome has a "done when".
- Building happens in its blocks: three of 90 minutes a week.

## How we work

- [How we write pages](how-we-work/write-pages.md)
- [How we track work](how-we-work/track-work.md)
- [How pages stay true](how-we-work/keep-pages-true.md)
- [How agents work here](how-we-work/agents.md)
