---
tags: [technique]
date: 2026-05-27
sources: 1
---

# Experience Synthesis

## Definition

Experience Synthesis is an agent-learning technique in which additional useful training experience is generated, recomposed, or otherwise synthesized from already available grounded interaction rather than collected only through fresh online rollouts.

The goal is to make experience-driven learning scale faster than raw environment interaction alone would allow.

## Key Approach

[[scaling_agent_learning_via_experience_synthesis]] is the current anchor paper in the vault for this idea.

The key move is simple but important:

- direct interaction remains the grounding source,
- synthesized experience acts as a multiplier on that source,
- and learning can in principle progress faster than the rate at which risky or expensive real interaction is gathered.

This makes the technique especially attractive for agentic and embodied systems where real interaction is limited by safety, cost, latency, or deployment friction.

## Relationship to Autonomous Systems

This technique sits naturally between [[era_of_experience]], [[foundation_models_for_intelligent_decision_making]], and [[ai_agents_for_autonomous_systems]].

For autonomous systems, the appeal is obvious: robots, drones, and vehicles often cannot explore freely in the real world. Experience synthesis suggests a way to stretch scarce grounded experience into broader policy improvement.

Compared with pure offline learning from human data, it stays closer to the experience-centered agenda.

Compared with pure online learning, it tries to reduce the dependence on expensive new interaction.

## Representative Papers

- [[scaling_agent_learning_via_experience_synthesis]]

## Open Problems

Open problems include:

- how to verify that synthesized experience remains causally faithful,
- how much synthetic augmentation can be tolerated before learning drifts away from reality,
- whether the technique helps only language-like agents or also transfers to embodied control,
- and how to keep the synthesis process safe when agents are already strategic, deceptive, or poorly calibrated.
