---
tags: [topic]
date: 2026-05-13
sources: 3
---

# Real-World Robotic Foundation Models

## Definition

Real-world robotic foundation models are large pretrained multimodal models applied to physical robots in ways that must survive embodiment, sensing noise, latency, safety constraints, and real task execution rather than only simulated or language-only evaluation.

## Key Framing

[[real_world_robot_applications_of_foundation_models_a_review]] frames this area around deployment reality: the interesting question is not whether foundation models are broadly capable, but where they genuinely help robotic systems in the physical world.

This gives the topic a different emphasis from generic foundation-model discussions. In robotics, broad priors are only useful if they remain grounded in sensing, timing, control, and safety.

[[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]] provides one racing-adjacent example: a VLA can in principle absorb more of perception-to-action mapping directly, but real deployment quickly exposes whether latency and action grounding are good enough.

The vault's current structure also suggests a practical stack: [[large_language_models]] for abstract reasoning, [[vision_language_models]] for multimodal grounding, and [[vision_language_action_models]] for the closest current form of foundation-model-based embodied control.

[[towards_general_purpose_robots_via_foundation_models_a_survey_and_meta_analysis]] adds the broader strategic framing: beyond today's deployments, the field is explicitly asking whether foundation models can move robotics toward more general-purpose competence across tasks and embodiments.

[[foundation_models_in_robotics_applications_challenges_and_the_future]] adds the middle-layer survey view: between concrete deployment papers and grand generality arguments, it maps where foundation models are currently being applied across robot autonomy and what obstacles still block reliable embodied use.

## Relationship to Embodied Intelligence and Decision-Making

This topic sits naturally between [[foundation_models_for_intelligent_decision_making]], [[embodied_autonomous_intelligence]], and [[real_world_robotic_reinforcement_learning]].

Compared with broad intelligent-decision reviews, it is much closer to deployment. Compared with RL-centered real-robot work, it asks whether large pretrained multimodal priors can supply useful structure before or alongside task-specific embodied learning.

## Representative Papers

- [[real_world_robot_applications_of_foundation_models_a_review]]
- [[towards_general_purpose_robots_via_foundation_models_a_survey_and_meta_analysis]]
- [[foundation_models_in_robotics_applications_challenges_and_the_future]]
- [[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]]

## Open Problems

Open problems include latency under onboard constraints, action grounding, safety and failure recovery, evaluating generality on physical hardware, and deciding how foundation models should interact with classical control and planning layers instead of trying to replace them wholesale.

The general-robots survey sharpens that last issue: claims of generality are only meaningful if they survive across embodiments, tasks, and system interfaces rather than only across benchmark prompts.

The IJRR survey adds a practical field-mapping issue: robotics may need different evaluation standards for foundation-model usefulness at the levels of perception, planning, manipulation, and action rather than one vague notion of "robot intelligence."
