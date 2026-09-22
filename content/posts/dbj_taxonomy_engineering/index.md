---
title: "The .taxonomy File"
date: 2026-08-01
description: "A dotfile that tells tools and agents where a folder sits in the company information space."
tags: ["taxonomy", "engineering", "agents"]
author: "Dusan B. Jovanovic"
cover:
    image: dbj_taxonomy_officer.png
---

DBJ Taxonomy defines the language for coordinates of the infospace. Content nobody can locate is content nobody finds.

> Taxonomy defines the locations on the map the business holds firmly in its hand.
>
> **Taxonomy is the language used for programming infospace navigation instruments**

The `.taxonomy` file connects the abstract taxonomy to actual content. It declares a taxonomy location using the [DBJ Core Taxonomy](https://method.dbj.org/taxonomy_core.html#core) key-words. Any kind of content: repositories of documents, images, specifications.

## Format

TOML. Two keys, both arrays:

```toml
category = ["Implementation"]
capability = ["Deployment", "Operations"]
```

Arrays because one folder and its offspring can hold more than one kind of work. Example: a deploy tool might contain `Deployment` and `Operations` — two capabilities at the same time. Clearly offspring of the same category.

## The names are key-words

Terms come from the core taxonomy. Four categories:

**Conceptual**, **Logical**, **Physical**, **Implementation**

Four capabilities each:

| Category | Capabilities |
|---|---|
| Conceptual | Business, Information, Application, Technology |
| Logical | Data Management, Integration, Platform, Security |
| Physical | Compute, Infrastructure, Network, Storage |
| Implementation | Deployment, Development, Monitoring, Operations |

No synonyms. Not "Dev" for Development, not "Ops" for Operations, not "Infra" for Infrastructure. A synonym dilutes the term and breaks the thing that makes the file useful — that everything answers with the same words.

## Placement

Any folder. The file covers that folder and everything under it.

Put one in the repository root and it describes the whole repository. Put one deeper and it describes that subtree. A documentation repository with `architecture/`, `security-policies/` and `runbooks/` is three different places in the infospace, and one file at the root cannot say that honestly. Add more `.taxonomy` files as you find appropriate.

The file is optional. Content without one is simply non allocated. Drifting in the infospace.

## Deeper replaces the upper

When a folder has its own `.taxonomy`, it **replaces** the parent's — whole file, both keys, no merging.

```
docs/.taxonomy              category = ["Conceptual"]
                            capability = ["Information"]

docs/security/.taxonomy     category = ["Logical"]
                            capability = ["Security"]
```

Everything under `docs/security/` is Logical / Security. Nothing of the parent survives. The whole point is that a `.taxonomy` reads correctly on its own.

## Why bother

Two reasons.

Agents use tools. Tools using the `.taxonomy` file, can place the content immediately. No heuristics over README text, no guessing from folder names, no separate registry that goes stale the moment someone forks.

An agent asked where security work in this folder lives, reads `.taxonomy` file and gets an answer instead of a search result. The declaration travels with the content and helps visitors orienteering.

## Status

This is a recommendation, hoping to become de-facto standard, not a tool. Nothing "official" validates the names, nothing resolves which file applies to a given folder, nothing rejects a synonym. There is no reason for FOSS initiative that would build it.

Until then it holds because people use it correctly. Which is worth knowing before you rely on it. On company level this functions. 
