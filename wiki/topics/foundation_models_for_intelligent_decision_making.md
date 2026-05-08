---
tags: [topic]
date: 2026-05-08
sources: 1
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

[[human_vs_machine_behavioral_differences_between_expert_humans_and_language_models_in_wargame_simulations]] gives a concrete stress test of that vision in a high-stakes setting: even when LLMs can generate plausible strategic recommendations, their aggression levels, sensitivity to framing, and simulated group dynamics may diverge from expert-human behavior.

[[limits_of_deep_learning_sequence_modeling_through_the_lens_of_complexity_theory]] adds a more structural warning: even if sequence models look broadly capable, [[compositional_reasoning_limits_in_sequence_models]] may prevent them from performing reliable multi-step reasoning on the kinds of chained decision problems many intelligent systems would require.

[[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]] adds a concrete embodied-control example: instead of using a foundation model for abstract decision support, [[racevla]] adapts a [[vision_language_action_models|vision-language-action model]] to produce racing-drone control actions from FPV video and language prompts.

## Relationship to Embodied and Autonomous Systems

This topic sits naturally near [[cognitive_navigation]], [[embodied_autonomous_intelligence]], [[era_of_experience]], and [[reinforcement_learning]].

For autonomous systems, the interesting question is whether foundation models can provide broader context, world knowledge, and multimodal integration without breaking the latency, reliability, and safety requirements of real-time control.

## Representative Papers

- [[foundation_models_and_intelligent_decision_making_progress_challenges_and_perspectives]]
- [[human_vs_machine_behavioral_differences_between_expert_humans_and_language_models_in_wargame_simulations]]
- [[limits_of_deep_learning_sequence_modeling_through_the_lens_of_complexity_theory]]
- [[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]]

## Open Problems

Open problems include grounding decisions in real environments, preserving robustness and safety under distribution shift, making large models efficient enough for deployment, and deciding how foundation-model reasoning should interact with lower-level controllers, planners, and learned policies.

The wargaming evidence adds another problem: foundation models may need much stronger behavioral evaluation before they are allowed to recommend actions in domains where overaggression, false consensus, or brittle framing effects could be catastrophic.

The sequence-limits evidence adds a deeper problem: some failures may not be patched away with better prompting alone if the underlying model architecture remains weak at composition-heavy reasoning.

RaceVLA adds a robotics problem: even if foundation-model-style control works in principle, embodied deployment may still be bottlenecked by inference rate, onboard compute, and the mismatch between pretrained priors and aggressive real-world dynamics.
