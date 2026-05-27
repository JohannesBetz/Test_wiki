---
tags: [topic]
date: 2026-05-22
sources: 2
---

# Quadrupedal Locomotion

## Definition

Quadrupedal locomotion studies how four-legged robots move robustly, efficiently, and increasingly quickly across real environments.

In this vault, the topic matters less as a standalone biomechanics problem and more as an embodied-autonomy testbed where perception, terrain understanding, navigation, and dynamic control meet under physical consequence.

## Key Framing

[[high_speed_control_and_navigation_for_quadrupedal_robots_on_complex_and_discrete_terrain]] gives this topic a strongly high-dynamic framing: once the terrain is complex and discrete, locomotion is no longer only about repeating stable gaits, but about coupling fast control and navigation tightly enough to stay decisive without becoming reckless.

[[learning_vision_based_pursuit_evasion_robot_policies]] adds an interaction-centric framing: a quadruped can also be a strategic embodied agent operating under partial observability rather than just a terrain-following machine.

[[rapid_locomotion_via_reinforcement_learning]] adds a fast-learning framing: quadruped locomotion is also one of the clearest cases where structured [[reinforcement_learning]] has already produced physically serious high-speed behavior in the wild.

[[highly_dynamic_quadruped_locomotion_via_whole_body_impulse_control_and_model_predictive_control]] adds a control-architecture framing: highly dynamic quadruped behavior can also emerge from explicit predictive force planning coupled to whole-body impulse control rather than from RL alone.

[[rma_rapid_motor_adaptation_for_legged_robots]] adds an adaptation-centric framing: high-performance locomotion may depend not only on fast policies, but on learning latent online adaptation to hidden terrain and dynamics changes.

[[hybrid_internal_model_learning_agile_legged_locomotion_with_simulated_robot_response]] adds an internal-response framing: robust agile locomotion may also depend on learning a better internal representation of how the robot responds to disturbance, rather than only on richer terrain perception or explicit adaptation modules.

[[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]] adds a perception-centric framing: high-speed legged competence may depend on using terrain information before contact, but only if the controller learns to survive noisy and misleading exteroception instead of assuming perception is always right.

[[legged_locomotion_in_challenging_terrains_using_egocentric_vision]] adds an egocentric-vision framing: terrain-aware locomotion can also emerge from a more compact vision-first policy without requiring the same degree of explicit terrain-map structure seen in other perceptive-control papers.

[[perceptive_locomotion_through_nonlinear_model_predictive_control]] adds a model-based perceptive framing: terrain perception can also enter a quadruped stack as optimization constraints inside online NMPC rather than only as features consumed by a learned policy.

[[attention_based_map_encoding_for_learning_generalized_legged_locomotion]] adds a generalized perceptive framing: selective terrain attention may be one of the ingredients that lets learned locomotion scale beyond one robot body and one terrain style.

[[robot_parkour_learning]] adds a parkour framing: quadrupedal locomotion can also be treated as one perceptive multi-skill obstacle-traversal problem rather than only as running, stepping, or local terrain adaptation.

[[agile_but_safe_learning_collision_free_high_speed_legged_locomotion]] adds a safety-architecture framing: fast learned quadruped locomotion may need an explicit learned switch between aggressive motion and recovery behavior rather than only one uniformly competent policy.

[[barkour_benchmarking_animal_level_agility_with_quadruped_robots]] adds a benchmark framing: quadruped locomotion research also needs shared obstacle-course evaluation targets, not only stronger controllers.

[[learning_robust_and_agile_legged_locomotion_using_adversarial_motion_priors]] adds a motion-prior framing: legged agility can also be improved by learning a stronger prior over coordinated motion rather than relying only on task rewards or explicit control structure.

[[animal_gaits_on_quadrupedal_robots_using_motion_matching_and_model_based_control]] adds a motion-library framing: quadruped gait diversity can also be organized through animal-motion retrieval and model-based tracking rather than only through explicit controller design or end-to-end learning.

[[learning_visual_parkour_from_generated_images]] adds a generated-visual parkour framing: quadruped agility can also depend on whether the training images themselves are realistic and diverse enough for RGB-only parkour transfer.

[[parc_physics_based_augmentation_with_reinforcement_learning_for_character_controllers]] adds a capability-expansion framing: agile traversal can also depend on how the motion dataset itself is iteratively expanded through physics-based augmentation rather than only on the final controller.

[[pie_parkour_with_implicit_explicit_learning_framework_for_legged_robots]] adds an implicit-explicit parkour framing: agile quadruped traversal can also depend on how the controller splits terrain and state understanding between latent inference and explicit estimation under noisy onboard sensing.

[[extreme_parkour_with_legged_robots]] adds a low-cost extreme-parkour framing: agile quadruped traversal can also emerge from end-to-end learning on imprecise hardware, which shifts part of the field’s attention from premium embodiment toward policy robustness under noisy real sensing and actuation.

[[deep_reinforcement_learning_for_robotics_a_survey_of_real_world_successes]] provides the broader maturity context. It treats quadruped locomotion as one of the notable real-world success areas in embodied robotics, which makes the domain useful as evidence that some forms of learned physical competence are already real rather than speculative.

## Relationship to Highly Dynamic and Embodied Autonomy

This topic belongs naturally near [[Highly_dynamic_autonomous_system]], [[embodied_autonomous_intelligence]], and [[real_world_robotic_reinforcement_learning]].

