---
tags: [topic]
date: 2026-05-26
sources: 14
---

# Highly Dynamic Autonomous System

## Definition

Highly dynamic autonomous systems are autonomous robots or vehicles that operate with high speed, high acceleration, short reaction times, nonlinear dynamics, and tight safety margins.

In hardware terms, this topic cuts across [[cars_and_race_cars]], [[drones]], [[quadrupeds]], and related fast embodied systems.

## Key Approaches

This topic connects [[autonomous_vehicle_racing]] to adjacent agile robotics domains such as drones, humanoids, quadrupeds, and other systems that must perceive, plan, and control near dynamic limits.

[[main_concept_for_high_speed_autonomous_systems]] summarizes the cross-cutting idea that ties these examples together: high-speed autonomy depends on continuously estimating and managing the usable dynamic envelope rather than treating speed as a fixed capability.

[[ranked_top_5_techniques_for_fast_and_agile_autonomy]] adds a second synthesis layer: if one asks which technical families currently look most promising across these examples, adaptive MPC-style limit handling still ranks highest overall, while foundation-model embodied policies remain the strongest long-term speculative bet.

[[erc_idea]] asks a broader strategic question across this whole branch: can experience-driven learning actually produce superhuman autonomous performance in extreme environments, and if so, what safety, evaluation, and architectural constraints would still have to be solved?

[[champion_level_drone_racing_using_deep_reinforcement_learning]] adds a concrete drone-racing example: onboard-only perception, real-time learned control, and sim-to-real transfer on a physical quadrotor racing at champion level.

[[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]] adds a high-fidelity simulator example where real-time control is coupled with human interaction, multi-agent tactics, and imprecise social/sportsmanship rules.

[[outplaying_elite_table_tennis_players_with_an_autonomous_robot]] adds a physical human-robot interaction example: real-time event-based spin perception, learned robot control, safe trajectory generation, and official-rules matches against elite and professional table-tennis players.

[[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]] adds a constraint-awareness example: highly dynamic systems may need spatially local models of what their body, controller, and environment can safely support, not only a global dynamics model.

[[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]] adds a human-skill lens: expert operators often combine multisensory feedback, experience, and rapid exploration to discover the usable dynamic envelope under sparse data.

[[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]] adds a physical-system learning example: [[apex]] learns performance constraints online while keeping exploration bounded by interpretable safety indicators.

[[safety_with_agency_human_centered_safety_filter_with_application_to_ai_assisted_motorsports]] adds a human-in-the-loop safety example: [[human_centered_safety_filter]] shows that highly dynamic autonomy is not only about keeping the machine stable, but also about preserving operator agency and comfort when AI intervenes near failure boundaries.

[[deep_reinforcement_learning_for_robotics_a_survey_of_real_world_successes]] adds a broader robotics comparison: among real-world DRL domains, agile drone racing appears as one of the clearest highly dynamic successes, while many other robotic applications still lag in physical maturity.

[[safety_assured_high_speed_navigation_for_mavs]] adds a complementary non-racing aerial example: [[super]] shows that high-speed autonomy in unknown clutter can be made much safer with long-range 3D LIDAR and [[safety_assured_high_speed_aerial_navigation]], while still exceeding 20 m/s in the real world.

[[how_fast_is_too_fast_the_role_of_perception_latency_in_high]] adds a sensing-bound example: highly dynamic performance may fail not because the controller is weak, but because perception latency and sensing range make the nominal speed target physically unsafe.

[[evaluation_of_driver_reaction_time]] adds a human baseline to that discussion: reaction-critical performance is not only a machine problem, but also a core human limitation in driving tasks, especially once obstacles appear unexpectedly or impairment degrades the perception-action loop.

[[autonomous_drone_racing_a_survey]] adds the broader aerial field map: it treats drone racing as a benchmark where every part of the stack is pushed to the limit simultaneously, making it one of the cleanest laboratories for highly dynamic autonomy.

[[learning_vision_based_pursuit_evasion_robot_policies]] adds an interactive terrestrial example: a visual quadruped pursuer must act under partial observability against an evasive agent, which makes uncertainty management and anticipatory behavior central parts of competent embodied action.

