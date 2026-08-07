---
title: "A Concrete Application"
date: 2026-08-07
description: "One image: an organization following BPT operational model. In a mature AI dev environment. Contrasted to  the anti-pattern most post-ai-pilot organizations are self exposed to."
tags: ["DBJ", "BPT", "AI", "Method", "Operational Model", "Product", "Development"]
author: "Dusan B. Jovanovic"
version: 0.4
featured: true
cover:
  image: "bpt-in-mature-ai-dev-env.png"
---

When you think about it. Everything revolves around a Product. Business/Industry/Investors think in terms of Products. Not Software artifacts. Product Owners and Business analyst are cycling to define WHAT business wants. Just then it is feasible to deploy the Technology people for will decide HOW will it be done. The better information they have the less time they will spend (aka waste) to "build the thing". Better means detailed, articulated, with requirements clarified.

The image above is product development, inside an (well behaved) organization that has adopted BPT and has learned how to use an LLM, and how not to. Crucially under the guidance of the "BPT Loop".

## The Top Half: BPT Applied

Four stages, each producing an owned artifact:

1. **`chat.md`** — freeform exploration. Confusion belongs here, and only here. This is where the organization finds out what it does not yet understand. WHY do they want the Product.
2. **`goal.md`** — the distilled goal statement. Architecture, stated. Cycling between Business and Product team until it is agreed.
3. **`plan.md`** — the concrete implementation plan. Steps, dependencies, order. Cycling between Product and Technology team until it is agreed. At this stage Product team has the visibility of the goal.md and can go back to Business to reconfirm the decisions or to provoke the goal.md revisiting.
4. **The loop** — implement, review, repeat. Bounded and stoppable, because stage 2 defined what done means. 
   1. Most important: each review will be able to backtrace two step back, to the origin. 
   2. Full trace back: the business decisions the product team decisions.
   3. This is very powerful OP Model capability: going back to the real source of an issue.

Design, then code. Not a new idea. What is critical is that stages 1 and 2 are now, sending product declaration artifacts, because the LLM is the consumer of them. A mature AI development environment is one where the model is given a goal and a plan, not a wish. That applied ever before, by the way.

Please note what this is not. It is not a tooling standard. It is not a LLM recommendation or choice. BPT defines stages, named artifacts, and ownership at each step, with a internal review loop with a stopping condition — the operational model made visible at the level of organization governing the outcome of one Product. 

There are various kinds of Products. Change the information artifacts and the same OP Model governs procurement, or claims, or onboarding. Not just public software products. 

## Warning: Prompt and Pray

Market pressure is tremendous. On the same image there is an anti-pattern. One can see them both and compare straight away. A clear and colossal mistake, unfortunately many organizations do make right now. 

Someone opens a chat window, types "just build the thing," and "prays" the AI hype is not a hype.

No defined input. No defined output. No way to separate success from failure. The model produces something. Nobody can say whether it is correct, because there is nobody who can say what correct means. When it fails, the finding is "the AI model is not good enough," which is never the actual cause.

This is not an AI problem. It is an undefined process running faster. Producing the puzzle.

## Why do we care 2026 Q2

At least half of the organizations currently in AI post-pilot zero ROI mode are running the bottom half. They have the licenses for tokens to spend, the AI team, the internal enablement deck. They ran the pilot, declared it a success, and scaled out — taking the anti-pattern with them. Costs we have seen can be catastrophical.

The pilot "succeeded" in a setting small enough where one person held the goal in their head. There was no `goal.md` because there did not need to be. Scaling that same process to an organization removes the only thing that was holding it together, and no amount of budget replaces it.

## The Summary

Information flow is two ways between the domains. BPT is not a sequence, it is a loop: the four artifacts are not just a sequence. Namely `goal.md` and `plan.md` are the artifacts carrying information between domains, and each carries a named roles across a boundary. 

In that BPT implementation `goal.md` and `plan.md` are boundary artifacts; each is the information passed between two domains. That is what makes them logical gates: a domain cannot function without one.

BPT scales. An organization can run these four stages for one developer and one feature, equally sensibly as for a business unit and a transformation programme.

**Maintenance stage** is the most expensive stage of the product lifecycle. BPT categorizes and saves crucial information for the maintenance stage.

If you want to know whether an organization is AI-ready, do not audit the tooling. Watch someone use it. If there is no visible op model, you are looking at the bottom half of the image.

---

## Vocabulary

- **BPT** — Business Process Transformation. In the DBJ Method it is an *operational model*: how the organization actually runs. Defined processes, named artifacts, clear decision rights, ownership, governed data. See the [BPT onboarding](https://method.dbj.org/onboarding/section-03.html).
- **Operational model** — the description of how an organization does its work day to day. Distinct from the business model, which is what it sells and to whom.
- **Post-pilot mode** — the state after an AI pilot has been declared a success and rollout has been funded, but before anyone has checked whether the process that made the pilot work survives being scaled.
- **Gate** — a point in a process that cannot be passed until a stated condition is met. Its value is entirely in being enforced.
- **Anti-pattern** — a common response to a recurring problem that is usually ineffective and often counterproductive.
