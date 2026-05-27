---
tags: [topic]
date: 2026-05-08
sources: 12
---

# Foundation Models for Intelligent Decision-Making

## Definition

Foundation models for intelligent decision-making are large pretrained multimodal models used to support or structure decision systems that must perceive, reason, plan, and act across varied tasks and environments.

The key promise is broader transfer and adaptivity than narrow task-specific models or rule systems.

## Key Framing

[[foundation_models_and_intelligent_decision_making_progress_challenges_and_perspectives]] describes this area as a progression beyond:

- expert-rule decision systems,
- shallow data-driven decision support,
- and standalone deep-reinforcement-learning pipelines.

In this framing, foundation models do not replace decision-making. They become a new substrate for how decisions can be represented, contextualized, and adapted across tasks.

Within the vault, one useful progression is [[large_language_models]] -> [[vision_language_models]] -> [[vision_language_action_models]], moving from abstract reasoning to multimodal grounding and then to embodied action.

[[human_vs_machine_behavioral_differences_between_expert_humans_and_language_models_in_wargame_simulations]] gives a concrete stress test of that vision in a high-stakes setting: even when LLMs can generate plausible strategic recommendations, their aggression levels, sensitivity to framing, and simulated group dynamics may diverge from expert-human behavior.

[[limits_of_deep_learning_sequence_modeling_through_the_lens_of_complexity_theory]] adds a more structural warning: even if sequence models look broadly capable, [[compositional_reasoning_limits_in_sequence_models]] may prevent them from performing reliable multi-step reasoning on the kinds of chained decision problems many intelligent systems would require.

[[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]] adds a concrete embodied-control example: instead of using a foundation model for abstract decision support, [[racevla]] adapts a [[vision_language_action_models|vision-language-action model]] to produce racing-drone control actions from FPV video and language prompts.

[[real_world_robot_applications_of_foundation_models_a_review]] adds a deployment filter on the whole topic: the real issue is not just whether foundation models can represent decisions broadly, but whether they remain useful once a physical robot imposes sensing noise, timing limits, safety requirements, and action-grounding demands.

[[towards_general_purpose_robots_via_foundation_models_a_survey_and_meta_analysis]] adds a robotics-generality framing: foundation models are not only being proposed as decision substrates, but as a possible route toward more reusable robot competence across embodiments and tasks.

[[foundation_models_in_robotics_applications_challenges_and_the_future]] adds a robotics-applications framing: foundation models may contribute across perception, planning, decision support, and action-related interfaces, but their value depends heavily on how they are embedded in the autonomy stack.

[[llm_and_ai_agents_for_autonomous_systems_a_survey_of_applications_datasets_and_security_challenges]] adds an agent-and-security framing: as LLMs evolve into more agentic autonomy components, the question shifts from usefulness alone to datasets, evaluation, and attack surface in safety-critical autonomous systems.

[[scaling_agent_learning_via_experience_synthesis]] adds a more constructive bridge from foundation models into the experience branch: instead of using generative models only for reasoning or action prediction, it asks whether they can help scale learning itself by synthesizing additional useful experience for agents.

[[exgrpo_learning_to_reason_from_experience]] adds a reasoning-centric version of the same bridge: instead of asking how foundation models reason after pretraining, it asks whether their reasoning behavior can itself be improved through accumulated experience.

[[why_ai_systems_dont_learn_and_what_to_do_about_it_lessons_on_autonomous_learning_from_cognitive_science]] adds a stronger challenge to the branch as a whole: even highly capable systems may still fail at genuine [[autonomous_learning]] if they remain too dependent on static pretraining and insufficiently grounded self-directed learning loops.

[[ai_and_human_co_improvement_for_safer_co_superintelligence]] adds a governance-and-collaboration layer on top of that: even if foundation models become much more capable, the decisive question may be how they co-evolve with human capability rather than how fully they replace it.

[[cognitio_emergens_agency_dimensions_and_dynamics_in_human_ai_knowledge_co_creation]] adds a collaboration-structure layer: even when foundation models are used for reasoning, synthesis, or planning support, the important question may not be model capability alone, but how agency and knowledge production are distributed across the human-AI system.

[[from_seeing_to_experiencing_scaling_navigation_foundation_models_with_reinforcement_learning]] adds an embodied-navigation layer: if foundation models begin as broad visual or representational priors, they may still need reinforcement-learning-based interaction to become strong closed-loop navigation systems.