[[high_speed_control_and_navigation_for_quadrupedal_robots_on_complex_and_discrete_terrain]] adds a terrain-dynamics example from legged robotics: a quadruped must keep control and navigation tightly coupled when high speed meets discrete foothold-like terrain rather than smooth continuous motion surfaces.

[[rapid_locomotion_via_reinforcement_learning]] adds a pure agility example from legged robotics: a quadruped can learn to sprint and turn rapidly on natural terrain, which strengthens the claim that high-dynamic embodied competence is not unique to vehicles and drones.

[[highly_dynamic_quadruped_locomotion_via_whole_body_impulse_control_and_model_predictive_control]] adds a predictive-control legged example: highly dynamic quadruped behavior can also be achieved through explicit MPC plus whole-body control, not only through end-to-end learning.

[[rma_rapid_motor_adaptation_for_legged_robots]] adds an online-adaptation legged example: highly dynamic performance may depend on how fast the system can infer hidden terrain and dynamics changes, not only on how fast it can execute one fixed locomotion policy.

[[hybrid_internal_model_learning_agile_legged_locomotion_with_simulated_robot_response]] adds an internal-response legged example: highly dynamic performance may also depend on whether the controller can infer disturbance from the robot's own response, not only from explicit perception or explicit adaptation modules.

[[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]] adds a perception-fusion legged example: highly dynamic behavior may also depend on how effectively the robot can use uncertain terrain information before contact instead of waiting to discover the world only through collisions and slips.

[[perceptive_locomotion_through_nonlinear_model_predictive_control]] adds a structured-control legged example: highly dynamic behavior can also depend on whether perceived terrain can be translated into optimization-compatible constraints quickly enough for a real-time NMPC loop.

[[perceptive_humanoid_parkour_chaining_dynamic_human_skills_via_motion_matching]] adds a humanoid skill-chaining example: highly dynamic behavior may also depend on selecting and transitioning among several aggressive whole-body behaviors fast enough that perception and balance stay coherent through the sequence.

[[real_world_humanoid_locomotion_with_reinforcement_learning]] adds a humanoid real-world RL example: highly dynamic competence is not only a quadruped or drone story, but increasingly a humanoid one as well.

[[learning_humanoid_locomotion_with_perceptive_internal_model]] adds a perceptive-prediction humanoid example: the [[pim]] framework demonstrates that exteroceptive elevation mapping can be concatenated directly with proprioceptive history to achieve robust zero-shot stair climbing and platform traversal on real humanoids, while bypassing depth-map rendering in simulation to train in under 3 hours.

[[humanoid_parkour_learning]] adds a humanoid end-to-end agility example: highly dynamic competence may also emerge from one visuomotor whole-body controller that covers several parkour-like maneuvers rather than only one locomotion regime.

[[beamdojo_learning_agile_humanoid_locomotion_on_sparse_footholds]] adds a humanoid foothold-precision example: highly dynamic competence may also depend on whether the system can place its body exactly where it must under sparse-terrain constraints, not only move quickly across broadly traversable ground.

[[hiking_in_the_wild_a_scalable_perceptive_parkour_framework_for_humanoids]] adds a humanoid wild-terrain example: highly dynamic competence may also depend on whether raw depth perception can support safe fast traversal in open unstructured environments without leaning on heavier mapping stacks.

[[hub_learning_extreme_humanoid_balance]] adds a humanoid stability-margin example: highly dynamic competence may also depend on how little balance margin a system can tolerate while still remaining recoverable under disturbance.

[[kungfubot_physics_based_humanoid_whole_body_control_for_learning_highly_dynamic_skills]] adds a humanoid skill-expression example: highly dynamic competence may also depend on whether a system can track expressive whole-body motions whose difficulty comes from coordination and reference fidelity, not only from forward speed or terrain.

[[physhsi_towards_a_real_world_generalizable_and_natural_humanoid_scene_interaction_system]] adds a humanoid interaction-stack example: highly dynamic embodied competence may also depend on whether a system can keep learned whole-body behavior grounded in a real scene rather than only executing one isolated dynamic skill family.

