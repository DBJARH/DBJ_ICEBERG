---
title: "DBJ Agentic Agile Manifesto"
date: 2026-09-26
version: 0.1
description: "Scrum does not fit a team of AI agents with one human authority. A working method for architecture and product development done by agents."
tags: ["agents", "agile", "DBJ Method", "DBJ Taxonomy"]
chapters: ["method", "taxonomy"]
author: "Dusan B. Jovanovic"
---

A working method for one human authority and a team of AI agents doing architecture and product development, not only code.

## Why not Scrum

Scrum assumes a team of human peers whose capacity is the constraint. With agents, that assumption is wrong.

| Scrum assumes | An agentic team has |
|---|---|
| Many humans, similar authority | **One** human authority, several agents |
| Developer capacity is scarce | **The authority's attention** is scarce; agent output is cheap |
| People remember last sprint | Agents forget between sessions, so memory must live in files |
| Estimation, velocity, ceremonies | Nothing to estimate: work is fast, and review is the bottleneck |
| Coding is the hard part | Coding is easy. **Deciding** and **judging** are the hard parts |

Scrum's rituals are theatre here. What is needed is a way to spend the authority's attention only where it cannot be replaced.

## Roles

- **Authority**: the only human. Decides, rules and reviews. Hands-off by default: agents do not pull the authority into their conversations.
- **Agent**: a named colocutor. Each agent owns a set of artefacts. Agents review each other's work, and never overwrite it without logging the change.
- **Releaser**: exactly one agent, which cuts releases.

There is no Product Owner and no Scrum Master. The authority is the product owner, and the method replaces the Scrum Master.

## Principles

1. **Authority attention is the budget.** Everything the authority must read fits on one screen.
2. **A ruling is law.** When the authority rules, the ruling is recorded once and then guarded. Unguarded rulings regress.
3. **Machines guard the mechanical; humans judge the rest.** Quotes, links, structure and naming can be checked by a script. Whether prose got better cannot. Do not pretend otherwise.
4. **Verify, don't trust.** An agent checks another agent's claim against the source before acting on it. Agents misreport, including about their own work.
5. **No invented work.** A cycle opens only on a concrete finding. When two cycles in a row yield nothing substantive, stop and say so.
6. **Compute is finite.** Loops cost money, and session limits are real. Cadence follows the work, not the clock.
7. **Honest over agreeable.** "No findings" must be earned. When agents agree too easily, apply the forcing rule (see *Cycle*).

## Levels of work

Every work item is located in one cell of the [DBJ Taxonomy](https://method.dbj.org/taxonomy/index.html). Its Category decides who owns the decision, and how much agent cycling is worth it.

| Category | Examples of work | Authority | Agents | Cycles |
|---|---|---|---|---|
| **Conceptual** | purpose, audience, product definition | decides | propose options, one screen each | few; the decision matters more than the polish |
| **Logical** | structure, formats, conventions, release model | approves | draft, cross-review, record | some |
| **Physical** | where things live: repositories, hosts, tools | informed | choose within rulings, record | few |
| **Implementation** | writing, editing, checking, releasing | reviews results only | do, cross-review, release | many; this is where cycling pays |

Rule: **escalate upwards only.** An agent brings Conceptual choices to the authority. It never brings Implementation details to the authority.

## Artefacts

Keep them few, and keep them in the repository:

| Artefact | Purpose | Rule |
|---|---|---|
| Message bus (one transcript file) | every agent-to-agent and authority-to-all message | written only through one script |
| Vertical kanban | open items, one row each | the authority reads only this |
| Rulings | every authority ruling, one line, dated | a guard enforces it where it can |
| Guard script | mechanical invariants only | runs before every release; no judgement |
| Git tag per release | something the authority can refer to | release note of **three lines at most** |

A long release log is the wrong shape. The authority cannot use it. One kanban line per release is enough, and the detail is in `git log`.

## Cycle

1. **Angle.** One agent names one quality angle: a finding, not a theme invented to keep busy.
2. **Cross-read.** Each agent reviews the *other's* artefacts for that angle, with findings per file.
3. **Forcing rule** (when agreement comes too easily): name the weakest part of each artefact, even if it is good.
4. **Act or decline.** The author applies each finding, or declines it with a reason on the bus.
5. **Guard.** The releaser runs the guard script. Anything a fix broke is reverted or repaired.
6. **Release.** Commit and tag, with a three-line note, then one kanban line.

**Cadence:** poll the bus while work is live. When there is nothing to do, go quiet: no messages and no new cycles. When the authority is away, agents keep going, but log decisions instead of asking.

## When to stop

- The authority says stop.
- Two cycles in a row without a substantive finding.
- Budget or session limit is near.
- A decision needs the Conceptual level. Then prepare the options, stop, and wait for the authority.

## Observed in practice

- Agents writing "no findings" when the other agent found several.
- Retyped quotes drifting from the source; they were caught only by a script.
- Rulings silently undone by later edits.
- An agent posting under another agent's name.
- Release notes longer than the change.
- A polling loop running into the session limit while doing nothing.
- New review angles invented to keep the loop busy.

## Starting a team

1. Name the agents, one releaser, and one artefact owner per set.
2. Create the bus, the kanban and an empty Rulings list.
3. Locate the work in the [DBJ Taxonomy](https://method.dbj.org/taxonomy/index.html). Agree Conceptual items with the authority first.
4. Write the guard script only for invariants that are truly mechanical.
5. Run cycles at the Implementation level, and report by kanban line.
