---
title: "A Tribute to C.A.R. Hoare"
date: 2026-02-01
description: "The paper everyone forgot — almost. On Hoare's 1966 record handling, the 35-year mistake, and what Rust got back."
tags: ["software-history", "architecture", "rust", "C"]
author: "Dusan B. Jovanovic"
draft: false
cover:
  image: "image-1.png"
---

(Image source: `https://cs.stanford.edu/people/eroberts/courses/soco/projects/2008-09/tony-hoare/images/hoare%20main.jpg` )


> In case you like code more than prose about the code, [here is the code](https://godbolt.org/z/sb7MTeGax). That is vibed. Quality is average, bordering on bad. I spent some time, in between other tasks, and made what is I might claim, elegant, human optimised code. ( https://godbolt.org/z/9M8oj34TT ) Those improvements need never stop, of course. 

## The Foundation Everyone Forgot — Almost

Before Simula 67. Before Smalltalk. Before anyone had coined the term object-oriented programming. Tony Hoare formalized the concept of the discriminated union in his seminal 1965 paper, "Record Handling."

In this paper, Hoare introduced the idea of a record (a data structure grouping related fields) and proposed that records could have a "variant part." By looking at a specific "tag" field within the record, the program could determine which variant of the record was currently active.

This concept was highly influential and was directly implemented in the programming language ALGOL W (which Hoare co-designed with Niklaus Wirth in 1966) and later became a staple of Pascal and Ada.

He wasn't thinking about objects sending messages to each other. He was thinking about something much simpler: data with a type tag, and code that switches on that tag. Example (Pascal-style Variant Record):

```javascript
type
  ShapeTag = (Circle, Square, Triangle);
  Shape = record
    case tag: ShapeTag of
      Circle: (radius: Real);
      Square: (sideLength: Real);
      Triangle: (base, height: Real);
  end;
```

In this structure, the tag field guarantees that if a program tries to access shape.radius, the compiler can verify that shape.tag is actually Circle.

---

### What He Actually Proposed

You have a record. The record knows what it is — it carries a tag. You have a dispatch function that looks at the tag and calls the right handler. The handler takes storage and params. That's it.

No object. No `this`. No method lookup. No vtable. A record, a tag, and a switch.

It's almost embarrassingly simple. Which is probably why it got overlooked. Hoare’s creation was a massive leap forward in type safety. Untagged Unions (C/C++): If you misinterpret the data in a C union (e.g., writing an integer and reading it as a pointer), the compiler will let you, resulting in memory corruption or crashes.

Tagged Unions (Hoare's model): The compiler enforces that the tag and the data match, preventing a whole class of bugs before the program even runs.

If you are reading about Tony Hoare and unions, you are reading about the moment he added type safety to composite data structures. By inventing the discriminated union (variant record), he gave programmers a way to securely model data that can take on multiple different forms, a concept that remains central to software engineering today.

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
