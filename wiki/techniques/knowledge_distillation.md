---
tags: [technique]
date: 2026-05-07
sources: 1
---

# Knowledge Distillation

## Definition

Knowledge distillation transfers behavior or internal representations from a teacher model to a student model.

## Key Approaches

In [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]], a teacher network is trained on expert driving demonstrations, and a student SAC policy is guided by feature-level temporal distillation through [[hippocampal_inspired_skill_consolidation_and_distillation]].

## Representative Papers

- [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]]

## Open Problems

For racing, the teacher may be imperfect and track-specific. Distillation should help early learning without preventing the student from surpassing expert demonstrations.
