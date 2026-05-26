---
tags: [paper]
date: 2026-05-07
task: autonomous_racing
venue: "arXiv"
sources: 1
year: "2026"
eprint: "2603.05842"
url: "https://arxiv.org/abs/2603.05842"
topic:
  - autonomous_racing
  - end_to_end_autonomous_racing
  - autonomous_racing_control
tech_backbone: [reinforcement_learning]
tech_representation: []
tech_generation: [trajectory_guided_dynamics_constrained_reinforcement_learning]
tech_conditioning: [curriculum_learning]
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [cars_and_race_cars]
simulators_used: []
---

# Expert Knowledge-driven Reinforcement Learning for Autonomous Racing via Trajectory Guidance and Dynamics Constraints

> Expert Knowledge-driven Reinforcement Learning for Autonomous Racing via Trajectory Guidance and Dynamics Constraints | arXiv:2603.05842 | Leng, Zhang, Li, Xiong, Jin, Yu, and Lv

## Summary

This paper proposes `TraD-RL`, a reinforcement-learning framework for autonomous racing that uses expert prior knowledge to stabilize learning and improve safety. The key idea is that pure trial-and-error RL is too sample-inefficient and too unsafe for high-dynamics racing, so the policy should be guided by an expert racing line and bounded by explicit dynamics constraints.

The paper targets a familiar failure mode in racing RL: policies can learn aggressive but unstable behaviors, or waste training time exploring obviously poor parts of the state-action space. `TraD-RL` addresses that by narrowing exploration without removing the possibility of surpassing the expert baseline.

## Method

The method has three coupled components.

First, it uses a prior expert racing line to construct an augmented state representation and shape the reward. This gives the policy a structured notion of where the fast path likely is and helps stabilize early learning.

Second, it injects explicit vehicle-dynamics priors through a safe operating envelope formulated with control barrier functions. The paper emphasizes yaw-rate and sideslip regulation, using the constraints to keep the learned behavior within a physically meaningful handling region.

Third, it applies multi-stage curriculum learning. The policy first learns under stronger expert guidance, then progressively shifts toward more autonomous exploration. The point of this schedule is to keep early learning stable while still allowing later performance to surpass expert-level behavior.

## Key Results

The paper evaluates `TraD-RL` in a high-fidelity simulator modeled after the Berlin Tempelhof Airport Street Circuit. The reported outcome is a joint improvement in lap speed and driving stability.

The ablation study is the most informative part. According to the authors, trajectory guidance prevents conservative local optima and improves exploration efficiency, while the dynamics-constraints module suppresses hazardous behaviors such as excessive yaw rate, large sideslip, and tail-happy instability.

The conclusion frames the result as a synergistic performance-safety optimization: guidance helps the policy find faster solutions, and explicit constraints keep those solutions inside a safe dynamic envelope.

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

This paper sits between several threads already in the vault. It shares the RL orientation of [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]] and [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]], but it differs by injecting stronger structured priors into the learning loop.

It also connects to learning-based control work such as [[learning_based_model_predictive_control_for_autonomous_racing]] and error-learning MPC methods, but replaces online optimization with a learned racing policy that is still shaped by explicit dynamics envelopes.

In spirit, it is also close to safety-aware racing RL such as the Evans high-speed racing work cited in the paper, but adds the extra ingredient of explicit expert-trajectory guidance.

## Notes / Critique

The strongest design choice is the combination of priors. The method does not rely on reward shaping alone; it changes state design, exploration structure, and safety enforcement together.

A likely limitation is transfer. The stronger the method depends on a specific expert line and specific envelope formulation, the more carefully it may need to be retuned when the track, tire model, or perception stack changes.
