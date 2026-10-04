---
version: 0.1
title: Taxonomy Usage Guide
description: How to use the DBJ Taxonomy as a simple classification core, with an optional Item Declaration, the Five Facets View (5F) matrix.
chapters: ["method"]
tags: ["taxonomy", "classification", "maturity"]
---

## The classification and an optional declaration

The DBJ Taxonomy is a single tree. The top level is an ordered list of categories: Conceptual, Logical, Physical, Implementation. Below it sit the capabilities. Every item has exactly one place in that tree, and the place is its stable ID.

Link [**To the Core**](https://method.dbj.org/taxonomy/taxonomy_core.html#core)

That is the whole core. It is deliberately small, and nothing in it is optional. Those names are the keywords.

<!-- The top level of the tree is the Abstraction facet. Around the core, an organization may attach the optional **Five Facets View (5F)**, a matrix template that describes an item by five facets: Segment, Domain, Abstraction, Lifecycle and Tag. Domain crosses Abstraction in the matrix, so a cell that coincides with a tree node agrees with it (`Application.Conceptual` is Conceptual › Application; `Technology.Logical` is Logical › Platform). The tree always decides the place. 5F is guidance, not part of the taxonomy. Tags describe an item; they never decide where it lives. A book in a library can carry any number of tags, but its shelf does not depend on any of them. -->

## What is an Item

An item is anything classified on a project: a document, a software product, a service, a physical book. The core does not say more than that, and does not need to. What a Product is, and what the organization produces, is declared by the business. The taxonomy only gives each item a place.

## What is an Item Declaration

Each organization decides how much goes into an Item Declaration. General recommendation is to keep it  **Minimal**: the item's place in the tree, plus one or two attributes (for example owner).

## What is an Item Declaration

The DBJ Taxonomy is the only classification. An Item Declaration does not classify. It adds attributes that describe an item in more detail. Each organization decides how many.


| Item Declaration |
|---|
| &nbsp; 

| Attribute | Conceptual architecture of Product X |
|---|---|
| Item </br>Title| Conceptual architecture of Product X |
| DBJ Taxonomy ID | Conceptual: Business, Information |
| Lifecycle | Draft |
| Tags | integration, security |
| Owner | Jane |

The [Taxonomy ID](https://method.dbj.org/taxonomy/taxonomy_core.html#core) is one category plus one to four of its capabilities. Only the Taxonomy ID says what the item is, amd where is it in the info space. All other attributes describe it. Using an Item Declaration to classify is a misuse of it.

<!-- The matrix template: Domain × Abstraction, plus Segment, Lifecycle and Tag.

Header row are Abstractions. First column are Domains, then Segment, Lifecycle and Tag. Values in template cells are names/addresses of the cells.

| | Conceptual | Logical | Physical |
|---|---|---|---|
| **Business** | `Business.Conceptual` | `Business.Logical` | `Business.Physical` |
| **Information** | `Information.Conceptual` | `Information.Logical` | `Information.Physical` |
| **Application** | `Application.Conceptual` | `Application.Logical` | `Application.Physical` |
| **Technology** | `Technology.Conceptual` | `Technology.Logical` — **Platform** | `Technology.Physical` — **Infrastructure** |
| **Segment** | `Segment.<value>` | &nbsp; | &nbsp; |
| **Lifecycle** | `Lifecycle.<value>` | &nbsp; | &nbsp; |
| **Tag** | `Tag.<value>` | &nbsp; | &nbsp; |

An example: the same template, filled in with the items of "Product X". Empty cells stay empty.

| | Conceptual | Logical | Physical |
|---|---|---|---|
| **Business** | Business case | &nbsp; | &nbsp; |
| **Information** | &nbsp; | Data model | &nbsp; |
| **Application** | Conceptual architecture | Interface specification | Source code |
| **Technology** | &nbsp; | Platform standard | Deployment topology |
| **Segment** | Products | &nbsp; | &nbsp; |
| **Lifecycle** | Draft | &nbsp; | &nbsp; |
| **Tag** | integration, security | &nbsp; | &nbsp; |

Segment and Lifecycle are attributes, not classification. Lifecycle in particular is private to the organizational unit in which a project is rotating, so a shared core cannot define it. -->

## Why not put all of it into the core

Complexity. A model with five independent facets can not be drawn as one hierarchy. It has no single canonical location for an item, and it invites the "tag" to become an escape route to anything.

A single tree is simpler and stricter. But simplicity is not understood immediately. It takes maturity, and organizations that never had to classify, find it hard.

So 5F is an optional extension, applied after the item is classified by the tree.

## Maturity

This is the same reasoning behind the DBJ CMM Level 5 "entry ticket". An organization must be mature enough to loop through the BPT at the speed of AI. Simplicity is the prize for that maturity, not a starting point.

## Rule of thumb

- The tree says what an item is.
- The Item Declaration (5F) says more about it, if required.
- Tags never change what an item is.

```text
---
title: Conceptual architecture of Product X
taxonomy: Conceptual.Application
segment: Products
cell: Application.Conceptual
lifecycle: Draft
tags: [integration, security]
---
```

The front matter above is the Item Declaration: tree is the item's place, and the other keys are 5F attributes. Tags never change what an item is.

The location is the item's taxonomy ID, so the key says so. The Title does not show it. It only names the item.
