---
tags: [topic]
date: 2026-05-13
sources: 1
---

# Autonomous Drifting

## Definition

Autonomous drifting studies vehicle control beyond the normal stability envelope, where large sideslip angles are intentional and the controller must coordinate path tracking, yaw regulation, tire-force saturation, and recovery margins at the same time.

## Key Approaches

Early drifting work in the vault is mostly controller-centric:

- [[analysis_and_control_of_high_sideslip_manoeuvres]] frames the problem around high-sideslip stability and controllability.
- [[a_controller_framework_for_autonomous_drifting_design_stability_and_experimental_validation]] develops a dedicated autonomous drifting control framework.
- [[simultaneous_stabilization_and_tracking_of_basic_automobile_drifting_trajectories]] and [[a_controller_for_automated_drifting_along_complex_trajectories]] focus on making drifting trajectories both trackable and stabilizable.
- [[toward_automated_vehicle_control_beyond_the_stability_limits_drifting_along_a_general]] pushes drifting from canonical maneuvers toward more general path-following.

The learning branch is newer:

- [[high_speed_autonomous_drifting_with_deep_reinforcement_learning]] explores whether drifting skill can be learned directly through RL.
- [[one_model_to_drift_them_all_physics_informed_conditional_diffusion_model_for_driving_at_the_limits]] reframes the problem as multimodal online adaptation, using a physics-informed conditional diffusion model inside real-time [[model_predictive_control]] so one system can drift different vehicles under changing conditions.

## Representative Papers

- [[analysis_and_control_of_high_sideslip_manoeuvres]]
- [[a_controller_framework_for_autonomous_drifting_design_stability_and_experimental_validation]]
- [[toward_automated_vehicle_control_beyond_the_stability_limits_drifting_along_a_general]]
- [[high_speed_autonomous_drifting_with_deep_reinforcement_learning]]
- [[one_model_to_drift_them_all_physics_informed_conditional_diffusion_model_for_driving_at_the_limits]]

## Open Problems

Open problems include reliable online estimation of changing tire and surface conditions, cross-vehicle generalization, recovery from failed drift initiation or collapse, computationally feasible control under severe nonlinearity, and connecting spectacular limit-handling demos to broader racing utility rather than isolated drift maneuvers.
