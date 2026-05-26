---
tags: [technique]
date: 2026-05-26
sources: 2
---

# Perceptive Locomotion

## Definition

Perceptive locomotion uses exteroceptive sensing such as depth, terrain maps, or other look-ahead observations to shape locomotion behavior before contact, instead of relying only on proprioceptive reaction after the robot has already touched the terrain.

## Key Approaches

In [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], perceptive locomotion is implemented through an attention-based recurrent encoder that fuses proprioceptive state with height samples from a robot-centric elevation map. A privileged teacher policy is learned in simulation and then distilled into a student policy that acts from noisy deployment-like observations on a physical quadruped.

In [[perceptive_locomotion_through_nonlinear_model_predictive_control]], perceptive locomotion is implemented from the opposite direction: terrain perception is distilled into local geometric and steppability constraints that can be embedded directly into an online nonlinear MPC problem.

In [[attention_based_map_encoding_for_learning_generalized_legged_locomotion]], perceptive locomotion is implemented through a learned [[attention_based_map_encoding|attention-based terrain encoder]] conditioned on proprioception, so the controller can focus selectively on terrain structure that matters for future motion.

In [[beamdojo_learning_agile_humanoid_locomotion_on_sparse_footholds]], perceptive locomotion appears in a humanoid sparse-foothold setting: a learned locomotion policy is paired with an onboard LiDAR-based elevation-map pipeline so precise terrain information can guide foot placement on real hardware.

In [[legged_locomotion_in_challenging_terrains_using_egocentric_vision]], perceptive locomotion appears in a more compact visual form: egocentric camera input is sufficient to help drive terrain-aware quadruped locomotion over challenging surfaces without a heavy explicit mapping stack.

In [[pie_parkour_with_implicit_explicit_learning_framework_for_legged_robots]], perceptive locomotion appears in a parkour-centric form: noisy egocentric depth sensing is paired with dual-level implicit-explicit estimation so a low-cost quadruped can traverse harsh obstacle terrain without relying on a heavyweight terrain-reconstruction module.

In [[extreme_parkour_with_legged_robots]], perceptive locomotion appears in an even more aggressive end-to-end parkour form: a single policy acts directly from front-facing depth images to execute extreme jumps and maneuvers on a low-cost quadruped with noisy sensing and imprecise actuation.

In [[learning_humanoid_locomotion_with_perceptive_internal_model]], perceptive locomotion is implemented through the [[perceptive_internal_model]] (PIM) by concatenating exteroceptive elevation maps directly into the state predictor. This enables high-efficiency, single-stage RL training in under 3 hours while achieving over 90% success rate on continuous stair climbing on physical Unitree H1 and Fourier GR-1 humanoids.

For this vault, the main point is not just that perception is present, but that perception becomes directly control-relevant. The controller learns when exteroceptive information is trustworthy enough to help and when it must fall back on more conservative embodied cues.

## Representative Papers

- [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]]
- [[perceptive_locomotion_through_nonlinear_model_predictive_control]]
- [[attention_based_map_encoding_for_learning_generalized_legged_locomotion]]
- [[beamdojo_learning_agile_humanoid_locomotion_on_sparse_footholds]]
- [[legged_locomotion_in_challenging_terrains_using_egocentric_vision]]
- [[pie_parkour_with_implicit_explicit_learning_framework_for_legged_robots]]
- [[extreme_parkour_with_legged_robots]]
- [[learning_humanoid_locomotion_with_perceptive_internal_model]]

## Open Problems

Perceptive locomotion is hardest exactly where it matters most: snow, dust, reflective surfaces, missing depth, pose drift, and other failures can make the exteroceptive signal incomplete or misleading right when the robot is moving fast.

That creates a sharp design question for the vault: how should a high-dynamic embodied system decide when to trust perception, when to discount it, and when to hand more authority back to adaptation or reactive control?

The Grandia paper adds a control-structure version of the same question: if perception enters through optimization constraints rather than through a learned policy, how should those constraints remain both computationally light and faithful to messy terrain?

The He paper adds a representation question: if perception enters through learned attention, what evidence shows the network is focusing on truly transferable terrain structure rather than dataset-specific visual shortcuts?

PIE adds an estimation-design question: if one parkour controller uses both implicit and explicit estimation, what is the right split between the information the policy should infer for itself and the structure the system should preserve explicitly under noisy sensing?

Extreme Parkour adds a hardware-tolerance question: if a low-cost robot can perform extreme maneuvers from noisy depth alone, what minimum sensing and actuation quality is actually necessary before explicit structure becomes worth the extra complexity?

PIM adds a rendering-vs-prediction question: if elevation maps can be integrated directly into a self-supervised state predictor to bypass simulator depth-rendering constraints, how far can we push prediction-based exteroception before explicit geometric reconstruction becomes mathematically necessary?
