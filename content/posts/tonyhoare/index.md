---
title: "A Tribute to C.A.R. Hoare"
date: 2025-01-01
description: "The paper everyone forgot — almost. On Hoare's 1966 record handling, the 35-year mistake, and what Rust got back."
tags: ["software-history", "architecture", "rust", "C"]
author: "Dusan B. Jovanovic"
---

![](/the dark bottom dbj.png)

## The Paper Everyone Forgot — Almost

Tony Hoare published "Record Handling" in 1966. Before Simula 67. Before Smalltalk. Before anyone had coined the term object-oriented programming.

He wasn't thinking about objects sending messages to each other. He was thinking about something much simpler: data with a type tag, and code that switches on that tag.

---

## What He Actually Proposed

You have a record. The record knows what it is — it carries a tag. You have a dispatch function that looks at the tag and calls the right handler. The handler takes storage and params. That's it.

No object. No `this`. No method lookup. No vtable. A record, a tag, and a switch.

It's almost embarrassingly simple. Which is probably why it got overlooked.

---

## The Irony

[Alan Kay](https://en.wikipedia.org/wiki/Alan_Kay) also called his model "message passing" — same words, completely different idea.

In Kay's model, dispatch is implicit. It's buried in the vtable, hidden behind the dot operator. The receiver decides what to do. The caller is blind to the mechanism.

In Hoare's model, dispatch is right there in front of you. The tag is visible data. The switch is visible code. You can inspect it, reason about it, have the compiler check it.

| | Kay | Hoare |
|---|---|---|
| Syntax | `object.method(args)` | `dispatch(cmd)` |
| Dispatch | Receiver owns it — caller is blind | Explicit — tag is inspectable |

---

## Where It Went Wrong

Simula read Hoare's paper. They kept the subclass idea. But they dropped `inspect` — the keyword that would have given you exhaustive switching on the type tag.

One keyword. Gone.

That single omission is what Casey Muratori calls the [35-year mistake](https://youtu.be/wo84LFzx5nI). C++ inherited Simula. Java inherited C++. And for decades, the mainstream got Kay's model — the one where the mechanism is hidden and the caller just has to trust.

---

## What Came Back Around

Rust's `enum` + `match` is essentially what Hoare described in 1966. Explicit tags. Exhaustive checking. The compiler tells you when you've missed a case. Nothing hidden, nothing implicit.

It took 58 years to get back there.

---

Sometimes the road not taken just takes longer.

Rest well, Sir Tony.
