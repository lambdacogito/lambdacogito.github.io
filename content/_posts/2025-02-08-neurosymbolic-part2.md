---
layout: post
title: "Neuro-symbolic AI (Part II)"
subtitle: "Why self-reference matters"
date: 2025-02-08
author: "Jamin Chen"
header-img: "img/post-bg-universe.jpg"
tags: ["Neuro-symbolic", "Knowledge Representation", "Artificial Intelligence"]
---

## Background

Self-reference, one of the most important concepts for understanding human
consciousness, is both a fundamental aspect and a powerful tool for advancing
future AI systems. Its profound implications are explored in Douglas
Hofstadter's books *Gödel, Escher, Bach* and *I Am a Strange Loop*. These two
works, spanning nearly thirty years, showcase the author's evolving thoughts on
self-reference, transitioning from empirical observations in cognitive science
to a deeper, more introspective philosophical perspective. In Hofstadter's
philosophy, self-reference is central to understanding the concept of "**I**".

In cognitive science, self-reference is closely tied to conscious experiences
such as memorization, reasoning, prediction, and decision-making. The sense of
"**I**" is considered to arise from the interplay of sensory feedback within
our biological subsystems and the cerebral neural network—mechanisms,
unfortunately, that still remains largely unexplored. This lack of
understanding, however, does not impede the development of AI; on the contrary,
it fuels our curiosity about the potential to replicate human consciousness
within a mechanical framework.

Meanwhile, self-reference poses challenges in mathematics and computer science.
It disrupts the foundations of mathematics through Gödel's incompleteness
theorems (1931) and renders Turing's Halting Problem undecidable (1936), both
of which rely on self-referential constructs (e.g., the *Gödel sentence*) to
derive contradictions. These results underscore the inherent limitations of all
formal systems, such as mathematical logic and Turing machines, and have
sparked decades of debate (see [Lucas-Penrose Argument](https://iep.utm.edu/lp-argue), 1961-2003)
over whether computer can truly emulate
human intelligence. This question remains a pivotal consideration as today we
are marching toward artificial general intelligence (AGI).

## Self-reference and AGI

Self-awareness, a fundamental aspect of future agentic systems, is deeply tied
to self-reference. If we aim to build human-like agents to serve our
civilization, their "mental" world must be self-consistent while mastering vast
knowledge and skills. The flip side of this is the risk of multiple conflicting
personalities, which can lead to dilemmas and inconsistencies. These, in turn,
may result in unintended reasoning processes and unpredictable behavior.

Current large language models can simulate role-playing scenarios through
prompts such as “assume you are a [role]…,” indicating a lack of
self-consistency and self-reference in general problem-solving contexts. This
limitation is one of the key sources of LLM hallucinations.

Gödel’s incompleteness theorems establish that consistency and completeness
cannot be achieved simultaneously. Gödel’s insights suggest that creating AGI
requires more than just accumulating data and refining neural networks; it
necessitates an understanding of the fundamental principles that shape logic,
mathematics, and cognition [1].

From a theoretical standpoint, we can make the following assertions regarding
AI and self-reference today:

* A formal system adheres to Gödel’s incompleteness theorems.
* A Turing machine is a formal system.
* Neural networks are not Turing-complete.
* However, transformers and recurrent neural networks (RNNs) have been proven
  to be Turing-complete under specific theoretical conditions [3].

This suggests that the balance between completeness and consistency remains a
crucial factor in transformer-based AI systems. Historically, Turing’s paradox
demonstrated the impossibility of a universal proving machine, an insight that
reshaped computing history and led to the development of modern, versatile
computers.

By analogy, we propose a bold prediction: large, unified language models
represent an intermediate stage in the evolution of AI architectures. The
next-generation mainstream approach is likely to be Mixture of Experts (MoE)
models, systems that enhance predictive accuracy (consistency) by incorporating
expert models with specialized but limited completeness in specific domains.
These architectures may provide a more balanced trade-off between completeness
and consistency, pushing AI development forward.

## Self-reference and Attention

The attention mechanism, a fundamental aspect of human intelligence for
processing contextual information, is a crown jewel of AI science. After years
of exploration by researchers worldwide in the field of natural language
processing, the success of the Transformer model (2017) is twofold. First, it
effectively captures the attention mechanism through an efficient multi-head
attention (MHA) structure, enabling scalable models that can be trained on
internet-scale data with parallel processing. Second, it demonstrates
remarkable generality in modeling sequential data within closed or semi-closed
complex systems, such as natural language, global weather patterns, and protein
structures.

This generality in modeling sequential data is particularly significant.
According to the second law of thermodynamics, our physical world operates as a
vast three-dimensional closed system with a temporal direction, resulting in a
unidirectional flow of information, i.e., a sequential system. Since human
consciousness emerges from interactions with the external world, our memory,
reasoning, and even emotions are deeply tied to temporal sequences in physical
reality. In this sense, mastering a powerful framework for modeling sequential
data is crucial for the advancement of human-like AI architectures.

Transformer models perform attention modeling through a combination of
positional encoding and self-attention mechanisms. The positional encoding
encodes the position of each token in the sequence, while the self-attention
mechanism allows the model to focus on different parts of the sequence to
enhance the information representation.

Encoding self-reference in a Transformer model remains a challenge due to the
absence of a dedicated module for capturing the sense of "**I**". In
role-playing games of large language models, a character's sense of self is
simulated through a segment of tokens representing its internal state—akin to a
memory cache—prepended to each query. This mechanism helps maintain consistency
in the character’s internal state by feeding information into the attention
modules.

In the MoE architecture, an alternative approach to self-reference involves
employing a dedicated expert model that encapsulates the concept of "I". The
output of this shared self-reference expert receives greater weight when the
input aligns with the system’s global internal state. However, this method may
diminish the knowledge coverage of other non-shared experts, ultimately
reducing the generality of global training.

A more advanced and human-like integration of self-reference would embed it
directly within the attention mechanism itself. Achieving this requires
reimagining and innovating attention structures within AI architectures. In
**neuro-symbolic AI**, the attention module can take different forms, such as a
sub-graph correlation matrix rather than a conventional vector distance matrix.
In this context, the core aspect of self-reference, when represented as a graph,
can be directly embedded within the correlation matrix. This mechanism will be
explored in greater depth in future blogs.

## Summary

In this blog, the concept of self-reference in the context Godel's
incompleteness theorems and its implications for AI are explored. It is shown
that self-reference is central to guide and advance future AI systems, such as
agentic or robotic systems.

## References

[1] [Gödel: Incompleteness Architect – Limits of Knowledge in AI Era](https://web.archive.org/web/20250208070520/https://editverse.com/kurt-godel-incompleteness-theorems-logical-paradoxes/)

[2] [Gödel's Incompleteness Theorem is Not an Obstacle to Artificial Intelligence](https://www.sdsc.edu/~jeff/Godel_vs_AI.html)

[3] Attention is turing-complete. Journal of Machine Learning Research, 2021, [link](https://jmlr.org/papers/volume22/20-302/20-302.pdf)
