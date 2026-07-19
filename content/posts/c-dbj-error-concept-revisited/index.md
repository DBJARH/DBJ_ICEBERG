---
title: "Why revisit it now?"
date: 2026-07-19
draft: false
description: "Revisiting a 2019 idea: VALSTAT, a value-and-status alternative to C++ error handling — and why the AND still holds up."
tags: ["C++", "VALSTAT", "Error Handling", "DBJ"]
author: "Dusan B. Jovanovic"
cover:
  image: "So little C++ so much good.png"
featured: true
---

**C++ DBJ Error Concept — Revisited**

Back in 2019 I wrote [C++ DBJ Error Concept, at last](https://dbj.org/c-dbj-error-concept-at-last/), proposing **[VALSTAT](https://github.com/valstat)** — Value & Status — as an answer to a gap ISO C++ has never closed: there is no standard C++ concept for "how did this call actually go."

Seven years on, the standard still doesn't have one. The idea might be worth restating.

(Certainly `std::expected` seems not to be widely adopted. My own assertion.)

## The naming correction

Key realisation: "Error handling" was the wrong name for the theme. Not every return from a function is an error. Most of what a function reports back is status: it worked, it partially worked, it worked but you should know something about it.

The C++ community's instinct, then and now, was to frame this as **value OR error** — `std::expected<T, E>`, exceptions, error codes, all variations on "did it work, yes or no." 

**[VALSTAT](https://github.com/valstat)**

VALSTAT reframed it as **value AND status**: both present, independently, at the same time.

## The mechanism, unchanged

The implementation was (then and [now](https://github.com/valstat)) — deliberately — almost nothing:

```cpp
template <typename T1_, typename T2_>
using pair_of_options = pair<optional<T1_>, optional<T2_>>;
```

A `pair` of two `optional`s gives four states for free, using only what C++17 already ships:

1. **Both present** — value and status (INFO: it worked, and here's context)
2. **Value only** — OK
3. **Status only** — ERROR
4. **Neither** — FATAL

No macros, no new vocabulary type to standardize, no coroutine machinery. Structured bindings make consumption read naturally at the call site. That was the whole pitch in 2019, and it's still the whole pitch — the standard library already had the parts, nobody had assembled them this way.

## Why revisit it now

`std::expected` landed in C++23. With the key conceptual error. It is strictly an **OR** type: you have the value, **or** you have the error, never both. That's a reasonable design for the narrow case it targets, but it's the same framing VALSTAT argued against — it still can't express "succeeded, and here's a warning you should see" without smuggling the warning into the value type itself.

The gap the 2019 post identified is still here. VALSTAT was never a bid to get into the standard; it was a demonstration that you didn't have to wait for the standard.

## The lesson underneath

This is the same discipline that shows up everywhere else in DBJ Method: don't accept a framing just because it's the one everyone repeats. "Error handling" theme name, was repeated so often it stopped being questioned. Rethinking the C++ `std::expected` "solution" — from OR to AND — was most of the work. The code came after, and it came easily, because C++17 already had every piece required.

If your favorite language standard library forces you to choose between a value and a status, you're not modeling the real shape of what a function reports. You're modeling the using the type that does not present the reality.