[[agility_meets_stability_versatile_humanoid_control_with_heterogeneous_data]] adds a humanoid regime-coverage example: highly dynamic competence may also depend on whether one controller can span both agile and stable operating regions instead of forcing the designer to choose one side of that tradeoff.

[[sonic_supersizing_motion_tracking_for_natural_humanoid_whole_body_control]] adds a humanoid motion-foundation example: highly dynamic competence may also depend on whether the whole-body motion-tracking substrate is large enough to support natural, varied humanoid behavior under real deployment constraints.

[[pie_parkour_with_implicit_explicit_learning_framework_for_legged_robots]] adds a quadruped estimation-structure example: highly dynamic competence may also depend on whether state and terrain understanding are split wisely between implicit policy inference and explicit estimation when sensing is noisy.

[[extreme_parkour_with_legged_robots]] adds a quadruped hardware-minimalism example: highly dynamic competence may also depend on whether learning can compensate for noisy sensing and imprecise actuation strongly enough that extreme maneuvers remain possible on low-cost hardware.

[[dreamcontrol_human_inspired_whole_body_humanoid_control_for_scene_interaction_via_guided_diffusion]] adds a humanoid generative-control example: highly dynamic whole-body competence may also depend on whether a guided generative prior can organize scene-interaction behavior more naturally than direct reactive control.

[[beyondmimic_from_motion_tracking_to_versatile_humanoid_control_via_guided_diffusion]] adds a humanoid versatility-transition example: highly dynamic whole-body competence may also depend on whether a motion-tracking substrate can be pushed into a broader and more adaptive control regime instead of remaining narrowly imitative.

[[learning_agile_soccer_skills_for_a_bipedal_robot_with_deep_reinforcement_learning]] adds a bipedal interaction-skill example: highly dynamic competence may also need to coordinate body motion with fast external-object interaction rather than only terrain negotiation.

[[robot_parkour_learning]] adds a quadruped parkour example: highly dynamic competence may also emerge from one vision-based policy that chooses among several obstacle-traversal maneuvers on the fly.

[[agile_but_safe_learning_collision_free_high_speed_legged_locomotion]] adds a quadruped safety-switching example: highly dynamic competence may also depend on whether the system can decide in real time that aggressive control should temporarily yield to recovery control before a collision or failure unfolds.

[[barkour_benchmarking_animal_level_agility_with_quadruped_robots]] adds a quadruped benchmark example: highly dynamic competence also needs common evaluation frames, because otherwise agility claims across controllers and hardware remain hard to compare.

[[animal_gaits_on_quadrupedal_robots_using_motion_matching_and_model_based_control]] adds a quadruped gait-structure example: highly dynamic competence can also depend on how the system selects among motion patterns, not only how it tracks one pattern once chosen.

[[learning_multipursuit_evasion_for_safe_targeted_navigation_of_drones]] adds an aerial multi-agent example: a drone must move fast enough to escape several pursuers while still reaching a target, making strategic adversarial interaction part of the dynamics problem rather than a separate layer above it.

[[real_time_neural_mpc_deep_learning_model_predictive_control_for_quadrotors_and_agile_robotic_platforms]] adds a controller-speed example: on agile platforms, the limiting factor may be not only model quality or sensing, but whether an MPC-quality controller can run fast enough to matter in the loop.

[[risk_averse_model_predictive_control_for_racing_in_adverse_conditions]] adds an uncertainty-management example: highly dynamic autonomy can fail not because the nominal controller is weak, but because rare low-friction regimes are handled as noise instead of as structured tail risk.

[[high_speed_accurate_robot_control_using_learned_forward_kinodynamics_and_non_linear_least_squares_optimization]] adds a modeling-and-optimization example: when high-speed motion violates simplified vehicle assumptions, a learned forward kinodynamic model can be reused across several control objectives instead of retraining a new inverse controller for each task.

[[learning_terrain_aware_kinodynamic_model_for_autonomous_off_road_rally_driving_with_model_predictive_path_integral_control]] adds an environment-adaptive driving example: aggressive control in rally-like terrain can depend on whether the controller carries a terrain-aware dynamics model into its online stochastic optimization loop.

