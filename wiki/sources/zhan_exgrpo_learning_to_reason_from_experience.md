---
tags: [source]
date: 2026-05-27
sources: 1
---

# Zhan ExGRPO Source

> Source: `raw/pdfs/Zhan_LEARNING_TO_REASON FROM_EXPERIENCE.pdf`
> Paper: ExGRPO: Learning to Reason from Experience

## Summary

This source introduces `ExGRPO`, a reasoning-oriented learning method that explicitly treats experience as a training signal for large-model reasoning rather than reserving experience only for embodied agents or reinforcement-learning control policies.

That makes it a useful addition to the vault. Until now, much of the `experience` branch has centered on racing, robotics, and grounded autonomous systems. This paper extends that logic into language-model reasoning itself:

**Can reasoning models improve not just from more static corpora, but from accumulated experience during learning?**

## Method / Framing

The paper frames `experience` as something that can shape reasoning policies over time. The title and method name suggest a deliberate move away from purely static reasoning supervision and toward a reinforcement-learning-style update loop where prior interaction outcomes matter to future reasoning behavior.

For this vault, the important conceptual bridge is that the paper narrows the gap between:

- the [[era_of_experience]] thesis,
- the [[large_language_models]] branch,
- and the broader question of whether foundation models can learn more effectively when experience is treated as a first-class training substrate.

## Relevance

This source is especially relevant to:

- [[era_of_experience]]
- [[large_language_models]]
- [[foundation_models_for_intelligent_decision_making]]
- [[exgrpo]]

It also matters as a counterpoint to [[limits_of_deep_learning_sequence_modeling_through_the_lens_of_complexity_theory]]. That paper warns that current sequence models may have structural reasoning ceilings. ExGRPO does not solve that concern by itself, but it represents one concrete attempt to use experience to strengthen reasoning competence rather than only scaling pretraining.

## Notes / Critique

The most interesting thing about this source is not just the algorithm name. It is the claim that `experience` can become central even in symbolic reasoning pipelines.

The main concern is the same one that appears elsewhere in the vault: if experience is poorly shaped, then the model may reinforce brittle strategies or superficial reward hacks rather than deeper reasoning ability.

## Pages Created From This Source

- [[exgrpo_learning_to_reason_from_experience]]
- [[exgrpo]]
