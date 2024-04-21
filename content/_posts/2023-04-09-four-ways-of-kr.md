---
layout: post
title: "Four Ways of Knowledge Representation"
subtitle: ""
date: 2023-04-09
author: "Jamin Chen"
header-img: "img/post-bg-universe.jpg"
tags: ["Cognitive Computing", "Knowledge Representation"]
---

Knowledge representation involves representing the key concepts and relations between the decision variables in some formal manner, typically within a framework suggested by an expert systems shell. Most representation mechanisms must provide support for three aspects of knowledge—conceptual representation, relational representation, and uncertainty representation. As such, four schemes are commonly used for knowledge representation.

## Rule-based representation

Such a scheme represents knowledge in the form of IF… THEN rules. For instance, a rule can be coded as “IF the credit rating of the applicant is poor, THEN do not grant the loan.” The rules are processed through a backward or forward chaining process, or a combination of the two. Rule-based representations allow the inclusion of uncertainty management through the use of confidence factors. Due to their simplicity of representation and ease of use, rule-based representations remain the most
popular representation scheme for expert systems.

## Frame-based representation

Frame-based schemes represent the knowledge in frames that capture descriptive and behavioral information on objects that are represented in the expert system. Because frame-based representations share a lot in common with object-oriented programming, they are powerful representation mechanisms and are increasingly becoming popular.

## Case-based representation

Such representation schemes encode expertise in the form of solved cases from past experience. Characteristics of the problem domain are used to describe these cases. When a new case is presented to the expert system, the representation scheme supports a comparison with stored cases and provides a decision that best represents the closest match based on some distance measure. Case-based representations are most effective when the domain is supported by an adequate number of cases.

## Fuzzy logic representation

A representation using fuzzy rules and sets is similar in nature to rule-based systems with the difference that the rules include statements with fuzzy variables that are assigned fuzzy values. For instance, a rule might be stated in fuzzy terms as “IF the credit rating is very bad, THEN do not approve loan for the next two years.” Fuzzy values are represented mathematically in fuzzy sets. Fuzzy logic is then applied to these rules and sets to process the reasoning. Fuzzy logic is a powerful
representation technique and has yielded performance at par with human operators in certain areas such as control systems.

In general, the representation technique selected must be simple and intuitive to the task domain. Collopy et al. recommend that the representation scheme selected must support full disclosure. In other words, the knowledge coded into the expert system must be simple to understand when examined by a person unfamiliar with the task domain.
