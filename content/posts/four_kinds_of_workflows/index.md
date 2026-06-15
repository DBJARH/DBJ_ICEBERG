---
title: "Four Kinds of Workflows"
date: 2026-06-13
description: "Workflow means different things at different levels of abstraction. The DBJ Taxonomy splits it into four — confusing them is why engineering tools get mistaken for strategy."
tags: ["BPT", "architecture", "DBJ Method", "workflow"]
author: "Dusan B. Jovanovic"
cover:
  image: "dbj_bpt_left_to_right.png"
---

## Summary

"Workflow" is one word doing four jobs, and the collision is costing organizations clarity about what they actually own. Here's the untangling.

Just as we have different kinds of Architecture, we have different kind of Workflows. Again, [DBJ Taxonomy](https://method.dbj.org/taxonomy) brings order to the confusion. Feasibility replaces the struggle of intertwined responsibilities. And the required precondition of the functioning [BPT](https://method.dbj.org/bpt) (aka "the Loop"), of the [DBJ Method](https://method.dbj.org/index) Operating Model of the AI Readiness.

## Four things, one word

1. **WORKFLOW 2026 abbr. WFL2026 — the implementation artifact.** Epitomized in [Dapr](https://dapr.io/) and [Temporal](https://temporal.io/), and their relatives: code-first, durable orchestration for distributed systems. It is a promise of persistent state, survived crashes, managed retries. It exists because modern applications are shaping up as constellations of microservices and AI agents landing in production as containers; and someone has to keep track of where each one is "right now" in its execution. **WFL2026** lives entirely in the **Technology (T)** domain of the BPT op model. And it's optional — a product can be built without it.
2. **The analytical workflow — a Business Analyst's tool.** This is the diagram in [Cawemo](https://cawemo.com/) or a [BPMN](https://www.omg.org/spec/BPMN/) chart: **a description used to align stakeholders on a business process**. It belongs to the **Product (P)** domain, the domain of Business Analysts, who use it to detail and describe the business logic, in a form that will be consumed by the Technology (T) domain. **Business (B)** itself — the domain of business roles — doesn't need this tool. TOGAF's Business Architecture is one segment among eight; workflow is barely in it.
3. **[BPT](https://method.dbj.org/bpt) — the Operational Loop.** Not a workflow at all. BPT is the governance structure that deliberately decouples B from T, with P as the bridge. It's the "what" and "why" — the rhythm and viability of the organization — not a diagram and not code.
4. **TODO — the fourth category from the DBJ Taxonomy.**

![](https://method.dbj.org/assets/dbj-methodology-clogs.png)

Calling all four "workflow" is the unfortunate terminology overflow. Once you separate them by the level of abstraction they cover, a lot of confusion dissolves on its own.

## Why the implementation artifact doesn't leak upward

WFL2026 sits in the T domain of the BPT. If a business rule changes at the BPT, Loop level, the logical flow in P may need updating — but the physical (application) workflow in T appears as a black box that executes whatever logic it's given. The BPT loop doesn't notice and shouldn't have to. WFL2026 consist of implementation artifacts on a lower levels of granularity.

![](dbj_bpt_left_to_right.png)

This is the same principle as architecture generally: lower levels of abstraction don't redefine higher ones. (And a correction worth keeping precise — architecture isn't *a system*, deterministic or otherwise. Architecture is the **formal description** of a system and its parts.)

Treating WFL2026 as encapsulated in the (T) domain — something that turns the T's definitions into stateful, recoverable reality — keeps the boundary clean. The Operational Loop governs; the implementation artifact executes.

## The takeaway

When a customer's engineers say "we have a workflow for that," ask which one they mean. Exactly the same when they say "we have an architecture for that". They actually don't. If it's [Temporal](https://temporal.io/) or [Dapr](https://dapr.io/), that's the engine room artefact — useful, optional, and replaceable. If it's a [Cawemo](https://cawemo.com/) diagram, that's territory that belongs to Product people — even if not established as the Product domain. And no BPT Loop exists yet to claim it. Neither of those is [BPT](https://method.dbj.org/bpt) in action.
