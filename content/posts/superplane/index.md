---
title: 'SuperPlane: The Bridge Over the "Glue Abyss"'
date: 2026-06-13
description: "An open-source event-driven control plane for platform engineering — and what it gets right about operational workflows."
tags: ["platform engineering", "open source", "AI", "DevOps"]
author: "Dusan B. Jovanovic"
cover:
  image: "superplane_over_the_glue_abyss.png"
---

## The Control Plane Your Platform Team Has Been Gluing Together Manually

Platform engineering teams write a lot of glue. CI finishes — someone triggers a deploy script. An alert fires — someone pings Slack, opens a Jira, checks the last five deployments manually. A release train needs three repos to be green before the coordinated push — someone watches dashboards and hits the button when the moment looks right.

This glue lives in a dozen places: GitHub Actions, bash scripts, cron jobs, Slack bots, Rundeck, internal wikis with "runbook" in the title. It works, until it doesn't — and when it doesn't, nobody knows which piece failed or why.

SuperPlane is an open-source attempt to fix this at the source.

---

## What It Actually Is

SuperPlane calls itself a **control plane for platform engineering**. That description is accurate but undersells it. More precisely: it is an event-driven workflow orchestrator that sits across your existing toolchain and coordinates actions between them — without replacing any of them.

The core model is simple:

- A **Canvas** is a directed graph of steps. You model a workflow visually.
- **Components** are the nodes — either built-in (HTTP request, If/branch, Wait, Approval gate) or integration-backed (GitHub, PagerDuty, Datadog, Slack, AWS Lambda, and 40+ others).
- **Events** arrive as triggers: webhooks, schedules, CI completions, infrastructure alerts, issue updates.
- **Executions** run the graph, track state, and expose full history and payloads in the UI and CLI.

There is also **Memory** — built-in key/value storage that persists data across executions of the same canvas. This matters more than it sounds: it means your workflows can accumulate context, not just react to isolated events.

---

## The Problem It Solves

Consider a standard policy-gated production deploy. The intent is clear to every engineer on the team:

1. CI passes
2. Only deploy during business hours
3. Get on-call approval and product sign-off
4. Then trigger the deploy

In practice, this intent is encoded in four different places, enforced inconsistently, and completely invisible when something goes wrong at 2am.

SuperPlane puts that workflow on a Canvas. Each gate is a node. The execution trace is inspectable. The approval step blocks until it's met. The deploy step only fires when all conditions are satisfied. The entire thing is a versioned artifact, not tribal knowledge.

Other patterns that work well here:

- **Progressive delivery**: deploy to 10%, verify, promote to 30%, verify, continue — with automatic rollback gates.
- **Release trains**: fan-in across multiple repos, fire the coordinated deploy only when all builds are green.
- **Incident triage**: on incident open, in parallel: fetch recent deploys, pull health signals, generate an evidence pack, open a Jira — before a human even looks at it.

---

## What Makes This Different

The honest comparison is against GitHub Actions, Argo Workflows, or Temporal.

GitHub Actions is per-repo, not cross-system. It doesn't have approval gates, incident integration, or a unified execution view across workflows. Argo is Kubernetes-native and excellent, but it requires significant infrastructure investment and is aimed at data pipelines as much as operational workflows. Temporal is powerful but developer-facing — you write Go or TypeScript, not a visual graph.

SuperPlane targets the **operator** use case: the platform engineer who needs to model an operational process that spans GitHub + PagerDuty + Datadog + Slack, wants to inspect every execution, and does not want to write a distributed state machine from scratch.

The integration list is genuinely broad: GitHub, GitLab, Bitbucket, Semaphore, CircleCI, AWS, GCP, Azure, Datadog, Grafana, PagerDuty, Incident.io, Jira, ServiceNow, Slack, Teams, and AI providers including Claude and OpenAI.

---

## The Technical Foundation

The stack: Go backend, TypeScript/React frontend, PostgreSQL, deployed via Docker or Kubernetes. Apache 2.0 license. 1,800+ GitHub stars, active commit history, 47 releases at time of writing. It is alpha-stage software and the team says so explicitly — expect breaking changes.

The quickstart is a single Docker command:

```bash
docker pull ghcr.io/superplanehq/superplane-demo:stable
docker run --rm -p 3000:3000 -v spdata:/app/data -ti ghcr.io/superplanehq/superplane-demo:stable
```

Open `localhost:3000` and you have a working instance. No Kubernetes required to evaluate it.

For production, single-host deployment on EC2, GCP, Hetzner, or DigitalOcean is documented. Kubernetes (EKS, GKE) is also supported. The architecture is container-first throughout.

---

## The Agent Angle

SuperPlane explicitly supports **agent-driven execution**: equip a coding agent with the SuperPlane CLI and it can trigger workflows, manage resources, and investigate execution history autonomously. The integration with Claude and OpenAI as first-class components means you can wire LLM calls directly into your operational workflows — not as a side experiment, but as a graph node with inspectable inputs, outputs, and retry behaviour.

This is the direction platform engineering is heading. Agents that can act on infrastructure need a control plane with audit trails, approval gates, and observable state. SuperPlane provides exactly that surface.

---

## Honest Assessment

It is alpha. The 308 open GitHub issues are real. Some integrations will be thinner than others. The visual canvas will hit limits on complex graphs. These are solvable problems in a young project with a clear architectural thesis.

What SuperPlane gets right is the level of abstraction. The workflow belongs to the platform team, not to the toolchain. The execution history belongs to your operations record, not to a vendor's SaaS. The approval gates are first-class citizens, not bolted-on workarounds.

If your team is currently maintaining a collection of scripts, Actions, and runbooks that together encode your deployment policy — SuperPlane is worth a serious look.

---

*SuperPlane is open source, Apache 2.0. Repository: [github.com/superplanehq/superplane](https://github.com/superplanehq/superplane). Documentation: [docs.superplane.com](https://docs.superplane.com).*
