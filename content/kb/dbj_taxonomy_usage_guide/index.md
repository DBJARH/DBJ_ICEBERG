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
