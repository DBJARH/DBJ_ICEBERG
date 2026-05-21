---
title: "The Language Layer Does Not Matter"
date: 2025-01-11
description: "On llama.cpp, inference engines, and why the host language is irrelevant when the GPU is the bottleneck."
tags: ["software-engineering", "AI", "C", "systems"]
author: "Dusan B. Jovanovic"
---

![](/the dark bottom dbj.png)

## The Language Layer Does Not Matter

Andrej Karpathy does not use C. He does not need to. His work sits at the model research and pedagogy layer where Python is the lingua franca. The real compute happens in C and CUDA underneath, but that layer is invisible to him. Training a model takes ten hours in C++ and ten hours in Python — the GPU is the bottleneck, not the host language.

The one exception is instructive: **llm.c** — a minimal GPT-2 training implementation in pure C, written deliberately as a proof of how thin the actual logic is once you strip framework overhead. That is the move closest to the systems programmer's instinct: strip it down, see what remains.

Bryce Adelstein Lelbach (BAL) at NVIDIA — active on ISO WG21, leading CUDA parallelism work — represents the C++ committee's relationship with C: benign neglect. C/C++ compatibility is acknowledged at the margins. C as a peer language is not engaged. The WG21 view is that C is a subset they have moved past.

This is not universal. The systems community disagrees. C remains a sharp, honest, deployment-ready tool.

---

## What llama.cpp Actually Is

llama.cpp is not a full LLM. It is an **inference engine**.

It loads pre-trained model weights in GGUF format, runs the forward pass efficiently on CPU and GPU, handles quantisation at 4-bit and 8-bit, and provides a simple API and server interface. It does not train models. It contains no weights. It has no training loop.

The analogy holds precisely: llama.cpp is the JVM. The model weights are the bytecode. One without the other is useless.

The full stack is: someone else trains, exports to GGUF, llama.cpp runs it.

There are LLM implementations in Zig — community efforts around transformer inference that are genuine and technically motivated. Zig's value proposition aligns with the problem: no hidden allocations, explicit memory control, C interop without FFI friction, comptime for kernel specialisation. But no production frontier LLM is written in Zig. These are hobby and research projects. The most credible C-adjacent inference story remains llama.cpp.

---

*Dušan Jovanović — Enterprise Architect, DBJ.METHOD*
