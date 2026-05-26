---
tags: [technique]
date: 2026-05-22
sources: 1
---

# Attention-Based Map Encoding

## Definition

Attention-based map encoding learns a selective terrain representation in which the controller attends to the most control-relevant parts of a local map rather than consuming the entire terrain observation uniformly.

## Key Approaches

In [[attention_based_map_encoding_for_learning_generalized_legged_locomotion]], the terrain encoder is conditioned on robot proprioception and trained jointly with the locomotion policy through [[reinforcement_learning]]. The goal is to preserve the robustness of learning-based locomotion while improving precision on sparse and structured terrain.

For this vault, the important point is that perception quality is partly a representation problem: the system may fail not because it lacks a terrain map, but because it does not know where to focus within that map.

## Representative Papers

- [[attention_based_map_encoding_for_learning_generalized_legged_locomotion]]

## Open Problems

Attention-based terrain encoders make perceptive locomotion more selective, but they also raise a key question: does the policy attend to terrain features because they are truly control-relevant, or because they correlate with success on the training distribution in a way that may break under new embodiments or terrain styles?
