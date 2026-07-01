---
title: "Observations on Skills"
date: 2026-07-01
description: "Skill is a runtime artifact, not a deployment one — and that's the key theme keeping the whole agent harness non-deterministic."
tags: ["agents", "architecture", "AI"]
author: "Dusan B. Jovanovic"
cover:
  image: "image.png"
---

## My Observations

1. runtime infrastructure != deployment infrastructure
2. Skill is runtime artifact. That is the key problem keeping the whole agent harness non-deterministic

## My Comments

1. Agreed. In the era of the general lack of experienced engineers that has to be said. Plainly.
2. Right but I'd widen the diagnosis slightly: it's not Skill specifically, it's the inherent mechanism Skill is used by — fuzzy natural-language matching against a description, decided by the model at invocation time rather than fixed dispatch. 
    1. That same mechanism is what makes deferred-tool loading (ToolSearch), subagent selection. Also the ordinary tool choice (Grep vs Read vs Agent) non-deterministic too. 
    1. Skills are just the most visible facet of the LLM non-determinism because they're named and listed explicitly.
        1. The classical-software analogue is late binding / reflection-based plugin dispatch — you trade a fixed call graph for runtime flexibility, and you always pay for it in determinism and debuggability. 
    2. The sharper version: it's not "Skill" that's the problem, it's that harness resolves most capability binding (skills, tools, subagents, memory recall) via probabilistic matching instead of a deterministic dispatch table — and that's a structural property of the whole architecture, not a flaw isolated to the Skill feature.
    3. There is no deterministic table dispatch

