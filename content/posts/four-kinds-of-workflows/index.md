---
title: "Four Kinds of Workflows"
date: 2026-07-30
description: "\"Workflow\" names three different things your organization owns — and a fourth that borrowed the word by accident. Confusing them is why engineering tools get mistaken for strategy."
tags: ["BPT", "architecture", "DBJ Method", "workflow"]
author: "Dusan B. Jovanovic"
cover:
  image: "dbj_bpt_left_to_right.png"
---

{{< callout type="important" >}}
When someone says "we have a workflow for that," they mean one of three things. Ask which. The answer tells you whether you are looking at a business decision, a description of one, or a piece of plumbing.
{{< /callout >}}

## One word, three jobs

Start with something older than software.

A **workflow** was a paper routing slip. A form moves desk to desk: approve, stamp, forward to accounting. Each desk does one step. The slip records where it is and what has already happened to it. If a clerk quits mid-task, someone finds the slip in the in-tray and picks it up, because the state is written on it.

That is the whole idea. Steps, order, a record of position, and a rule for what happens when someone drops it.

Every modern use of the word is a descendant of that slip, but they have drifted so far apart that they now name different things owned by different people:

1. **The operational loop.** The rhythm by which your organization decides what to build and confirms it was worth building. In [DBJ Method](https://method.dbj.org/index) this is [BPT](https://method.dbj.org/bpt). It is governance — the "what" and the "why." It is not a diagram and not code, and it is the only one of the three the board actually owns.

2. **The description.** A business analyst's diagram of a process, drawn so that stakeholders agree on what the process *is* before anyone builds it. This is the Product domain's tool. It exists to be read by humans and handed to engineers.

3. **The plumbing.** Software that keeps track of long-running work — which step a job reached, what to do when a server dies mid-job. It lives entirely in Technology. It is optional. Products get built without it.

These are not three views of one thing. They sit at different levels of abstraction, they are owned by different people, and they fail in different ways.

## Why the confusion is expensive

Because the word is shared, the plumbing gets mistaken for the governance.

An engineering team adopts a workflow engine and reports that the company "now has workflow." A board hears that a process problem has been addressed. It has not. A tool was installed in Technology. The operational loop — who decides, on what evidence, how often — is untouched.

The reverse costs just as much. A business rule changes at the loop level. The description in Product needs updating. The plumbing in Technology usually does not, because it executes whatever logic it is handed; it does not know what the logic *means*. Teams that conflate the layers rebuild the plumbing every time a policy changes, and cannot explain why the bill keeps arriving.

Lower levels do not redefine higher ones. That is the general principle, and it is the same reason architecture is not a system — architecture is the formal *description* of a system.

{{< callout type="tip" >}}
In a vendor conversation, "we have a workflow for that" is not an answer. If it is a diagramming tool, that belongs to Product. If it is an execution engine, that belongs to Technology — useful, optional, replaceable. Neither is your operational loop.
{{< /callout >}}

## And a fourth that took the name

There is a fourth thing wearing this word, and it is the one causing the most noise right now.

Around 2019 a category of software started calling itself **durable execution** — and, interchangeably, "workflow." It is not a workflow in any of the three senses above. It solves one narrow engineering problem: a program running in memory forgets everything when it crashes, so the work needs to be written down somewhere that survives the crash.

It does not describe a process or govern anything. It keeps a record so that work survives a crash. That is worth understanding, and it is worth keeping out of this taxonomy — the name is a historical accident and it has cost a great deal of clarity.

That story is its own post: **[Durable Execution Is Not a Workflow]({{< relref "/posts/durable-execution" >}})**.

## The takeaway

When a customer's engineers say "we have a workflow for that," ask which one they mean. Exactly the same when they say "we have an architecture for that." They usually don't.

Once you separate the three by the level of abstraction they cover, most of the confusion dissolves on its own — and the fourth stops pretending to be strategy.

---

## Appendix — the technical cut

For readers who want the engineering framing rather than the governance one.

### The same three, in BPT terms

![DBJ Taxonomy](https://method.dbj.org/assets/dbj-methodology-clogs.png)

- **WFL2026** — the implementation artifact. [Dapr](https://dapr.io/), [Temporal](https://temporal.io/) and relatives: code-first durable orchestration for distributed systems, promising persistent state, survived crashes, managed retries. It exists because modern applications are constellations of microservices and AI agents landing in production as containers, and something has to track where each one is *right now*. Lives entirely in **Technology (T)**. Optional.
- **The analytical workflow** — [Cawemo](https://cawemo.com/), [BPMN](https://www.omg.org/spec/BPMN/). A description used to align stakeholders, belonging to **Product (P)**, produced by business analysts in a form the T domain can consume. **Business (B)** does not need this tool; TOGAF's Business Architecture is one segment among eight, and workflow is barely in it.
- **BPT** — not a workflow at all. The governance structure that deliberately decouples B from T with P as the bridge.

### Why the implementation artifact does not leak upward

WFL2026 sits in T. If a business rule changes at the BPT loop level, the logical flow in P may need updating — but the physical workflow in T is a black box that executes whatever logic it is given. The loop does not notice and should not have to. WFL2026 consists of implementation artifacts at a lower level of granularity.

Treating WFL2026 as encapsulated in T — something that turns T's definitions into stateful, recoverable reality — keeps the boundary clean. The operational loop governs; the implementation artifact executes.

### The two axes

Engineers usually cut this space differently, by scope and by persistence:

|            | Business scope | Technology scope |
|:---:|---|---|
|            | **Macro** | **Micro** |
| **Durable** | BPMN/BPEL engine, persisted process state (Camunda, legacy BPEL) | Temporal, DBOS, Azure Durable Functions |
| **Standard** | Paper/manual process, or BPMN diagram with no persistence guarantee | Plain function call chain, no crash recovery |

This is a useful cut for choosing tools. It is not a useful cut for deciding ownership, because it says nothing about who is accountable for the result — which is the question the three-way split above answers.
