---
title: "The Business Ship Manual"
date: 2026-06-15
description: "BPT explained through one analogy: the bridge, the engine room, and the operational manual the whole ship runs on."
tags: ["BPT", "architecture", "DBJ Method", "workflow"]
author: "Dusan B. Jovanovic"
cover:
  image: "prepared-ship.png"
---


## The Flight Plan and the Autopilot

#### The elusive goal of the "Competitive Advantage"

> What will "give" the "competitive advantage" is the **Operational model**, in order to navigate the whole organization around that huge iceberg of legacy.
>
> https://method.dbj.org/shop/
>
> OP model introduction is not simple. But its worth it. Especially if organization is small(ish) and not too calcified. Just decide on one OP model, implement it and follow it. AI or no AI.
> 

Most customers have never thought about an "operational model" as something they need to know about. BPT is new to them. So let's skip the taxonomy and use an analogy:

- **BPT Operational Loop = the Flight Plan.** The strategic path. How the organization spots an opportunity, builds something, and validates it. Not a software diagram.
- **The Autopilot.** The AI Agents Machinery that keeps execution on course through turbulence — service crashes, timeouts, retries — without the human ship pilot manually steering every adjustment.

The narrative that lands well with new customers:

1. **"We don't draw our code."** Business intent is too valuable to bury it in technical diagrams. BPT keeps business knowledge clean and independent of whatever implements it.
2. **"The technology is a black-box helper."** Development products are not for business process modeling. They are software shock absorbers, used so that when part of the system fails, it remembers where it was and recovers the low level design.
3. **"Separation of concerns is the goal."** Force business rules into a executable workflow engine, and you lose agility — you can't change the business without tearing down the technology.

## The Ship Analogy

**TOGAF is the sextant.** The Enterprise Architect is the navigator who reads it. The C-room steers the ship. **BPT is the set of behavioral rules in the operational manual** — how the whole crew is expected to run things, regardless of which instruments are belowdecks.

<!-- ![The TOGAF sextant, the navigator, and the C-room steering toward the BPT operational loop](image.png) -->

To be allowed on the bridge, crew must pass the DBJ CMM course. Based on TOGAF CMM, but adjusted for the business, So now the whole ship operates at CMM Level 5 — not just the navigator.

Below deck, in the **Technology engine room**, is where the technical artifact live: services, microservices and agents it coordinates, encrypted comms, stateful storage, modern low level "workflows as code". None of it is visible from the bridge, and none of it should need to be.

## The takeaway

BPT is the operational manual. It doesn't live in a repo, and it doesn't get exported as BPMN XML. It's the operational manual the whole ship runs on.
