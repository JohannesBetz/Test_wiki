---
tags: [source]
date: 2026-05-08
sources: 1
---

# Wang Learning Motion Planning and Control Survey Source

> Source: `raw/pdfs/Wang_A_Survey_on_Learning_Motion_Planning_and_Control_for_Mobile_Robots_Toward_Embodied_Intelligence.pdf`
> Paper: A Survey on Learning Motion Planning and Control for Mobile Robots: Toward Embodied Intelligence, IEEE Transactions on Neural Networks and Learning Systems 2026

## Summary

This paper surveys learning-based motion planning and control for mobile robots through the lens of embodied intelligence. Rather than treating planning and control as isolated downstream modules, it frames them as core parts of an embodied agent that must perceive, decide, and act under real-world uncertainty.

For this vault, the paper is useful as a bridge between the conceptual framing of [[cognitive_navigation]] and the more algorithmic framing of [[reinforcement_learning]] and robot-learning surveys.

## Method / Framing

The survey organizes the space around learning approaches to motion planning and control for mobile robots, with particular emphasis on methods such as:

- [[reinforcement_learning]],
- imitation learning,
- and other learning-based action-generation strategies for navigation and control.

Its broader argument is that planning and control should be studied as parts of embodied intelligence, not only as optimization problems detached from sensing, environment interaction, and task context.

## Relevance

For this vault, the main value is synthesis. The paper gives a mobile-robot-centered overview of how learned planning and control methods are evolving, and it helps connect broad embodied-AI language to concrete navigation and control pipelines.

That makes it especially relevant near [[cognitive_navigation]], [[embodied_autonomous_intelligence]], and [[real_world_robotic_reinforcement_learning]].

## Notes / Critique

The paper's strength is scope with a practical center of gravity. It is broader than a single-domain survey but still focused enough to say something concrete about learning-based motion generation for mobile robots.

Its limitation for this vault is that it remains general-purpose. It is a strong framing document for autonomy and robot learning, but it does not directly resolve the near-limit timing, interaction, and dynamics questions that dominate autonomous racing.

## Pages Created From This Source

- [[a_survey_on_learning_motion_planning_and_control_for_mobile_robots_toward_embodied_intelligence]]
