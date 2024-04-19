---
layout: post
title: "本体论框架"
subtitle: "Ontology Framework"
date: 2024-04-18
author: "Jamin Chen"
header-img: "img/post-bg-universe.jpg"
tags: ["Ontology", "Knowledge Representation"]
---

## 概述

本文总结当前主流的语义网络（知识图谱）领域的本体描述框架，包括理论，语言和系统。
其中本体论介绍相关理论发展，以及大家对其形而上学的争论；本体工程介绍若干基础和领
域的本体概念集；本体语言介绍典型的知识表示语言及其发展过程。最后展望在大语言模型
变革下的本体论技术发展趋势。

## 简史

符号知识系统的发展，从最初的通用问题解决器GPS 到最近的语义网络和知识图谱，经历了
多次的基础理论迭代和系统发展，这里简要总结（Wikipedia通过ChatGPT总结生成）。

* **1959**
    * General Problem Solver (GPS) System，由Allen Newell & Herbert A. Simon提出
      关于规划和分解解决问题的数据结构。
    * Advice Taker，John McCarthy提出，提倡使用predicate calculus进行常识推理。

* **1960s**
    * Resolution Method，John Alan Robinson提出，提出利用一阶逻辑进行自动化定理
      证明。
    * Situation Calculus，John McCarthy and Pat Hayes提出，对场景和因果知识通过
      逻辑表示。

* **1970s**
    * 逻辑编程和Prolog，提出了一种将Horn子句映射成目标约减过程的解法，并发展了系
      统化的计算机语言。
    * Frame Concept，Marvin Minsky提出，可认为一次重要的发展节点，消弭了长期关于
      知识的基于本体论的静态表示和基于逻辑推理的过程知识表示，提出Frame概念表示
      本体及问题解决策略。Frame概念受到面向对象理念发展的影响，二者有诸多相似之
      处。目前主流的知识表示语言，与Frame概念一脉相承。

* **1980s**
    * Knowledge Engineering Environment (KEE)，Intellicorp公司提出，在以frame概
      念为基础的知识表示之上，增加了规则引擎。
    * KL-ONE，一种frame语言，包含了规范预发和自动推理引擎。
    * Cyc，Doug Lenat创立的Cyc公司，后发布过OpenCyc，其目标为基于frame的知识表示，
      构建一个常识推理系统。
    * 知识表示假设，Brian C. Smith首次提出知识表示假设(Knowledge Representation
      Hypertheses)，对于如何表示知识进行了理论化表述，引用原文：

        > Any mechanically embodied intelligent process will be comprised of structural
        ingredients that a) we as external observers naturally take to represent a
        propositional account of the knowledge that the overall process exhibits, and b)
        independent of such external semantic attribution, play a formal but causal and
        essential role in engendering the behavior that manifests that knowledge.

* **Since 2000**
    * Semantic Web，由W3C组织提出，又称Web 3.0，基于RDF、OWL等标准化技术实现。
      Knowledge Graph也属于这一技术领域。Berners-Lee在1999年这样表达自己对于语义
      网络的Vision（结合当前AIGC的发展仍然具有启发性）：

        > I have a dream for the Web [in which computers] become capable of
        analyzing all the data on the Web – the content, links, and transactions
        between people and computers. A "Semantic Web", which makes this
        possible, has yet to emerge, but when it does, the day-to-day mechanisms
        of trade, bureaucracy and our daily lives will be handled by machines
        talking to machines. The "intelligent agents" people have touted for
        ages will finally materialize


## 本体论

关于本体论(Ontology)的基本定义，在发展过程中一直备受争议。总结起来有两种递进意义
下的定义。侠义地，本体论指概念及其关系的集合。广义地，本地论指以高度语义化的表达
描述关于客观世界的知识。

Russell & Norvig给出的结构化表示（structural representation）可以认为是一种狭义
的定义：

> facts about particular objects and event types and arrange the types into a
> large taxonomic hierarchy analogous to a biological taxonomy.

Tom Gruber也给出类似的定义：

> An ontology is a description (like a formal specification of a program) of the
> concepts and relationships that can formally exist for an agent or a community
> of agents.

Gruber（1993）试图给出更一般的定义：

> Ontologies are also not limited to conservative definitions — that is,
> definitions in the traditional logic sense that only introduce terminology and
> do not add any knowledge about the world. To specify a conceptualization, one
> needs to state axioms that do constrain the possible interpretations for the
> defined terms.

Feilmayr & Wöß (2016) 对Gruber的定义进行了更清晰的说明