[[a_harmonized_approach_beyond_the_limit_control_for_autonomous_vehicles_balancing_performance_and_safety_in_unpredictable_environments]] adds a co-optimization example: highly dynamic autonomy may fail if performance and safety are designed as separate layers rather than as one coupled beyond-the-limit control problem.

[[llm_and_ai_agents_for_autonomous_systems_a_survey_of_applications_datasets_and_security_challenges]] adds a systems-risk example from the foundation-model side: if agentic models are inserted into autonomous loops, the core issue becomes not only capability but also benchmark quality, security, and whether such agents can be trusted under physical consequence.

[[agile_robot_navigation_through_hallucinated_learning_and_sober_deployment]] adds a deployment-discipline example: highly dynamic autonomy may benefit from aggressive learning regimes, but physical deployment may still require a more conservative execution mode than the one used to generate competence during training.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[champion_level_drone_racing_using_deep_reinforcement_learning]]
- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]
- [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]
- [[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]]
- [[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]]
- [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]]
- [[safety_with_agency_human_centered_safety_filter_with_application_to_ai_assisted_motorsports]]
- [[deep_reinforcement_learning_for_robotics_a_survey_of_real_world_successes]]
- [[safety_assured_high_speed_navigation_for_mavs]]
- [[autonomous_drone_racing_a_survey]]
- [[learning_vision_based_pursuit_evasion_robot_policies]]
- [[high_speed_control_and_navigation_for_quadrupedal_robots_on_complex_and_discrete_terrain]]
- [[rapid_locomotion_via_reinforcement_learning]]
- [[highly_dynamic_quadruped_locomotion_via_whole_body_impulse_control_and_model_predictive_control]]
- [[rma_rapid_motor_adaptation_for_legged_robots]]
- [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]]
- [[perceptive_locomotion_through_nonlinear_model_predictive_control]]
- [[perceptive_humanoid_parkour_chaining_dynamic_human_skills_via_motion_matching]]
- [[real_world_humanoid_locomotion_with_reinforcement_learning]]
- [[humanoid_parkour_learning]]
- [[beamdojo_learning_agile_humanoid_locomotion_on_sparse_footholds]]
- [[hiking_in_the_wild_a_scalable_perceptive_parkour_framework_for_humanoids]]
- [[hub_learning_extreme_humanoid_balance]]
- [[kungfubot_physics_based_humanoid_whole_body_control_for_learning_highly_dynamic_skills]]
- [[physhsi_towards_a_real_world_generalizable_and_natural_humanoid_scene_interaction_system]]
- [[agility_meets_stability_versatile_humanoid_control_with_heterogeneous_data]]
- [[sonic_supersizing_motion_tracking_for_natural_humanoid_whole_body_control]]
- [[pie_parkour_with_implicit_explicit_learning_framework_for_legged_robots]]
- [[extreme_parkour_with_legged_robots]]
- [[dreamcontrol_human_inspired_whole_body_humanoid_control_for_scene_interaction_via_guided_diffusion]]
- [[beyondmimic_from_motion_tracking_to_versatile_humanoid_control_via_guided_diffusion]]
- [[learning_agile_soccer_skills_for_a_bipedal_robot_with_deep_reinforcement_learning]]
- [[robot_parkour_learning]]
- [[agile_but_safe_learning_collision_free_high_speed_legged_locomotion]]
- [[barkour_benchmarking_animal_level_agility_with_quadruped_robots]]
- [[animal_gaits_on_quadrupedal_robots_using_motion_matching_and_model_based_control]]
- [[learning_multipursuit_evasion_for_safe_targeted_navigation_of_drones]]
- [[real_time_neural_mpc_deep_learning_model_predictive_control_for_quadrotors_and_agile_robotic_platforms]]
- [[risk_averse_model_predictive_control_for_racing_in_adverse_conditions]]
- [[high_speed_accurate_robot_control_using_learned_forward_kinodynamics_and_non_linear_least_squares_optimization]]
- [[learning_terrain_aware_kinodynamic_model_for_autonomous_off_road_rally_driving_with_model_predictive_path_integral_control]]
- [[a_harmonized_approach_beyond_the_limit_control_for_autonomous_vehicles_balancing_performance_and_safety_in_unpredictable_environments]]
- [[llm_and_ai_agents_for_autonomous_systems_a_survey_of_applications_datasets_and_security_challenges]]
- [[learning_humanoid_locomotion_with_perceptive_internal_model]]

