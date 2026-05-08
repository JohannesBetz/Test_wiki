---
tags: [paper]
date: 2026-05-08
task: autonomous_racing
venue: "Neural Computing and Applications"
sources: 1
year: "2025"
doi: "10.1007/s00521-025-11597-5"
topic:
  - autonomous_racing
  - end_to_end_autonomous_racing
  - autonomous_racing_simulation
tech_backbone: [reinforcement_learning]
tech_representation: []
tech_generation: [track_agnostic_reinforcement_learning]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
simulators_used: []
---

# Enhancing Generalization in Autonomous Driving Through Track-Agnostic Reinforcement Learning

> Enhancing Generalization in Autonomous Driving Through Track-Agnostic Reinforcement Learning | Neural Computing and Applications 2025 | Jean-Baptiste Authier-Carcelen and Rubina Zadourian

## Summary

This paper targets a narrow but important failure mode in learned racing and driving systems: dependence on explicit track geometry. Many strong RL agents use centerlines, future curvature samples, or other track-specific priors, which makes them fast on known tracks but less transferable to unseen ones.

The authors propose a track-agnostic RL framework intended to preserve competitive driving performance while enabling zero-shot transfer to new track layouts.

## Method

The core idea is [[track_agnostic_reinforcement_learning]]. The paper trains PPO policies without supplying explicit racetrack information such as centerlines.

Instead, the policy learns from:

- structured sensor observations in a 2D environment, including Lidar and speed-related signals,
- or fused raw image pixels plus physics-based features in a 3D TrackMania environment.

The key design choice is an asymmetry-based reward. Rather than rewarding progress relative to a predefined centerline, the reward penalizes geometric asymmetry in the current observation, which acts as a proxy for poor track centering and poor local orientation. This gives the policy a track-independent training signal.

The paper therefore aims at a different robustness problem than [[out_of_distribution_generalization_with_a_sparc_racing_100_unseen_vehicles_with_a_single_policy]]. SPARC adapts to unseen hidden vehicle contexts, while this paper tries to avoid overfitting to the geometry of the training track itself.

## Key Results

In the 2D environment, PPO outperforms SAC, DDPG, and A2C on the authors' benchmark and achieves lap times essentially identical to a track-specialized baseline on the training track.

On three unseen 2D tracks, the same trained agent completes all tracks and remains close to track-specialized agents, with the largest reported lap-time gap about 6.6 percent on the most novel geometry.

Ablation results show that removing the asymmetry reward substantially hurts transfer to unseen tracks, dropping completion rates sharply on the harder alternatives.

In the 3D TrackMania evaluation, the zero-shot agent completes 5 out of 5 unseen official tracks, with near-100 percent average completion on the easiest map and lower completion on more obstacle-heavy tracks. After fine-tuning, the method reaches lap times comparable to average human players on 3 of 4 evaluated tracks and beats the average-player benchmark on one.

## Related Work

This paper belongs near [[end_to_end_autonomous_racing]] because it studies learned policies that rely less on hand-coded geometry priors and more on direct sensory input. It also fits [[autonomous_racing_simulation]], since all evidence comes from simulation environments ranging from a custom 2D setup to TrackMania.

Compared with [[a_champion_level_vision_based_reinforcement_learning_agent_for_competitive_racing_in_gran_turismo_7]], this work is less about champion-level performance and more about transfer across unseen tracks. Compared with [[out_of_distribution_generalization_with_a_sparc_racing_100_unseen_vehicles_with_a_single_policy]], it studies geometric transfer across tracks rather than latent dynamics adaptation across vehicles.

## Notes / Critique

The strongest contribution is conceptual cleanliness. The paper removes a common hidden crutch in racing RL and then measures what remains when the agent must infer the local track structure from current observations alone.

The main weakness is that the most impressive generalization claims still live in simulation and mostly in time-trial-style settings. The paper says less about opponent interaction, real-world sensing, or whether the asymmetry reward remains stable in noisier physical environments.
