---
tags: [topic]
date: 2026-05-08
sources: 1
---

# Compositional Reasoning Limits in Sequence Models

## Definition

Compositional reasoning limits in sequence models refer to the difficulty current architectures have in reliably solving tasks that require chained function composition, state tracking, and multi-step intermediate reasoning.

The issue is not only whether a model can sometimes produce the right answer, but whether it can do so systematically as reasoning depth grows.

## Key Framing

[[limits_of_deep_learning_sequence_modeling_through_the_lens_of_complexity_theory]] frames this as partly a computational problem rather than only a prompting or training problem.

The paper argues that certain model families, including structured state space models and closely related sequence architectures, face basic barriers on composition-heavy tasks unless state size or reasoning steps scale unfavorably.

## Relationship to Foundation Models

This topic sits naturally near [[foundation_models_for_intelligent_decision_making]] and [[era_of_experience]].

Those broader views point toward more capable general decision systems, but this topic highlights a concrete obstacle: large sequence models may still lack the dependable internal machinery for robust step-by-step reasoning, even when they appear fluent or broadly knowledgeable.

## Representative Papers

- [[limits_of_deep_learning_sequence_modeling_through_the_lens_of_complexity_theory]]

## Open Problems

Open problems include how to build models that can carry stable intermediate state across long computations, how to separate genuine reasoning from shortcut exploitation, and whether future systems will need architectural changes rather than only more data, scale, or prompting.