## Open Problems

The first baseline from autonomous racing points to high-speed perception, multi-agent planning, adversarial interaction, real-time dynamics modeling, and safety-performance tradeoffs as reusable research problems across highly dynamic autonomy.

The Swift result adds robustness gaps that matter across agile systems: appearance change, crash recovery, opponent-aware strategy, and adaptation beyond a known course.

Ace adds another transfer gap: in real-time human-robot sports, the real objective is match outcome, but training often relies on surrogate shot-level rewards because human opponent behavior is difficult to model in simulation.

GripMap adds a localization of uncertainty problem: the usable dynamic envelope can vary across space, and systems need ways to learn or update those local constraints without becoming too conservative everywhere.

Professional-racer interviews add a learning-speed problem: highly dynamic autonomy still lacks the few-shot adaptability expert humans show when conditions change.

Human-centered safety filtering adds a collaboration problem: an intervention policy can improve safety yet still degrade performance if it feels abrupt, opaque, or controlling to the human operator.

The robotics-survey perspective adds a maturity problem: highly dynamic domains can produce spectacular DRL demonstrations, but the field still lacks consistent standards for when a physical result counts as genuinely robust rather than carefully staged.

SUPER adds a sensing-and-planning coupling problem: high-speed guarantees depend heavily on long-range perception and fast replanning, so safety can collapse quickly if sensing range, map fidelity, or computation margin shrinks.

The ADR survey adds a co-design problem: some of the hardest barriers in highly dynamic systems arise not from any single module, but from how aerodynamic modeling, sensing, state estimation, planning, and control amplify one another’s weaknesses at the edge of performance.

Pursuit-evasion adds an intent-inference problem: a highly dynamic system may need to estimate what another agent is trying to do, not only where that agent is right now.

High-speed quadruped navigation adds an embodiment-coupling problem: if terrain discreteness directly alters what motions remain executable, navigation and control may need to be co-designed more tightly than classical layered robotics pipelines assume.

Rapid quadruped locomotion adds a scaling problem for learned agility: once a policy is fast in one real robot and terrain regime, how far can that competence transfer across bodies, surfaces, and maneuvers before the training structure itself has to change?

Highly dynamic quadruped MPC adds a design-choice problem: when explicit predictive control already achieves strong agility, what additional evidence is needed before replacing that structure with learned control rather than integrating the two?

RMA adds a hidden-state problem: in highly dynamic systems, how much of real competence depends on estimating latent conditions that the robot never observes directly but still must adapt to almost immediately?

Perceptive locomotion adds a sensing-trust problem: when the robot is fast enough that look-ahead terrain information matters, control quality may depend less on raw sensor availability than on whether the system can judge exteroceptive reliability quickly enough to remain stable.

Perceptive NMPC adds a constraint-design problem: in highly dynamic systems, perception is only useful to predictive control if the sensed world can be compressed into constraints the optimizer can solve against before the world changes again.

Humanoid parkour adds a sequencing problem: in highly dynamic systems, strong single skills are not enough if the robot cannot choose and connect them quickly enough to survive the next obstacle.

Real-world humanoid locomotion adds a maturity problem of a different kind: once zero-shot humanoid locomotion is possible, the field needs clearer standards for what counts as real robustness versus carefully curated deployment conditions.

PIM adds a perception-efficiency trade-off: if a humanoid locomotion policy can achieve zero-shot stair climbing by integrating 2.5D height-map queries directly into the state predictor, how should we balance the efficiency of this height-query shortcut against the richer but computationally heavy raw depth maps or point cloud models?

Humanoid parkour learning adds a scope-integration problem: if one policy spans multiple agile maneuvers, how can we tell whether the controller has learned a coherent locomotion skill space rather than a fragile interpolation among tasks?

BeamDojo adds a foothold-resolution problem: once a highly dynamic system depends on landing on a few exact supports, how accurate and trustworthy must the terrain representation be before learned agility stops being a demo and becomes a robust capability?

