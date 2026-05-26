---
tags: [technique]
date: 2026-05-07
sources: 2
---

# Sim-to-Real Transfer

## Definition

Sim-to-real transfer moves policies, models, or controllers trained in simulation onto physical systems despite mismatches in sensing, dynamics, latency, and environment appearance.

## Key Approaches

In [[champion_level_drone_racing_using_deep_reinforcement_learning]], sim-to-real transfer is handled by fitting empirical residual models from real-world rollouts and injecting those residuals into simulation before fine-tuning the policy. This differs from broad domain randomization: the simulator is made more realistic using short, targeted real-world experience on the race track.

In [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]], sim-to-real transfer relies on noisy sensor histories, simulator noise models, physics perturbations, and an [[asymmetric_actor_critic]] setup where the critic learns from privileged simulator truth while the policy learns to act from deployment-like observations.

[[rapid_locomotion_via_reinforcement_learning]] adds a legged-robotics pattern: transfer is supported by online system identification so the simulated training regime stays better aligned with the physical quadruped as locomotion becomes more aggressive.

[[rma_rapid_motor_adaptation_for_legged_robots]] adds another legged-robotics pattern: the sim-to-real gap is reduced not only through better training conditions, but through a runtime adaptation module that can absorb hidden dynamics changes after deployment.

[[hybrid_internal_model_learning_agile_legged_locomotion_with_simulated_robot_response]] adds an internal-modeling legged pattern: transfer can also be supported by learning a disturbance-aware internal response representation from minimal sensing, rather than by relying primarily on richer terrain observations.

[[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]] adds a perception-heavy transfer pattern: the policy is trained through a privileged teacher-student pipeline so the deployment controller can act from noisy terrain observations and proprioception without requiring perfect sensing on hardware.

[[learning_visual_parkour_from_generated_images]] adds a generated-visual-world transfer pattern: instead of only randomizing simulator parameters or fitting dynamics residuals, the training pipeline synthesizes diverse and physically accurate egocentric image sequences so an RGB-only visual parkour policy transfers zero-shot to hardware.

## Representative Papers

- [[champion_level_drone_racing_using_deep_reinforcement_learning]]
- [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]
- [[rapid_locomotion_via_reinforcement_learning]]
- [[rma_rapid_motor_adaptation_for_legged_robots]]
- [[hybrid_internal_model_learning_agile_legged_locomotion_with_simulated_robot_response]]
- [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]]
- [[learning_visual_parkour_from_generated_images]]

## Open Problems

The main challenge is learning enough about real-world error modes without requiring so much track-specific data that the method loses generality. Appearance changes, sensing failures, actuator degradation, and opponent interactions remain difficult to simulate faithfully.

Quadruped rapid locomotion adds another version of the same problem: when speeds rise, even small dynamics mismatches can destabilize the gait, so transfer procedures must keep up with the robot's growing agility rather than only with nominal walking behavior.

RMA adds a more adaptive version: instead of expecting the simulator to account for every deployment condition in advance, the controller can learn to infer and compensate for hidden changes online.

Hybrid Internal Model adds a representation version: if transfer depends on learning a better internal response model, how robust is that learned representation when the real-world disturbance patterns differ from those seen in simulation?

Perceptive locomotion adds a sensing-gap version: transfer is no longer only about dynamics mismatch, but also about whether the policy has learned to stay useful when terrain perception is incomplete, delayed, or misleading in the real world.

Visual parkour from generated images adds a generated-appearance version: if the visual world itself is synthesized, how do we know when the generated diversity is genuinely helping transfer and when it is introducing subtle artifacts the robot quietly overfits to?
