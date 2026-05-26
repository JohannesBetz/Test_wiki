---
tags: [technique]
date: 2026-05-06
sources: 5
---

# Model Predictive Control

## Definition

Model predictive control repeatedly solves a finite-horizon optimization problem, applies the first control action, then replans from the updated vehicle state.

## Key Approaches

In [[autonomous_vehicles_on_the_edge]], MPC is central to both [[autonomous_racing_planning]] and [[autonomous_racing_control]]. Variants include NMPC, MPPI, stochastic MPC, sparse randomized MPC, LPV-MPC, tube MPC, learning MPC, envelope control, and MPC combined with game theory, Gaussian processes, DNNs, and reinforcement learning.

[[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]] is relevant to MPC because [[g_g_g_v_diagrams]] can provide compact acceleration-envelope constraints. This lets an MPC formulation respect near-limit vehicle behavior derived from high-fidelity simulation without directly embedding the full black-box model in the optimizer.

[[kineto_dynamical_planning_and_accurate_execution_of_minimum_time_maneuvers_on_three_dimensional_circuits]] shows a different MPC role: economic NMPC itself becomes the online minimum-time planner, using a learned kineto-dynamical model and 3D-aware acceleration constraints rather than only tracking a precomputed reference.

[[alpha_racer_real_time_algorithm_for_game_theoretic_motion_planning_and_control_in_autonomous_racing_using_near_potential_function]] shows MPC in a multi-agent tactical role. There, MPC does not decide the full competitive strategy by itself; instead, it tracks a raceline-derived reference whose overtaking and blocking geometry is selected online through [[dynamic_near_potential_functions]].

[[lipschitz_regularized_learned_dynamics_for_autonomous_racing_mpc]] adds a model-learning compatibility view: when learned dynamics are embedded inside racing MPC, regularity of the model itself becomes part of controller design, not just an offline regression detail.

[[real_time_neural_mpc_deep_learning_model_predictive_control_for_quadrotors_and_agile_robotic_platforms]] adds a controller-distillation view: when online MPC is too slow for aggressive platforms, a neural surrogate can approximate the MPC policy and recover much of its behavior at far lower runtime cost.

[[one_model_to_drift_them_all_physics_informed_conditional_diffusion_model_for_driving_at_the_limits]] adds an adaptation-under-uncertainty view: MPC remains the execution layer, but the prediction model is conditioned online through a diffusion-based generator so the controller can switch across latent vehicle-and-surface regimes while drifting at the handling limit.

[[risk_averse_model_predictive_control_for_racing_in_adverse_conditions]] adds a tail-risk view: when friction and tire parameters are uncertain, MPC can optimize against worst-plausible outcomes through a sample-based `CVaR` formulation rather than planning only for a nominal dynamics model.

[[learning_terrain_aware_kinodynamic_model_for_autonomous_off_road_rally_driving_with_model_predictive_path_integral_control]] adds a terrain-adaptive sampling-based view: when vehicle dynamics shift with the surface itself, [[model_predictive_path_integral_control]] can use a learned terrain-aware kinodynamic model to keep aggressive control online in off-road rally settings.

[[robust_spatiotemporal_motion_planning_for_multi_agent_autonomous_racing_via_topological_gap_identification_and_accelerated_mpc]] adds an interaction-aware planning view: MPC is used not only for tracking or nominal local optimization, but as an accelerated execution layer inside a planner that first selects a topologically meaningful space-time gap among nearby racing agents.

[[strategizing_at_speed_a_learned_model_predictive_game_for_multi_agent_drone_racing]] adds an aerial interaction-game view: MPC-style receding-horizon reasoning can also serve as the backbone of a learned real-time game for multi-agent drone racing, where the main difficulty is not only feasibility but fast strategic response to other agile agents.

[[highly_dynamic_quadruped_locomotion_via_whole_body_impulse_control_and_model_predictive_control]] adds a legged-robotics view: MPC can plan reaction-force profiles for a quadruped while a whole-body controller realizes those forces through aerial phases and rapid contact transitions.

[[perceptive_locomotion_through_nonlinear_model_predictive_control]] adds a terrain-aware legged view: nonlinear MPC can also absorb perception directly when locally approximated terrain-feasibility constraints are embedded into the optimizer, allowing the controller to reason about footholds and body motion together in real time.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]]
- [[kineto_dynamical_planning_and_accurate_execution_of_minimum_time_maneuvers_on_three_dimensional_circuits]]
- [[alpha_racer_real_time_algorithm_for_game_theoretic_motion_planning_and_control_in_autonomous_racing_using_near_potential_function]]
- [[lipschitz_regularized_learned_dynamics_for_autonomous_racing_mpc]]
- [[real_time_neural_mpc_deep_learning_model_predictive_control_for_quadrotors_and_agile_robotic_platforms]]
- [[one_model_to_drift_them_all_physics_informed_conditional_diffusion_model_for_driving_at_the_limits]]
- [[risk_averse_model_predictive_control_for_racing_in_adverse_conditions]]
- [[learning_terrain_aware_kinodynamic_model_for_autonomous_off_road_rally_driving_with_model_predictive_path_integral_control]]
- [[highly_dynamic_quadruped_locomotion_via_whole_body_impulse_control_and_model_predictive_control]]
- [[perceptive_locomotion_through_nonlinear_model_predictive_control]]

## Open Problems

MPC for racing must handle nonlinear vehicle/tire dynamics, long enough horizons for feasibility and interaction, real-time solve times, uncertainty, changing friction, and safety constraints without becoming too conservative for racing performance.

Alpha-RACER adds a multi-agent coupling challenge: once MPC is embedded inside a higher-level game, the overall system depends not only on controller solve time but also on whether the strategic parametrization is rich enough to express useful racecraft.

Lipschitz-regularized learned dynamics add a model-quality challenge: even a statistically accurate learned model may be a poor MPC prediction model if its local sensitivity makes the optimizer unstable or overly brittle.

Neural MPC adds a runtime-fidelity challenge: a learned surrogate may solve the compute bottleneck, but it raises the question of how much true MPC behavior is preserved when operating off distribution or near hard constraints.

Diffusion-conditioned drifting adds an adaptation challenge: if the controller depends on online inference over latent dynamics modes, MPC performance may hinge as much on fast regime identification and multimodal model selection as on the optimizer itself.

Risk-averse racing adds an objective-design challenge: even a fast optimizer with expressive models can fail if the cost and constraints do not adequately represent low-probability but high-consequence loss-of-control events.

Terrain-aware MPPI adds a model-environment challenge: if the effective dynamics vary with the surface, controller quality depends on whether the terrain-conditioned model adapts fast enough for the optimizer to stay useful.

The quadruped MPC example adds a realization challenge: even if the predictive layer is strong, the architecture only works if the lower whole-body controller can execute the planned forces quickly and robustly through violent contact changes.

Perceptive NMPC adds a terrain-abstraction challenge: perception may provide richer information than the optimizer can afford to use directly, so the choice of local terrain constraints becomes part of controller design rather than a mere preprocessing detail.
