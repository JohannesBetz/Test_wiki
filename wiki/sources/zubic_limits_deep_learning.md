---
tags: [source]
date: 2026-05-08
sources: 1
---

# Zubic Limits Deep Learning Source

> Source: `raw/pdfs/Zubi_Limits_Deep_Learning.pdf`
> Paper: Limits of Deep Learning: Sequence Modeling Through the Lens of Complexity Theory, ICLR 2025

## Summary

This paper studies a basic but uncomfortable question: why do current sequence models still fail on tasks that require multi-step reasoning, function composition, and reliable state tracking, even when prompting tricks appear to help in some cases?

For this vault, the paper is useful because it gives a theoretical and empirical account of the limits of current sequence-model families, especially Transformers and structured state space models (`SSMs`), rather than only reporting another benchmark score.

## Method

The paper combines complexity-theoretic proofs with empirical evaluation. On the theory side, it proves limits for SSMs on function composition and related compositional tasks, and it links multi-layer finite-precision SSMs to weak complexity classes.

Because SSMs and Transformers are closely related in computational expressivity, the authors argue that the results illuminate broader deep-learning limits in sequence reasoning, not only a niche architectural failure.

## Evaluation

The experimental section tests models on function composition, multi-digit multiplication, dynamic programming, and Einstein-style logic puzzles. The paper reports substantial performance degradation as compositional depth rises, even with Chain-of-Thought prompting.

The qualitative pattern is that models often fall back on shallow shortcuts or unstable intermediate reasoning, which leads to compounding errors rather than dependable stepwise problem solving.

## Notes / Critique

The strongest contribution is the combination of formal limits and empirical behavior. That makes the paper much more informative than either a pure theory note or a benchmark-only complaint about reasoning failures.

Its main limitation for this vault is abstraction level. The paper is not about racing or robotics directly, but about the computational ceilings of sequence models that many broader AI systems rely on.

## Pages Created From This Source

- [[limits_of_deep_learning_sequence_modeling_through_the_lens_of_complexity_theory]]
- [[compositional_reasoning_limits_in_sequence_models]]
