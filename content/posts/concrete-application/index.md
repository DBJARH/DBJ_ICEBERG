---
title: "A Concrete Application"
date: 2026-08-07
description: An organization following BPT operational model. Anchored in a mature AI dev environment. Contrasted to  the anti-pattern most post-ai-pilot organizations are self exposed to."
tags: ["DBJ", "BPT", "AI", "Method", "Operational Model", "Product", "Development"]
author: "Dusan B. Jovanovic"
version: 0.4
featured: true
cover:
  image: "bpt-in-mature-ai-dev-env.png"
---

<span style="font-size:2rem;">W</span>hen you think about it. Everything revolves around a "Product". Business/Industry/Investors, all think in terms of Products. Not Software, Architectural or some other  artifacts. After  Business decided they know WHY do the need it, product owners and business analyst are iterating to define WHAT business wants. Just then it is feasible to deploy the consistent plan to the Technology people, to decide HOW will it be done. The better information they have the less time they will spend iterating to "understand the thing". Better means detailed, articulated, with requirements managed and clarified. No ambiguities.

The image above is an product development, inside an (well behaved and organized) company; that has adopted and implemented the BPT and has learned how to use an LLM, and how not to. Crucially under the [guidance of the "BPT Method"](https://method.dbj.org/kb/BPT_Operational_Model/engagement_architecture/index).

## The Top Half: BPT Applied

Four stages, each iterating to produce an artifact:

1. **`chat.md`** — freeform exploration. Confusion belongs here, and only here. This is where the organization finds out what it does not yet understand. WHY do they want the Product.
2. **`goal.md`** — the distilled goal statement. Architecture, stated. Iterating between Business and Product team until it is agreed.
3. **`plan.md`** — the concrete implementation plan. Steps, dependencies, order. Iterating between Product and Technology team until it is agreed. At this stage Product team has the visibility of the goal.md and can go back to Business to reconfirm the decisions or to provoke the goal.md revisiting.
4. **The primordial loop** — implement, review, repeat. Simple and stoppable. 
   1. Most important: each technology product review activity will be able to backtrace, to the origin. Business is accountable.
   2. Full trace back, when some says: "This is not what I wanted": all the way to the business decisions and the product team decisions.
   3. This is very powerful capability of the BPT OP Model: going back to the real source of an issue. Outside of the confines of the technology.

Design, then code. Not a new idea. What is critical is that stages B and P are now, sending fully articulated product declaration artifacts. very malleable for a mature AI development where the model is given a goal and a plan, not a wish. Not prompt and pray.

Please note what this is not. It is not a tooling standard. It is not a LLM recommendation or choice. BPT defines stages, named artifacts, and ownership at each step, with a internal review loop with backtrace feature — the simple operational model made visible at the level of everyone in the organization owning the outcome . 

There are various kinds of Products. Change the information artifacts and the same OP Model governs procurement, or claims, or onboarding. Not just public software products. 

## Do not Prompt and Pray

Market pressure is tremendous. On the same image there is an anti-pattern. One can see them both and compare straight away. A clear and colossal mistake, unfortunately many organizations do make right now. 

Someone opens a chat window, types "just build the thing," and "prays". 

No defined input. No defined output. No way to separate success from failure. The model produces something. Nobody can say whether it is correct, because there is nobody who can say what correct means. When it fails, the finding is "the AI model was not good enough," which was never the actual cause.

This is not an AI problem. It is an undefined process running faster. Producing the puzzle. The lack of operational model.

## Why do we care 2026 Q2

At least half of the organizations currently in AI post-pilot zero ROI mode are running the bottom half. They have the licenses for tokens to spend, the AI team, the internal enablement ""something"". They ran the pilot, declared it a success, and scaled out — spreading the anti-pattern with them. Costs we have seen can be catastrophical.

The pilot "succeeded" in a setting small enough where one person held the goal in their head. There was no `goal.md` because there did not need to be. Scaling that same process to an organization removes the only thing that was holding it together, and no amount of budget can help it.

## The Summary

BPT information flow is two iterations between the three domains. BPT is not a sequence, it is a loop: the four artifacts are not a waterfall sequence. Namely `goal.md` and `plan.md` are the artifacts produced iterating between domains. And each carries a named roles and origin information across a boundary. 

**The Gates**. In this BPT implementation `goal.md` and `plan.md` are boundary artifacts; each carries the information passed between two domains. That is what makes them logical gates.

**Scalability**. BPT scales. An organization can run these three stages for one developer and one feature, equally sensibly as for a business unit or a transformation programme.

**Product Maintenance** is the most expensive stage of the product lifecycle. BPT loop, categorizes and saves crucial information for the maintenance stage.

If you want to know whether an organization is AI-ready, do not audit the tooling. Watch someone use it. If there is no visible op model, you are looking at the bottom half of the image.


> 
> &nbsp;
> 
> [CAVEAT](https://www.merriam-webster.com/dictionary/caveat): This is true but simplified DBJ BPT implementation. Organizations all have slightly different agentic harnesses, or no harnesses, or even no software products portfolio.Most have product quarterly plans, heavy JIRA managed procedures, etc. But all (and more) fit nicely into this simple and feasible operations model.
> 
> &nbsp;
>
---

## Vocabulary

- **BPT** — Business Process Transformation. In the DBJ Method it is an *operational model*: how the organization actually runs. Defined processes, named artifacts, clear decision rights, ownership, governed data. See the [BPT onboarding](https://method.dbj.org/onboarding/section-03.html).
- **Operational model** — the description of how an organization does its work day to day. Distinct from the business model, which is what it sells and to whom.
- **Post-pilot mode** — the state after an AI pilot has been declared a success and rollout has been funded, but before anyone has checked whether the process that made the pilot work survives being scaled.
- **Gate** — a point in a process that cannot be passed until a stated condition is met. Its value is entirely in being enforced.
- **Anti-pattern** — a common response to a recurring problem that is usually ineffective and often counterproductive.