The central reason is simple: quadrupeds expose the same deeper question seen elsewhere in the vault.

**How does an embodied system move fast enough to be useful without losing the tight coupling between environment constraints, internal dynamics, and action timing?**

In that sense, quadrupedal locomotion is not separate from the vault's main themes. It is another body form through which the same extreme-autonomy questions become visible.

For a recent robot-focused synthesis of those questions, see [[main_concepts_for_agile_high_speed_robot_behavior]].

## Representative Papers

- [[high_speed_control_and_navigation_for_quadrupedal_robots_on_complex_and_discrete_terrain]]
- [[rapid_locomotion_via_reinforcement_learning]]
- [[highly_dynamic_quadruped_locomotion_via_whole_body_impulse_control_and_model_predictive_control]]
- [[rma_rapid_motor_adaptation_for_legged_robots]]
- [[hybrid_internal_model_learning_agile_legged_locomotion_with_simulated_robot_response]]
- [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]]
- [[legged_locomotion_in_challenging_terrains_using_egocentric_vision]]
- [[perceptive_locomotion_through_nonlinear_model_predictive_control]]
- [[attention_based_map_encoding_for_learning_generalized_legged_locomotion]]
- [[robot_parkour_learning]]
- [[agile_but_safe_learning_collision_free_high_speed_legged_locomotion]]
- [[barkour_benchmarking_animal_level_agility_with_quadruped_robots]]
- [[learning_robust_and_agile_legged_locomotion_using_adversarial_motion_priors]]
- [[animal_gaits_on_quadrupedal_robots_using_motion_matching_and_model_based_control]]
- [[learning_visual_parkour_from_generated_images]]
- [[parc_physics_based_augmentation_with_reinforcement_learning_for_character_controllers]]
- [[pie_parkour_with_implicit_explicit_learning_framework_for_legged_robots]]
- [[extreme_parkour_with_legged_robots]]
- [[learning_vision_based_pursuit_evasion_robot_policies]]
- [[deep_reinforcement_learning_for_robotics_a_survey_of_real_world_successes]]

## Open Problems

Open problems include how to maintain high speed on discontinuous terrain, how to couple perception and foothold-relevant navigation tightly enough for real deployment, how to preserve robustness when terrain changes abruptly, and how to transfer locomotion competence across robot bodies and environments without brittle retuning.

The high-speed quadruped paper adds a sharper systems question: when terrain feasibility and control feasibility are deeply entangled, where should the abstraction boundary between navigation and locomotion actually live?

The rapid-locomotion paper adds a learning-structure question: how much of fast legged competence comes from more experience, and how much comes from designing the right curriculum, command distribution, and sim-to-real update loop?

The highly dynamic locomotion paper adds a control-decomposition question: when aggressive quadruped motion depends heavily on contact-force realization, how much of the problem should be solved by explicit predictive control and how much by learned policies?

RMA adds an adaptation question: if a fast legged robot can infer hidden terrain and dynamics shifts online, what other autonomy stacks in the vault should be redesigned around latent adaptation rather than static policy execution?

Hybrid Internal Model adds a response-modeling question: how much of robust legged competence can be recovered from the body's own response history before the system truly needs richer exteroceptive terrain understanding?

Perceptive locomotion adds a trust question: when a fast quadruped sees the terrain ahead, how should the control stack decide whether the map is informative, misleading, or incomplete before that judgment itself becomes the source of failure?

Egocentric-vision locomotion adds a representation question: when terrain understanding is compressed into a compact onboard visual policy, what evidence shows the robot has learned transferable terrain structure rather than one narrow visual shortcut?

Perceptive NMPC adds a controller-design question: when terrain perception is embedded into online optimization, what is the right abstraction level between raw geometry and tractable real-time constraints?

Attention-based terrain encoding adds a generalization question: when a learned locomotion policy seems broadly capable, how much of that breadth comes from the attention mechanism itself versus the training distribution, embodiment choice, and map preprocessing pipeline?

Robot parkour learning adds a repertoire question: when one quadruped policy spans many obstacle-crossing maneuvers, how do we tell whether it has learned a coherent parkour skill space rather than a brittle collection of special cases?

Agile But Safe adds a policy-switching question: when one controller is optimized for aggression and another for recovery, what evidence shows the learned handoff is robust rather than itself becoming the failure point?

Barkour adds a benchmark-design question: when agility is compressed into one obstacle course and one score, which important forms of embodied competence are still left out?

Adversarial motion priors add a prior-design question: when locomotion quality is learned as a prior, how do we tell whether the prior is genuinely broadening robustness or simply biasing the robot toward one narrow style of motion?

Animal-gait motion matching adds a retrieval-design question: when gait diversity is organized through a motion library, what kinds of locomotion novelty remain impossible because they are absent from the library itself?

Generated-image visual parkour adds a world-generation question: when the robot learns from synthetic RGB scenes, what parts of locomotion success come from better policies and what parts come from better training worlds?

PARC adds a data-growth question: if agile competence depends on expanding the motion dataset itself, what guarantees do we have that the augmented motions stay useful rather than drifting into artifacts of the simulator?

PIE adds an estimation-split question: if a parkour controller mixes implicit and explicit estimation, how do we know whether the split is genuinely robust and not just well matched to one sensor configuration and obstacle distribution?

Extreme Parkour adds a hardware-minimalism question: if extreme agility is possible on a cheap, noisy robot, where is the real lower bound on hardware quality before parkour competence collapses?
