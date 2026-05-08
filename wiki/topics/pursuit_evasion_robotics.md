---
tags: [topic]
date: 2026-05-08
sources: 1
---

# Pursuit-Evasion Robotics

## Definition

Pursuit-evasion robotics studies interactive robot behavior where one agent must detect, track, predict, and intercept another agent that is actively trying to avoid capture.

The problem sits between control, perception, game-like decision making, and embodied uncertainty management.

## Key Framing

[[learning_vision_based_pursuit_evasion_robot_policies]] frames pursuit-evasion as a partially observable embodied interaction problem. The pursuer must reason not only about physical motion, but also about hidden intent and future behavior of the evader.

In that paper, a fully observable teacher policy supervises a partially observable visual policy deployed on a quadruped robot. The result is a useful example of how strategic robot behavior can be learned without assuming full state access at deployment time.

[[learning_multipursuit_evasion_for_safe_targeted_navigation_of_drones]] extends the topic into aerial multi-agent interaction: [[asynchronous_multistage_deep_reinforcement_learning]] trains one evader drone against multiple pursuers so the evader can still reach a target under adversarial pressure.

This makes pursuit-evasion robotics a good adjacent topic for this vault: it is not autonomous racing, but it shares many pressures around reaction time, uncertainty, embodied execution, and multi-agent interaction.

## Relationship to Embodied Autonomy and RL

This topic belongs near [[reinforcement_learning]], [[real_world_robotic_reinforcement_learning]], [[Highly_dynamic_autonomous_system]], and [[embodied_autonomous_intelligence]].

Its central tension is similar to racing and other agile robotics domains: the robot must move decisively in real time while sensing is incomplete and the environment includes another adaptive agent.

## Representative Papers

- [[learning_vision_based_pursuit_evasion_robot_policies]]
- [[learning_multipursuit_evasion_for_safe_targeted_navigation_of_drones]]

## Open Problems

Open problems include scaling to faster interactions, handling richer adversarial behavior, learning under tighter sensing and latency constraints, and transferring pursuit-evasion behavior across robot bodies and environments without brittle retuning.

The multi-pursuer drone setting adds another challenge: as the number of adversaries grows, the policy must handle both nonstationary opponent behavior and increasingly geometry-dependent escape dynamics.
