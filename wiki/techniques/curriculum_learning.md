---
tags: [technique]
date: 2026-05-07
sources: 1
---

# Curriculum Learning

## Definition

Curriculum learning structures training tasks from easier to harder, or otherwise controls task exposure, to improve learning efficiency and robustness.

## Key Approaches

For autonomous racing, curriculum learning can help with sparse rewards, long horizons, and difficult cornering or overtaking situations. [[alternating_phases_curriculum_learning]] is one racing-specific form that alternates reverse and forward curriculum phases.

[[mixed_scenario_training]] is another related approach: it keeps a mix of full-task and specialized scenarios present throughout training so important rare skills are retained.

[[rapid_locomotion_via_reinforcement_learning]] adds a legged-robotics example where an adaptive curriculum over velocity commands is one of the key enablers of aggressive learned physical behavior.

## Representative Papers

- [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]]
- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]
- [[rapid_locomotion_via_reinforcement_learning]]

## Open Problems

Useful curricula are often hand-designed and domain-specific. A recurring challenge is making the curriculum adapt automatically to the learner's current ability without overfitting to narrow state distributions.

Rapid quadruped locomotion sharpens that challenge: the curriculum may need to grow aggression without destabilizing the policy or creating brittle dependence on one command distribution.