[[memory_in_the_age_of_ai_agents]] adds a persistence layer underneath the whole branch: even highly capable foundation-model-based agents may remain brittle if they cannot retain, organize, and reuse experience over time.

[[ranked_top_5_techniques_for_fast_and_agile_autonomy]] places this branch in the vault's broader competitive picture: foundation-model approaches are not yet the best current answer for fast and agile autonomy, but they are the strongest long-term bet if `LLM -> VLM -> VLA` systems can eventually close the latency, grounding, and stability gap to specialized controllers.

[[erc_idea]] adds a more skeptical strategic layer: if superhuman autonomy in extreme environments is the goal, foundation models may still matter, but the vault currently suggests they will need to sit inside a more experience-driven, safety-aware, and control-grounded architecture rather than replace that architecture outright.

[[agi_imagined_how_is_agi_configured_by_the_theories_of_mind]] adds a deeper conceptual warning underneath that whole branch: some disagreements about foundation-model futures are really disagreements about what a mind is, and therefore about whether broad pretrained symbolic competence should count as the main path toward AGI at all.

[[human_versus_artificial_intelligence]] adds a more practical comparison layer: even if AI becomes highly capable, the right benchmark may not be human imitation alone. A more useful question may be how human and artificial intelligence differ, where they complement one another, and when hybrid decision systems should preserve human judgment rather than overwrite it.

## Relationship to Embodied and Autonomous Systems

This topic sits naturally near [[cognitive_navigation]], [[embodied_autonomous_intelligence]], [[era_of_experience]], and [[reinforcement_learning]].

For autonomous systems, the interesting question is whether foundation models can provide broader context, world knowledge, and multimodal integration without breaking the latency, reliability, and safety requirements of real-time control.

## Representative Papers

- [[foundation_models_and_intelligent_decision_making_progress_challenges_and_perspectives]]
- [[human_vs_machine_behavioral_differences_between_expert_humans_and_language_models_in_wargame_simulations]]
- [[limits_of_deep_learning_sequence_modeling_through_the_lens_of_complexity_theory]]
- [[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]]
- [[real_world_robot_applications_of_foundation_models_a_review]]
- [[towards_general_purpose_robots_via_foundation_models_a_survey_and_meta_analysis]]
- [[foundation_models_in_robotics_applications_challenges_and_the_future]]
- [[llm_and_ai_agents_for_autonomous_systems_a_survey_of_applications_datasets_and_security_challenges]]
- [[scaling_agent_learning_via_experience_synthesis]]
- [[exgrpo_learning_to_reason_from_experience]]
- [[why_ai_systems_dont_learn_and_what_to_do_about_it_lessons_on_autonomous_learning_from_cognitive_science]]
- [[ai_and_human_co_improvement_for_safer_co_superintelligence]]
- [[cognitio_emergens_agency_dimensions_and_dynamics_in_human_ai_knowledge_co_creation]]
- [[from_seeing_to_experiencing_scaling_navigation_foundation_models_with_reinforcement_learning]]
- [[memory_in_the_age_of_ai_agents]]

## Open Problems

Open problems include grounding decisions in real environments, preserving robustness and safety under distribution shift, making large models efficient enough for deployment, and deciding how foundation-model reasoning should interact with lower-level controllers, planners, and learned policies.

The wargaming evidence adds another problem: foundation models may need much stronger behavioral evaluation before they are allowed to recommend actions in domains where overaggression, false consensus, or brittle framing effects could be catastrophic.

The sequence-limits evidence adds a deeper problem: some failures may not be patched away with better prompting alone if the underlying model architecture remains weak at composition-heavy reasoning.

RaceVLA adds a robotics problem: even if foundation-model-style control works in principle, embodied deployment may still be bottlenecked by inference rate, onboard compute, and the mismatch between pretrained priors and aggressive real-world dynamics.

The real-world robotics review sharpens that problem into a broader systems question: how much of foundation-model usefulness survives contact with physical deployment once latency, embodiment, and safety become non-negotiable?

The general-robots survey adds a complementary ambition question: even if deployment improves, what kind of "generality" is actually being achieved, and how much is still task-conditioned reuse rather than robust open-ended embodied competence?

The robotics-applications survey adds a systems question: even before true generality is reached, which components of robot autonomy benefit most from foundation models, and which remain bottlenecked by data, embodiment, or control precision?

The agentic-autonomy survey adds a security question: even if model capabilities improve, how should autonomous systems benchmark and defend agent-like models whose reasoning, delegation, and tool use may enlarge the system's attack surface?
