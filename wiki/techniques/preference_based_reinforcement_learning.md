---
tags: [technique]
date: 2026-05-26
sources: 1
---

# Preference-Based Reinforcement Learning

## Definition

Preference-Based Reinforcement Learning (`PbRL`) is a reinforcement learning technique where the agent learns a control policy from pairwise human preference feedback (comparing two trajectories and indicating which is better), rather than relying on a manually designed reward function.

## Key Approaches

In *Learning Acrobatic Flight from Preferences*, `PbRL` is applied to train controllers for quadrotor drone acrobatics. To handle the uncertainty and inconsistencies in human feedback, the authors introduce Reward Ensemble under Confidence (REC), which models per-step reward uncertainty through an ensemble of distributional reward models. This enables zero-shot sim-to-real transfer of complex acrobatics (such as power loops and barrel rolls) learned purely from preference data.

This technique is highly relevant for the vault because:

**manually designed rewards for agile tasks often fail to capture the qualitative details of smooth, stable, and natural motion (agreeing with human judgment only ~60% of the time).**

PbRL provides a way to align neural control policies with human expertise without manual tuning.

It belongs naturally near [[reinforcement_learning]] and [[professional_race_driver_expertise]].

## Representative Papers

- *Learning Acrobatic Flight from Preferences*

## Open Problems

Open problems include:
- **Sample Inefficiency**: Human preference feedback is expensive to collect, requiring methods that can learn from minimal queries.
- **Feedback Noise**: Human experts can make mistakes, have inconsistent criteria, or experience fatigue, corrupting the preference dataset.
- **Exploration**: How to encourage the agent to explore novel states to present interesting trajectory pairs to the human supervisor without risking system damage.