>  An ontology is a formal, explicit specification of a shared conceptualization
>  that is characterized by high semantic expressiveness required for increased
>  complexity.

这也是我们采用的广义定义，主要特征包含通用性、语义化、强表达力。需要说明的是，
Ontology一词被广泛使用，通常根据上下文可能代表概念词表、分类系统、元数据、以及语
义网络等不同含义，因此我们很难给出统一的使用限制。在AI领域里，我们推荐Feilmayr &
Wöß的定义作为广义的AI Ontology概念。

## 本体工程

本体工程（Ontology Engineering）属于应用本体论的范畴。在信息学领域，以Sowa的
Conceptual Graph（ISO标准化为Common Logic）、W3C标准化的Semantic Web相关技术为代
表，通过系统化和标准化，实现本体论所定义的对世界知识的语义性表达。

本体工程的产物，本文中也称之为本体模型，即定义了概念及其关系的集合。和大语言模型
的基础模型和微调模型类似，本体模型也包含基础本体模型（Foundation ontology or
Upper ontology）和领域本体模型（Domain ontology）。常见的基础本体模型有BFO、
Dublin Core、GFO、Cyc、SUMO、UMBEL、FOAF、DOLCE等。WordNet也被大多数研究者认为是
基础本体模型，但是在实际应用中，wordnet通常被作为语言学工具学习领域本体模型。

在本体工程中，只有开放合作，才能实现不同领域专家知识的连接和共享。因此标准化的工
作至关重要。目前相关标准包括W3C RDF/RDFS资源定义框架、OWL知识表示语言、SPARQL查
询语言。以及ISO Common Logic标准（ISO/IEC 24707:2007），定义了一套逻辑编程语言的
框架，有助于不同的知识表示语言能够相关转化；其中也定义了一些方言，例如逻辑交换格
式CLIF、概念图交换格式CGIF等。CL标准具有通用性，其他基于逻辑的语言（例如OWL）可
以转化为CL定义的抽象语法和语义。

与此同时，W3C发起了[Linked Data](https://en.wikipedia.org/wiki/Linked_data)项目，
旨在基于标准化定义，实现不同本体模型的对齐和关联，实现全人类共同拥有和受益的语义
网络。

![lod-cloud](https://lod-cloud.net/clouds/lod-cloud.svg "The Linked Open Data Cloud")

## 本体论语言

这部分我们再回顾本体论框架下的知识表示语言（Knowledge Representation Languages,
KRL）的发展。回顾这些历史， 有助于我们在当下技术发展阶段，进一步发展出表达力更强、
更易于计算的KRL。典型的语言包括CASL、CycL（Cyc项目）、KIF（基于S表达式的一阶逻辑
语言）、Olog、OntoUML、OWL等。

在众多KRL当中，有一类语言基于Frame概念，至今方兴未艾，也深刻影响了OWL的标准化制
定，这一类语言包括KRL（第一个通用的Frame语言）、KL-ONE、Loom、RDFS、OIL、DAML
（基于RDF的标记语言）、以至OWL。其中OWL的标准化设计，受到了DAML+IOL的深刻影响。

## 未来

在基于Transformer的大语言模型的深刻技术变革中，本体论相关技术以其强逻辑性、可解
释性，有潜力实现对大语言模型隐式知识表达的融合和创新。近两年已有不少有趣的工作和
项目出现，例如知识图谱和LLM的结合应用[3]、基于LLM的Ontology Learning[4]等，这方
面未来值得花篇幅单独介绍。

另一方面，本世纪以来，人类在软件工程化（例如数据计算和信息提取领域），实现了长足
进步，尤其在开源软件社区蓬勃发展的驱动下。早期以标记符号为主的知识表示语言（例如
OWL）开始展现出不足，尤其是对于计算型知识（Computational Knowledge）的表达表现出
较大局限性。如何实现基于标准化、又发展标准化的新的KRL，能够充分利用当前已有的软
件生态以及计算硬件，是构建未来的高科技实力组织，并且实现通用人工智能的关键环节之
一。

## 参考

* [1] https://en.m.wikipedia.org/wiki/Ontology_(information_science)
* [2] https://en.m.wikipedia.org/wiki/Ontology_language
* [3] Neuhaus, Fabian. (2023). Ontologies in the era of large language models – a
  perspective. Applied Ontology. 18. 399-407. 10.3233/AO-230072. 
* [4] Hamed Babaei Giglou etc., LLMs4OL: Large Language Models for Ontology
  Learning, https://arxiv.org/abs/2307.16648
