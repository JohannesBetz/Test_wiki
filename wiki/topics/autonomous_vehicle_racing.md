---
tags: [topic]
date: 2026-05-06
sources: 7
---

# Autonomous Vehicle Racing

## Definition

Autonomous vehicle racing studies autonomous racecars operating near the limits of handling, where high speed, high acceleration, low reaction time, uncertain sensing, nonlinear tire dynamics, and adversarial interaction become first-order problems.

In [[autonomous_vehicles_on_the_edge]], the scope is restricted to four-wheeled racecars and racecar-like platforms, including small-scale vehicles, full-size racecars, and racing simulators.

## Key Approaches

- Classical autonomy pipeline: [[high_speed_perception]] -> [[autonomous_racing_planning]] -> [[autonomous_racing_control]].
- Classical autonomy pipeline: [[high_speed_perception]] -> [[autonomous_racing_planning]] -> [[autonomous_racing_control]], which can also be read through the broader [[cognitive_navigation]] lens of perception-decision-execution coupling.
- Optimization and optimal-control approaches for raceline generation and minimum-lap-time objectives.
- [[model_predictive_control]] for local planning, tracking, robustness, and operation near dynamic limits.
- Learning-based control, especially repeated-lap learning and model-error compensation.
- [[end_to_end_autonomous_racing]] using deep learning and [[reinforcement_learning]].
- Multi-agent learned racing policies such as [[gt_sophy]] that combine speed, tactics, and [[racing_etiquette]].
- Expert-guided learned policies such as [[csdal]] that combine [[knowledge_distillation]], [[curriculum_learning]], and RL for lap-time improvement.
- Human-expertise studies such as [[professional_race_driver_expertise]], which translate driver limit detection and exploration strategies into autonomous racing design goals.
- Online performance-envelope learning systems such as [[apex]], which adapt local planning and control constraints from observed system response.
- Vehicle-dynamics constraint maps such as [[g_g_g_v_diagrams]], which turn high-fidelity simulation into acceleration envelopes for planners and controllers.
- Spatial grip maps such as [[gripmap]], which make those constraints track-position-dependent for offline and online planning.
- Platform-driven evaluation through [[f1tenth]], [[formula_student_driverless]], [[roborace]], [[indy_autonomous_challenge]], and simulation.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]
- [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]]
- [[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]]
- [[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]]
- [[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]]
- [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]]

## Open Problems

- High-speed perception and sensor fusion.
- Multi-vehicle trajectory planning.
- Multi-agent prediction and interaction.
- Adversarial driving and risk-aware behavior.
- Real-time vehicle dynamics modeling.
- Balancing safety and lap-time performance.
- Common autonomous racing rules and regulations.
- Real-time full-stack software performance.
- Racing-specific sensors, compute, and high-speed hardware.
- Spatially resolved grip estimation and adaptation under changing track conditions.
- Translating professional driver intuition, limit detection, and exploration into autonomous software modules.
