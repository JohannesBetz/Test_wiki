---
tags: [topic]
date: 2026-05-13
sources: 2
---

# AI Agents for Autonomous Systems

## Definition

AI agents for autonomous systems are agentic AI components, often built on large language or multimodal foundation models, that are intended to support, coordinate, or partially automate decision-making inside autonomous systems.

## Key Framing

[[llm_and_ai_agents_for_autonomous_systems_a_survey_of_applications_datasets_and_security_challenges]] frames this area through applications, datasets, and security challenges.

That gives the topic a distinct role in the vault. It is not only about whether foundation models can perceive or reason, but whether agent-like systems can be trusted with meaningful autonomy-facing decision loops.

The topic also sits naturally next to the existing `LLM -> VLM -> VLA` progression:

- [[large_language_models]] for high-level reasoning,
- [[vision_language_models]] for multimodal grounding,
- [[vision_language_action_models]] for embodied action,
- and agentic systems as the orchestration layer that may decide how these components are used.

[[human_versus_artificial_intelligence]] adds a useful caution underneath this progression: the more agentic AI becomes, the more important it is that humans understand where AI cognition differs from human cognition rather than assuming the system reasons like a human teammate.

[[scaling_agent_learning_via_experience_synthesis]] adds a more optimistic systems question to the same branch: if agents are costly to train through direct interaction alone, can generative or synthetic experience become part of how agent competence scales?

## Relationship to Intelligent Decision-Making and High-Dynamics Autonomy

This topic belongs near [[foundation_models_for_intelligent_decision_making]] and [[Highly_dynamic_autonomous_system]].

For high-speed or safety-critical autonomy, the central question is whether agentic flexibility increases capability faster than it increases unpredictability and attack surface.

## Representative Papers

- [[llm_and_ai_agents_for_autonomous_systems_a_survey_of_applications_datasets_and_security_challenges]]
- [[human_vs_machine_behavioral_differences_between_expert_humans_and_language_models_in_wargame_simulations]]
- [[scaling_agent_learning_via_experience_synthesis]]

## Open Problems

Open problems include benchmark realism, security vulnerabilities, prompt and policy brittleness, safe delegation boundaries, human oversight, and deciding how much authority agentic models should have in autonomy stacks with real physical consequences.