Hiking in the Wild adds an outdoor-generalization problem: once the terrain is open-ended and messy, how do we know whether a perceptive policy is really robust rather than just broad enough for a curated set of field trials?

HuB adds a stability-margin problem: once a humanoid is asked to hold extreme poses, how should we measure whether its balance skill is truly robust rather than only reference-tracking under carefully prepared conditions?

KungfuBot adds a reference-fidelity problem: once a humanoid is asked to imitate highly dynamic full-body motion, how do we separate failure caused by poor policy learning from failure caused by untrackable or badly retargeted reference motion?

PhysHSI adds a systems-grounding problem: once a humanoid is expected to interact naturally with real scenes, how much of observed competence belongs to the learned controller itself and how much to the surrounding perception, localization, and deployment scaffolding?

Agility Meets Stability adds a regime-coverage problem: once the target controller must be both agile and stable, how do we know whether heterogeneous training truly broadens capability rather than hiding brittle tradeoffs between those operating modes?

SONIC adds a motion-foundation problem: once a humanoid controller is built on a supersized motion-tracking substrate, how do we tell whether the resulting naturalness is robust embodied competence rather than strong interpolation inside a very large behavior prior?

PIE adds an estimation-allocation problem: once a high-dynamic quadruped must rely on noisy egocentric sensing, how much of the needed understanding should live in implicit learned state and how much should remain explicit enough to stabilize transfer?

Extreme Parkour adds a compensation-limit problem: if learning can rescue noisy hardware to a surprising degree, what are the real limits of policy compensation before sensing and actuation quality again become the dominant bottleneck?

DreamControl adds a generative-stability problem: if whole-body scene interaction is driven by guided diffusion, how should the field evaluate whether the resulting behavior is controllably robust rather than merely more natural-looking?

BeyondMimic adds a beyond-tracking problem: if a humanoid controller claims to move past imitation and into versatility, how should the field measure that transition in a way that is more meaningful than simply showing more diverse tracked motions?

Agile soccer learning adds an interaction-dynamics problem: once a fast embodied system must coordinate with a moving task object, agility may depend on perception-action timing that is different from pure locomotion benchmarks.

Robot parkour learning adds a maneuver-selection problem: once a fast embodied system has several available traversal modes, its competence depends not only on executing them well but on selecting the right one early enough.

Agile But Safe adds a regime-switching problem: once a system has both aggressive and recovery modes, how can we tell whether the learned transition logic is robust enough to count as real safety rather than a benchmark-specific convenience?

Barkour adds an evaluation problem: how should highly dynamic fields compare progress when agility is multidimensional and no single course can capture every relevant failure mode?

Animal-gait motion matching adds a motion-selection problem: once a system can choose among several gait patterns, how should we evaluate whether those choices remain robust when the environment or task departs from the motion examples it was built from?

Multi-pursuer aerial pursuit-evasion adds a game-dynamics problem: even if one vehicle is well controlled, success can still fail if the learning process does not capture how several opponents jointly constrain escape geometry.

Neural MPC adds a computation problem: even a principled controller may fail to deliver agile behavior if its optimization latency exceeds the platform's useful reaction window.

Risk-averse racing adds an objective-calibration problem: in highly dynamic systems, being fast enough is not sufficient if the planner quietly assumes away the very rare conditions that cause catastrophic failure.

Learned forward kinodynamics adds a control-abstraction problem: if one wants reusable high-speed control across several objectives, the learned model and the optimizer must generalize together rather than only perform well on one handcrafted task.

Terrain-aware rally control adds a surface-adaptation problem: in highly dynamic systems, the environment can alter the dynamics so quickly that control quality depends on whether terrain effects are modeled where the optimizer can exploit them.

Harmonized beyond-the-limit control adds an architectural problem: if safety and performance are deeply coupled near instability, system designers may need controllers whose objective structure reflects that coupling directly.

The agentic-autonomy survey adds a trust problem: in highly dynamic systems, even capable agent models may be unusable if their security properties, delegation boundaries, and failure modes are too poorly understood.

Hallucinated learning and sober deployment adds a train-deploy asymmetry problem: systems may need one regime to become agile and a different regime to remain safe enough once that agility is exposed to the real world.
