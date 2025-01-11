---
layout: post
title: "Neurosymbolic AI (part I): why self-explanation matters"
subtitle: ""
date: 2025-01-11
author: "Jamin Chen"
header-img: "img/post-bg-universe.jpg"
tags: ["Neurosymbolic"]
---

The success of LLMs has triggered a new wave of prosperity of AI researches.
The market, supply chains and end-users have been educated in a unprecedented
depth about AI capabilities in this wave. This is another fresh start toward
the future of intelligent world.

## Motivation

Project [LaCogito](https://github.com/lambdacogito) was initiated to explore
the foundational architecture of next-generation AI—an AI system characterized
by *self-explanation, self-reference, and unlimited extensibility for diverse
real-world contexts via active inference* [3]. Positioned at the forefront of
innovation, LaCogito aims to identify and develop the essential core
technologies, service capabilities, and market opportunities based on the first
principles of intelligence.

The foundational idea behind LaCogito was conceived as a system designed to
fuse multi-source data and enable interactive, autonomous knowledge mining,
akin to [Wolfram Alpha](https://www.wolframalpha.com/), even before the
announcement of [ChatGPT](https://chat.openai.com/). I was deeply impressed by the scale and
multidimensionality of the data supporting Wolfram Alpha and its Cloud
services. To unravel its underlying technologies, I explored a wide range of
disciplines, from the semantic web to category theory to neural networks.
Despite these efforts, I ultimately failed to build such a system.

The sudden emergence of ChatGPT, however, reignited hope by demonstrating a
practical AI system aligned with this vision. Yet, the more I delved into
understanding how large language models (LLMs) operate, the stronger my desire
grew to revolutionize the design of an AI system. My vision centers on key
principles: self-reference with consistent cognition, self-explanation through
concrete and precise concept representation, active inference derived from
interactions with the external world, and continuous learning for evolution.

In a series of posts, I will outline the fundamental concepts underpinning this
ideal future AI system. In this post, I will depict the essentials and
solutions to support AI systems with self-explanation.

## What is Self-Explanation

Self-explanation addresses the research direction of explainable AI models, in
which we can understand how the AI systems work and control their behaviors
when necessary. What locates at the core of self-explanation is the representation of a
**concept**. Understanding the significance of conceptual representation in
artificial intelligence is akin to understanding the space-time dimension in
Einstein's relativity theory.

In traditional semantic web, a concept is recorded as a symbol (e.g., 'Love' in
English and '愛' in Chinese). In artificial neural networks (ANN), a concept is
encoded in the vectors (e.g., 1001001010101 in LLM). As for biological neural
networks, memorial formation and storage of a concept still remain
mysterious ([cognitive science](https://en.wikipedia.org/wiki/Cognitive_science)
and [systems biology](https://en.wikipedia.org/wiki/Systems_biology),
two related promising areas to uncover this).

From my perspective, AI systems capable of self-explanation should possess the following characteristics:

* **Controllable Concept Formation**: This applies regardless of whether the conceptual representations are explicit or implicit.
* **Traceable Logical Reasoning**: The reasoning should be based on clearly defined conceptual relationships.

## Cerebral vs. ANN Intelligence

To analyze the differences in conceptual representations, it is essential to
consider the encoding and decoding processes. When comparing cerebral and
artificial neural networks, irrespective of their actual structures, concepts
in the brain are functionally encoded within a *multi-modal, heterogeneously
featured, and highly dimensional space*, while they are conveyed by
hidden layers in ANN with a vast amount of parameters.

Empirically, when stimulated by specific external signals (e.g., a familiar
scene or an old object), the human brain can rapidly reconstruct a concept and
its related associations within milliseconds. These associations can encompass
both symbolic information (e.g., a piece of literature) and non-symbolic
information (e.g., emotions or feelings) . However, despite these empirical
insights, a sufficiently robust theoretical foundation for cerebral encoding,
decoding, and their interactions remains lacking.

In contrast, artificial neural networks (e.g., transformers) perform encoding
through pre-training, embedding concepts into network weights that are tightly
linked to network topology. In this process, vectors primarily serve as
transmission mediums to collect and compress contextual information layer by
layer via attention heads, weights, and residual pathways. This implies that
concepts are stored within the network’s transformations rather than in the
vectors themselves [2].

A significant limitation of this approach is the distributed and implicit
correlation across the entire network, involving numerous active parameters
that are still largely unknown and uncontrollable in the global parameter
space. This globally correlated representation gives rise to challenges such as
hallucinations, difficulties in ad-hoc updates to pre-trained models, and
inefficiencies in reusing encoded knowledge. Techniques like Reinforcement
Learning with Human Feedback ([RLHF](https://arxiv.org/abs/2203.02155))
or Direct Preference Optimization ([DPO](https://arxiv.org/abs/2305.18290))
provide only limited solutions to these issues, as their end-to-end and
result-oriented guidance and optimization approaches fail to address the root
causes effectively.

Recent researches [1,2] comparing brain intelligence and the mechanisms of LLMs
offer a valuable opportunity to explore how intelligence is "generated".
Current findings reveal some intriguing similarities between the brain and LLMs,
such as cascading information processing (e.g., cerebral cortex regions vs.
transformer layers) and contextual knowledge integration (e.g., cortex neuron
connectivity vs. transformer attention heads). However, it remains unclear
whether they share the same underlying mechanisms. The lack of effective
technologies to trace cerebral neural activities during thought processes
limits our understanding of possible counterparts to transformer's embeddings,
attention transformations, residual optimizations, and more. Nevertheless,
continued progress in cognitive and brain sciences is essential to unraveling
the complexities of cerebral intelligence.

## Neurosymbolic AI

Another potential solution for developing self-explainable systems is the
integration of symbolic technologies. Traditional symbolic AI faced significant
inefficiencies during the previous "AI winter" (late 1980s to 2000),
particularly in iconic symbolic processing (e.g., LISP machines) and
frame-based expert systems. However, adversity often fosters innovation. The
decline of purely symbolic approaches, coupled with the potential challenges of
pure neural-network AI, has paved the way for the emergence of promising
*neuro-symbolic AI*.

In this novel framework, a **General Symbol (GS)** represents a concept in various
forms, such as a sequence of words, a 3D geometric shape, a sound, or even a
physical sensation (potentially embedded as smaller models). Neural networks
are not directly involved in encoding all knowledge. Instead, they are trained
to perform specific tasks, such as routing paths to particular concepts,
encoding complex non-symbolic concepts, or understanding and mastering the
intrinsic relationships among them.

Together, these general symbols and their interconnections form the
foundational knowledge base of AI. The sheer scale and complexity of such a
symbolic knowledge base may surpass human capacity for manual upkeep. To
address this, agentic bots with specific goals can be designed to assist humans
in managing and maintaining the knowledge base effectively.

## Summary

In this post, I have outlined the essentials and a potential solution, i.e.,
neurosymbolic AI, for explainable AI systems. The next posts will delve into
two other fundamental principles: self-reference and active inference.

## References

[1] Contextual Feature Extraction Hierarchies Converge in Large Language Models
and the Brain, Nature Machine Intelligence, 2024, [link](https://www.nature.com/articles/s42256-024-00925-4)

[2] Shared functional specialization in transformer-based language models and
the human brain, Nature Communications, 2024, [link](https://www.nature.com/articles/s41467-024-49173-5)

[3] Generating meaning: active inference and the scope and limits of passive AI,
Trends in Cognitive Sciences, 2024, [link](https://www.sciencedirect.com/science/article/pii/S1364661323002607)
