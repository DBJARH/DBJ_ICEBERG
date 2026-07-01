---
title: "Do we have the right set of skills"
date: 2026-07-01
description: "Skill is a runtime artifact, not a deployment one — and that's the key theme keeping the whole agent harness non-deterministic."
tags: ["agents", "architecture", "AI"]
author: "Dusan B. Jovanovic"
cover:
  image: "do-we-have-the-right-set-of-skills.png"
---

## Observations and Comments

1. Observation: runtime infrastructure != deployment infrastructure
   1. Agreed. In the era of the general lack of experienced engineers that has to be said. Plainly.
2. Observation: Skill is runtime artifact. That is the key problem keeping the whole agent harness non-deterministic
   1. It's not Skill, it's the inherent mechanism Skill is used by — fuzzy natural-language matching against a description, decided by the model at invocation time rather than fixed dispatch. 
    2. That same mechanism is what makes deferred-tool loading (ToolSearch), subagent selection. Also the ordinary tool choice (Grep vs Read vs Agent) non-deterministic too. 
    3. Skills are just the most visible facet of the LLM non-determinism because they're named and listed explicitly. But used non deterministically.
        1. The classical-software analogue is late binding / reflection-based plugin dispatch
        2. Trading a fixed call graph for runtime flexibility, and paying for it in determinism missing. 
    4. It is not "Skill" that is the problem, it is that harness resolves most capability binding (skills, tools, subagents, memory recall) via probabilistic matching instead of a deterministic dispatch table — and that's a structural property of the whole LLM architecture, not a flaw isolated to the Skills.
    5. There is no deterministic table dispatch. It is as simple as that






