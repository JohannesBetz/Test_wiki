---
tags: [paper]
date: 2026-05-08
task: robotics
venue: "IEEE Transactions on Artificial Intelligence"
sources: 1
year: "2024"
doi: "10.1109/TAI.2024.3366871"
topic:
  - pursuit_evasion_robotics
  - Highly_dynamic_autonomous_system
  - real_world_robotic_reinforcement_learning
tech_backbone: [reinforcement_learning]
tech_representation: [asynchronous_multistage_deep_reinforcement_learning]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [drones]
simulators_used: []
---

# Learning Multipursuit Evasion for Safe Targeted Navigation of Drones

> Learning Multipursuit Evasion for Safe Targeted Navigation of Drones | IEEE Transactions on Artificial Intelligence 2024 | Jiaping Xiao and Mir Feroskhan

## Summary

This paper tackles a multi-agent drone-navigation problem where one drone must reach a target while avoiding physical interception by multiple pursuer drones. The challenge is not only motion planning, but adversarial adaptation: the evader must learn how pursuers behave and respond quickly enough to stay safe.

The paper frames this as a pursuit-evasion game and proposes a multi-stage deep-RL method to train both sides without collapsing into unstable co-adaptation.

## Method

The main method is [[asynchronous_multistage_deep_reinforcement_learning]] (`AMS-DRL`).

The setup includes:

- one evader drone trying to reach a target region safely,
- multiple pursuer drones trying to intercept it,
- and multi-stage asynchronous training of adversarial policies.

Instead of training all agents simultaneously in one undifferentiated loop, the method trains one team against a fixed policy snapshot of the other team from the previous stage. This staged bipartite training is intended to produce more stable capability growth and a better approximation to Nash equilibrium behavior.

The paper also studies how factors such as relative maximum speed and spatial geometry change success rates, which is important because multi-agent flight competence is tightly bound to embodiment rather than only to abstract game policy quality.

## Key Results

The paper reports higher navigation success rates than baseline methods in extensive simulations of multi-pursuer drone pursuit-evasion.

It also adds two practically useful analyses:

- a study of how relative speed changes navigation performance,
- and a success-rate heatmap that shows how geometry affects the evader's chances.

Most importantly for this vault, the authors also validate the learned policies in physical drone experiments with real-time flight. That moves the work beyond a pure game-theory or simulator result.

## Hardware Used

- [[drones]]


## Related Work

This paper belongs most directly near [[pursuit_evasion_robotics]], since it extends pursuit-evasion from a ground-robot setting into multi-drone adversarial navigation.

It also connects to [[real_world_robotic_reinforcement_learning]] because the policy is tested in physical experiments, and to [[Highly_dynamic_autonomous_system]] because the agents must react under tight timing and motion constraints.

Compared with [[learning_vision_based_pursuit_evasion_robot_policies]], this paper is less about partial visual observability and more about multi-agent adversarial evolution for aerial interception and escape.

Compared with [[champion_level_drone_racing_using_deep_reinforcement_learning]] and [[safety_assured_high_speed_navigation_for_mavs]], it is less about absolute speed and more about safe targeted navigation under adversarial interaction.

## Notes / Critique

The strongest part of the paper is the training structure. Multi-agent RL often suffers from instability and opponent overfitting, so the staged asynchronous setup is a reasonable and concrete answer to that problem.

The main caveat is environmental richness. Even with physical validation, the task still abstracts away many of the sensing and world-complexity issues that dominate open-world autonomous flight. So it is best read as a strong controlled study of adversarial drone navigation rather than a full general solution to safe multi-drone autonomy.
