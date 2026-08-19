---
title: "BPT simply and feasibly applied"
date: 2026-08-07
description: "Example of an organization feasibly following BPT operational model. Company is anchored in a mature AI dev environment. Contrasted to the anti-pattern most post-ai-pilot organizations are self exposed to."
tags: ["DBJ", "BPT", "AI", "Method", "Operational Model", "Product", "Development"]
author: "Dusan B. Jovanovic"
version: 0.4
featured: true
cover:
  image: "bpt-and-escalation.png"
---

## The value of the BPT 

<span style="font-size:2rem;">T</span>hink about it. Everything revolves around a "Product". Business/Industry/Investors, all actors think in terms of Products. Not Software, Architectural or some other  artifacts. After  Business decided they know WHY do the need it, product owners and business analyst are iterating to define WHAT business wants. Just then it is feasible to deploy the consistent plan to the Technology people, to decide HOW will it be done. The better information they have the less time they will spend iterating to "understand the thing". Better means detailed, articulated, with requirements managed and clarified. No ambiguities.

The image above is an product development Operational Model, inside an (well behaved and organized) company. Company that has adopted and implemented the BPT and has learned how to use an LLM, and how not to. Crucially under the [guidance of the "BPT Method"](https://method.dbj.org/kb/BPT_Operational_Model/engagement_architecture/index).

> **Caveat Emptor**: DBJ BPT is not "[Product Driven Development](https://www.lyssna.com/blog/product-driven-development/)". [DBJ BPT](https://method.dbj.org/onboarding/section-03.html) is (much) wider in scope. It is organizational  operational model. Basically if adopted it changes the whole organization. And delivers ROI. AI or no AI.

Three domains, each iterating with the next, to produce two main artifact  `goal.md` and the  `plan.md` . Iterations can produce more but these are two main two.

1. **`chat.md`** — freeform exploration. Confusion belongs here. Where the organization stake holders find out what do they not understand. WHY do they want the Product.
   1. Very often it is iterated only over between "Business" and the "Product"
2. **`goal.md`** — the distilled goal statement artifact. Architecture gets involved. Iterating between Business and Product teams, the public deliverable, signed and staying
   1. Now note the **Exceptions**. Note the optional cascading and the overall effect.
      1. BPT Exceptions are "all hands" events carrying the full trace: where it happened, and what has happened
         1. BPT Exception is caught by the domain where it originated from. Because non Engineering roles missed the problem that caused the Exception being thrown "down the line". 
            1. That is  BPT Agility, inbuilt backtracking events
   2. Exception are operating model mechanisms. 
   3. Carrying the information used to discover and solve the cause. 
      1. To notice and rectify the expensive mistakes, on the level of organization, not inside the Technology domain which has no view into the domains that cause the Sequence of Event that led to a Exception.
3. **`plan.md`** — the concrete implementation plan, made by roles in the Product team. Business Analyst being the important role.
   1. Steps, dependencies, order. Iterating between Product and Technology team until it is agreed. 
      1. At this stage Product team has the visibility of the goal.md and can go back to Business to reconfirm the decisions or to provoke the goal.md revisiting.

After seeing the product release in production, someone can say: "This is not what I wanted". Engineering role "throws" the  BPT Exception out of the technology domain. Full information on the "Product" (previous) domain is available, as it was the formal request to develop and deliver.

1. Important BPT Model feature: each technology product review activity will be able to throw the Exception back to the Product domain.
2. Eventually arriving to the Business, if Product demands. 
   1. Top accountable domain.
3. Exception cascading is propagating with the full trace back, all the way to the business decisions and the product team decisions.
4. This is very powerful capability of the BPT OP Model: going back to the real source of an issue. 
   1. Outside of the confines of the technology.

Design, then code. Mature idea. 

1. Origins are in the good old primordial loop
   1. Design, implement, review, repeat. 
2. But 
   1. tightly monitored.Simple and stoppable. 
   

What is critical is that domain Business and Product are sending fully articulated product declaration and requirements artifacts. For the Product to be factorized inside the Technology domain.

Very malleable for a mature AI development where the model is given a goal and a plan, not a wish. That is not a prompt and pray, anti-pattern

Please note what this is not. It is not a tooling standard. It is not a LLM recommendation or choice. BPT model defines domains, named artifacts, and roles ownership at each step. 

With a internal backtrace loop made possible by the Exception feature — the simple operational model made visible at the level of the organization owning the outcome. 

And the outcome is the Product. Hence the "Product Factory" name.

There are various kinds of Products. Change the artifacts structure and the same Operating Model governs procurement, or claims, or onboarding. Not just public software products. 

## Do not Prompt and Pray

Market pressure is tremendous. A clear and colossal mistake, many organizations do make right now. Unfortunately. 

Someone opens a chat window, types "just build the thing," and "prays". 

No KPIs. No defined input. No defined output. No way to separate success from failure. The model produces something. Nobody can say whether it is correct, because there is nobody who can say what correct means. When it fails, the finding is "the AI model was not good enough," which was never the actual cause.

This is not an AI problem. It is a legacy undefined process just running faster. 

### Why do we care

At least half of the organizations currently in AI post-pilot "zero ROI" mode are following the "Prompt and pray" strategy. There are licenses for tokens to spend, the AI team. They ran the pilot, no KPI of the outcome. 

It is a success, and it is scaled out — spreading the anti-pattern on the company level. Costs we have seen can be catastrophical.

## The Summary

BPT information flow is two iterations between the three domains. BPT is not a sequence, it is a loop: the two artifacts are not a waterfall sequence. Namely `goal.md` and `plan.md` are the artifacts produced by updating as a result of iterating between domains. And each carries a named roles and origin information across a boundary. 

To be used by Exception throwing and by Exception solving.

`goal.md` and `plan.md` are boundary artifacts; each carries the information passed between two domains. 

**Scalability**. BPT scales. An organization can run these three domains separately, for a product needing one developer and one feature; equally sensibly as for a whole business unit or a transformation programme. BPT Loops are multiple and running in parallel. It all depends on the size and complexity of the organization.

**Product Maintenance** is the most expensive stage of the product lifecycle. BPT loop, categorizes and saves crucial information for the maintenance stage.

It is very easy to restart the paused loop. There are artifacts and information needed.

If you want to know whether an organization is AI-ready, do not audit the tooling. Watch someone use it. If there is no visible op model, you are looking at the problem.

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
<!-- - **Gate** — a point in a process that cannot be passed until a stated condition is met. Its value is entirely in being enforced. -->
- **BPT Exception** — an event thrown by a role when the work received does not match what was asked for. It carries the full trace back to the domain where the cause originated, so the fix happens there, not where the symptom appeared.
- **Anti-pattern** — a common response to a recurring problem that is usually ineffective and often counterproductive.
