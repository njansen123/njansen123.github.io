---
layout: page
title: Uncertain POMDPs
description: Provably Correct Policies for Uncertain POMDPs. NWO Open Competition ENW Klein.
img: assets/img/upomdps.png
importance: 1
category: work
---

Recent years have seen a rapid progress in artificial intelligence (AI) and machine learning with a strong impact to fields like autonomous systems, computer vision, or robotics. As a consequence, many systems employing AI show an increasing interaction with aspects of our everyday life, consider autonomous cars operating amongst pedestrians and bicycles. Such applications necessitate safety considerations for AI decision-making to avoid harmful behavior. Formal verification subsumes a plethora of techniques that provide guarantees on system behavior, based on clear semantics for reasoning about correctness. In particular, model checking is a rigorous verification technique that assess correctness of a well-defined system model with respect to specifications, for instance given as temporal logic constraints. AI systems, though, often operate in unknown or unpredictable environments, coping with contextual changes at runtime and incompleteness of information. This variability and unpredictability in the underlying models has so far restricted the usefulness of model checking to AI systems.
We propose to improve the state-of-the-art in the synergy between model checking and AI by devising verification and synthesis methods for a specific type of problems. A typical model, prominent in both research communities, to capture uncertainty and partial information is a partially observable Markov decision process (POMDP). We consider an extension where probabilities are not exactly known but are captured by so-called uncertainty sets, for instance in the form of probability intervals. In general, we propose to employ model checking techniques among other based on convex optimization and parameter synthesis to address the following key challenges:

* Determine policies for uncertain POMDPs that provably adhere to formal specifications.
* Augment reinforcement learning for uncertain POMDPS such that decision-making respects specifications during the exploration of an environment.

For both challenges we will investigate tradeoffs between finite memory and randomization in policies. Techniques stemming from this project will be disseminated as part of a publicly available toolset and evaluated on case studies collected by the formal methods and the AI communities.