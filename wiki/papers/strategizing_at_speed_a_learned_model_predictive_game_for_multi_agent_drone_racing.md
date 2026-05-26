---
tags: [paper]
date: 2026-05-20
task: autonomous_drone_racing
venue: "arXiv"
sources: 1
year: "2026"
doi: "10.48550/arXiv.2602.06925"
url: "https://doi.org/10.48550/arXiv.2602.06925"
topic:
  - autonomous_drone_racing
  - highly_dynamic_autonomy
tech_backbone: [model_predictive_control]
tech_representation: [learned_model_predictive_game]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [drones]
simulators_used: []
---

# Strategizing at Speed: A Learned Model Predictive Game for Multi-Agent Drone Racing

> Strategizing at Speed: A Learned Model Predictive Game for Multi-Agent Drone Racing | arXiv 2026 | Andrei-Carlo Papuc, Lasse Peters, Sihao Sun, Laura Ferranti, and Javier Alonso-Mora | DOI: 10.48550/arXiv.2602.06925

## Summary

This paper appears to tackle a missing piece in autonomous drone racing: how to perform short-horizon strategic reasoning against other drones without giving up the real-time responsiveness needed for agile flight.

Its answer, as stated by the title, is a learned model predictive game.

## Method

The paper's central idea is captured here as [[learned_model_predictive_game]].

At a high level, the method appears to combine:

- model-predictive short-horizon planning,
- explicit multi-agent game structure,
- and learned components that likely accelerate or regularize the resulting interaction model enough for high-speed deployment.

This makes the paper a natural bridge between:

- [[multi_agent_time_optimal_motion_planning]], which emphasizes coordinated multi-drone speed,
- [[learning_multipursuit_evasion_for_safe_targeted_navigation_of_drones]], which emphasizes adversarial aerial interaction,
- and game-theoretic racing work on ground vehicles, where strategic interaction is already treated as part of the planning problem.

## Key Result

At the vault level, the key result is conceptual:

**multi-agent drone racing may need explicit real-time strategic game reasoning, not only fast trajectory generation or learned reactive policies.**

That matters because close aerial racing is not only about flying a good path. It is also about choosing how to exploit, deny, or reshape shared space under severe timing pressure.

## Hardware Used

- [[drones]]


## Related Work

Compared with [[dashing_for_the_golden_snitch_multi_drone_time_optimal_motion_planning_with_multi_agent_reinforcement_learning]], this paper likely leans more toward explicit predictive game structure and less toward coordination through pure multi-agent RL.

Compared with [[alpha_racer_real_time_algorithm_for_game_theoretic_motion_planning_and_control_in_autonomous_racing_using_near_potential_function]], the overlap is clear: both papers treat racing as a real-time interaction game. The likely difference is embodiment and modeling emphasis, with this paper targeting agile aerial racing rather than racecar maneuver shaping.

Compared with [[real_time_neural_mpc_deep_learning_model_predictive_control_for_quadrotors_and_agile_robotic_platforms]], it likely shifts focus from making one controller fast enough for agile flight to making multi-agent strategic interaction itself fast enough.

## Notes / Critique

The strongest idea is the combination of learned acceleration with explicit strategic structure. That gives the method a more interpretable interaction story than pure learned policy approaches while still acknowledging the compute limits of real drone racing.

The main caveat of this ingest is practical: the metadata was clear, but I did not have a convenient full-text extraction path in this workspace, so this note is intentionally careful and should be deepened later with fuller access to the paper text.
