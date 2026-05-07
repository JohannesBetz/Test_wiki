---
tags: [model]
date: 2026-05-07
sources: 1
---

# CSDAL

## Definition

CSDAL, Cognitive Skill Distillation and Alternating Learning, is the autonomous-racing policy framework introduced in [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]].

## Key Approaches

- Base learner: [[soft_actor_critic]].
- Expert-data teacher model trained from rFactor 2 driver-in-the-loop laps.
- [[hippocampal_inspired_skill_consolidation_and_distillation]] for memory-node selection, periodic review, and temporal feature distillation.
- [[alternating_phases_curriculum_learning]] for alternating reverse and forward curriculum phases.
- Residual action formulation around an expert reference line and velocity profile.
- Lower-level NMPC trajectory tracking.

## Representative Papers

- [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]]

## Open Problems

CSDAL depends on expert demonstrations and track-specific expert references. A central open problem is making the method generalize to novel tracks without prior expert laps.
