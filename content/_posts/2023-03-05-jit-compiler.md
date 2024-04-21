---
layout: post
title: "How JIT optimizes code"
subtitle: ""
date: 2023-03-05
author: "Jamin Chen"
header-img: "img/post-bg-universe.jpg"
tags: ["Computer Language", "Java", "Compiler"]
---

The JIT compilation consists of five stages:

# Inlining

Inlining is the process by which the trees of smaller methods are merged, or "inlined", into the trees of their callers. This speeds up frequently executed method calls.

Two inlining algorithms with different levels of aggressiveness are used, depending on the current optimization level. Optimizations performed in this phase include:

*   Trivial inlining
*   Call graph inlining
*   Tail recursion elimination
*   Virtual call guard optimizations

# Local optimizations

Local optimizations analyze and improve a small section of the code at a time. Many local optimizations implement tried and tested techniques used in classic static compilers.

The optimizations include:

*   Local data flow analyses and optimizations
*   Register usage optimization
*   Simplifications of Java™ idioms

These techniques are applied repeatedly, especially after global optimizations, which might have pointed out more opportunities for improvement.

# Control flow optimizations 

Control flow optimizations analyze the flow of control inside a method (or specific sections of it) and rearrange code paths to improve their efficiency.

The optimizations are:

*   Code reordering, splitting, and removal
*   Loop reduction and inversion
*   Loop striding and loop-invariant code motion
*   Loop unrolling and peeling
*   Loop versioning and specialization
*   Exception-directed optimization
*   Switch analysis

# Global optimizations

Global optimizations work on the entire method at once. They are more "expensive", requiring larger amounts of compilation time, but can provide a great increase in performance.

The optimizations are:

*   Global data flow analyses and optimizations
*   Partial redundancy elimination
*   Escape analysis
*   GC and memory allocation optimizations
*   Synchronization optimizations

# Native code optimizations  

Native code generation processes vary, depending on the platform architecture. Generally, during this phase of the compilation, the trees of a method are translated into machine code instructions; some small optimizations are performed according to architecture characteristics.

The compiled code is placed into a part of the JVM process space called the code cache; the location of the method in the code cache is recorded, so that future calls to it will call the compiled code. At any given time, the JVM process consists of the JVM executable files and a set of JIT-compiled code that is linked dynamically to the bytecode interpreter in the JVM.

Source: https://www.ibm.com/docs/en/sdk-java-technology/7.1?topic=compiler-how-jit-optimizes-code
