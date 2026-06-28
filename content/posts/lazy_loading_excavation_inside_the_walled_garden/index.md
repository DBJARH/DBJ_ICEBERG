---
title: "Lazy Loading excavation inside the Walled Garden"
date: 2026-06-28
description: "A friendly rebuttal to a not-viral iOS lazy-loading post — dlopen and dlsym are not a 2025 discovery, they're a 1988 result the Apple toolchain buried."
tags: ["iOS", "Software Engineering", "History", "Dynamic Linking"]
author: "Dusan B. Jovanovic"
draft: false
cover:
  image: "image.png"
---

> Original article: https://medium.com/@cjckytxz/lazy-loading-dynamic-libraries-and-building-plugin-architectures-on-ios-challenge-accepted-a554fccdb84c

# Lazy Loading excavation inside the Walled Garden

*A friendly rebuttal to "Lazy Loading Dynamic Libraries and Building Plugin Architectures on iOS — Challenge Accepted!"*

There's a genre of engineering blog post that I love and distrust in equal measure: the heroic proof-of-concept. Someone is told "you can't do X on platform Y," they roll up their sleeves, and several diagrams later they emerge holding a working binary. The recent piece on lazy-loading dynamic libraries on iOS is a fine specimen of the genre. Make no mistake, the work is careful, the write-up is honest, and the conclusion is sober.

It is also, in the most literal sense, a rediscovery of 1988.

I don't mean that as an insult. I mean it as the actual, interesting story — one the article gets *close* to telling about itself and then walks past. But its not telling it.

## What the article proves

Strip away the Xcode screenshots and the claim is this: an iOS app can leave a dynamic library unlinked at launch and pull it into memory later, on demand. The method is four steps — build the feature as a separate framework, switch off automatic linking, share only a Swift protocol so no concrete symbols leak, and then at runtime call `dlopen`, let Dyld verify the code signature, and resolve the entry point with `dlsym`.

That sequence — `dlopen` to map the library, `dlsym` to look up a symbol, then call through a known interface — is not a new idea that happens to work on iOS. It *is* the dynamic-loader contract that shipped with System V Release 4 in 1988 and was later standardized into POSIX. iOS has `dlopen` for the same reason it has `fork` and `mmap`: underneath the Swift, it's a Unix.

## The prior art is older than most

Here is the lineage the article is standing on, whether it cites it or not:

- **1964** — Multics loads code segments on first reference. Dynamic linking as a *concept* is older than the C language.
- **1988** — SunOS ships `.so` shared libraries; SVR4 defines `dlopen`/`dlsym`. Runtime loading with symbol lookup becomes a documented, portable API.
- **mid-1990s** — Netscape plugins, Apache modules, Photoshop filters. "Load a separately-built module that conforms to a known interface" becomes the default way to make software extensible. This is *exactly* the "plugin architecture" in the title.
- **2001** — Mac OS X inherits NeXT's `NSBundle`, and Cocoa apps load code bundles at runtime as a matter of routine.
- **2014** — iOS 8 blesses embedded dynamic frameworks. The building blocks the article uses become first-class on the platform.
- **2025** — the article, framing the same technique as a challenge to be proven possible.

Thirty-eight years separate `dlopen` from "challenge accepted." 

**That gap is the whole point.**

## So why did it feel (to iOS developers) like a discovery?

Because for a large cohort of iOS developers, it genuinely was one — and the article says so in its single most important sentence:

> "...because of Xcode and Cocoapods default settings which load all dylibs at launch time... these standard build system defaults may have inadvertently trained a generation of young iOS developers to believe that there was no better way."

Read that again, because it quietly demolishes the framing of the rest of that post. There was never a *technical* prohibition on lazy loading. Dyld didn't refuse. iOS didn't forbid it. There was a checkbox — `Link Frameworks and Libraries Automatically` — defaulted to *on*, and a toolchain culture that never thought to switch it off. The "impossible" thing was a default.

I  dare to claim: that is what makes the post a rabbit hole rather than a breakthrough. The effort was real, but the destination was a documented twentieth-century result that the Apple platform own defaults had buried. The struggle wasn't against the limits of the machine; it was against Apple institutional forgetting. The Objective-C and NeXT worlds did runtime bundle loading without ceremony. That knowledge simply didn't survive the migration to Swift and CocoaPods intact, so it had to be re-derived — by hand, one developer at a time, as a "challenge."

## Where the author is genuinely right

Fairness demands I name the parts that are real, platform-specific, and not findable in a 1988 man page:

**The code-signing constraint.** On iOS, `dlopen` only succeeds against a binary already signed into your app bundle, because the App Store forbids downloading and executing remote code. The article states this plainly, and it matters: it *neuters the original reason dynamic libraries were invented* — shipping module updates over the network. What's left is a launch-time optimization, nothing more. That's a sharp, correct observation about how Apple's sandbox reshapes an old tool.

**The auto-link gotcha.** Keeping concrete symbols out of the shared framework — protocols only — so the linker doesn't silently bind the library at launch is a genuine, fiddly, iOS-2025 detail. It's the kind of thing you only learn by doing exactly what the author did.

And the closing advice is exactly right: this is worth doing only for enormous apps that need a single-digit percentage of their code at launch, and "most developers don't need to use dynamic libraries outside of the common system libraries."

## The real headline

So here's my rewrite of the title, offered in good faith:

> *I spent a long time proving iOS still lets you do a thing Unix has done since 1988 — and the only reason it was hard is that the Apple toolchain hid it from us.*

That's a better story than "challenge accepted," because it points at the actual culprit. The villain isn't a missing capability. It's the combination of opinionated build defaults and a walled garden that, between them, severed a generation of developers from forty years of operating-systems knowledge — to the point where re-exposing `dlopen` reads as a feat of engineering rather than a footnote.

The author didn't reinvent shared libraries. He went down into the basement of his own platform and dug them back up. That's a worthwhile thing to do. It's just worth being honest that the basement was full of other people's tools, neatly labeled, dated 1988 — and that the surprising part of the story is how they ended up buried in the first place.
