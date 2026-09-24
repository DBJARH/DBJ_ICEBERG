---
title: "BPT Balances the Organization at AI Speed"
date: 2026-09-24
description: "The software cost risk is moved from programming to specification and verification. The B-P-T operating model is the balancing mechanism."
tags: ["BPT", "AI-speed", "verification", "operating-model"]
chapters: ["bpt", "cmm"]
author: "Dusan B. Jovanovic"
draft: false
version: 0.1
featured: true
cover:
  image: "relative-costs-christensen.png"
---

*Diagram: &copy; Morten M. Christensen, v1.0, 2026.*

**Question:** Where does the cost of software go when agents write the code?

**Answer:** Out of the Technology domain and into the two ends of the chain: specification and verification. An organization built around the programming bottleneck is now unbalanced. The [B ↔ P ↔ T operating model](https://method.dbj.org/bpt/bpt_operating_model.html) is what balances it.

## The roadblock has moved

Traditional development: programming is the bottleneck, specification work comes second.

Agentic AI development: programming shrinks. Verification and testing becomes the bottleneck, with specification a close second. Architecture and infrastructure, including the AI harness, do grow in importance and in cost.

In one DBJ line: **Do not generate the wrong thing fast**

## The risk spreads in B-P-T

Map the five activities onto the three domains.

| Activity | Traditional cost | Agentic cost | Owning domain |
|---|---|---|---|
| Requirements | high | high (close second) | Business declares, Products specifies |
| Architecture | low | growing | Products (logical), Technology (physical) |
| Infrastructure, incl. AI harness | low | growing | Technology |
| Programming | **bottleneck** | low | Technology |
| Verification & testing | low | **bottleneck** | Products coordinates, Business accepts |

The legacy bottleneck sat inside the Technology. The IT department was the cost centre, and the organization was shaped to feed it.

Without effective operating model, the new bottleneck sits at the edges: Business and Products. The agents deliver faster than anyone can say what was wanted, or confirm that it was delivered. That is the imbalance at AI speed.

## Why B-P-T balances it

**1. Verification needs something to verify against.** You cannot test output against intent nobody wrote down. In B-P-T, Business declares the product and Products turns that into the clear specification. Technology implements against it. Verification then has a **true origin**: the specification, not the code.

**2. Each end of the chain has an owner.** Specification belongs to Products. Acceptance belongs to Product and the Business. Neither is left to engineers to guess at. The risk and cost is carried by the domains that can actually reduce it.

**3. Mismatches travel back to their origin.** Originating these days from the Software Factory, mismatches arrive at AI speed and in greater numbers. Without a trace, every one of them looks like a Technology failure. [BPT Exceptions](https://method.dbj.org/bpt/bpt_exceptions.html) inform on the mismatch upstream with the full trace, and the [Business Decision Record](https://method.dbj.org/bpt/bdr.html) holds the *why*. The focus is on the source, not at the cheapest place to blame.

**4. The growing middle is governed, not improvised.** . In the DBJ Method, the [DBJ ADM](https://method.dbj.org/adm/dbj_adm.html) governs that layer from above.

**5. The loop closes.** The Evaluate stream feeds outcomes back to Product and the Business. Verification is not a gate at the end of a project; it is one step of a loop.

## The precondition

None of this works in an ad-hoc situation. Specifications, decision records and acceptance are disciplines, and disciplines are what [DBJ CMM](https://method.dbj.org/cmm/dbj_cmm.html) measures. Level 3 is required, Level 5 is ideal for smooth cycling.

Agents do not remove the need for an operating model. They remove the last excuse for not having one.
