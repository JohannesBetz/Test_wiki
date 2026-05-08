---
tags: [paper]
date: 2026-05-08
task: robotics
venue: "ICRA"
sources: 1
year: "2024"
doi: "10.1109/ICRA57147.2024.10610498"
topic:
  - Highly_dynamic_autonomous_system
  - embodied_autonomous_intelligence
  - pursuit_evasion_robotics
tech_backbone: [reinforcement_learning]
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
simulators_used: []
---

# Learning Vision-based Pursuit-Evasion Robot Policies

> Learning Vision-based Pursuit-Evasion Robot Policies | ICRA 2024 | Andrea Bajcsy, Antonio Loquercio, Ashish Kumar, and Jitendra Malik

## Summary

This paper asks how a robot can learn strategic pursuit behavior from vision when the evader's motion and intent are only partially observable. The key challenge is that pursuit-evasion is not just low-level control; it is an interactive decision problem where the pursuer must infer, anticipate, and intercept.

The paper's answer is to learn a visual policy that can operate under sensing constraints while borrowing supervision from a more informed fully observable policy.

## Method

The authors reformulate the interactive learning problem into a teacher-student setup.

- A fully observable pursuer policy has access to stronger state information and generates supervision.
- A partially observable visual pursuer learns from that supervision.
- The deployed robot uses RGB-D sensing and must act from realistic onboard observations.

The paper highlights two important design variables:

- the tradeoff between diversity and optimality in the evader behavior used for supervision,
- and the strength of the modeling assumptions baked into the teacher policy.

This is interesting because it does not treat partial observability only as a nuisance. Instead, it studies how strategic behavior can still emerge when the learner must gather information, predict intent, and intercept from incomplete visual evidence.

## Key Results

The policy is deployed on a physical quadruped robot in outdoor or unstructured pursuit-evasion interactions. The headline qualitative result is that the learned robot exhibits nontrivial strategic behaviors: it slows down to reduce uncertainty, accelerates when detection improves, and attempts anticipatory interception rather than only greedy chasing.

For this vault, the most important result is not a single benchmark number but the demonstration that physically deployed vision-based policies can produce useful multi-agent behavior under partial observability.

## Related Work

This paper belongs naturally near [[real_world_robotic_reinforcement_learning]], because it is a physical deployment result rather than only a simulator study.

It also connects to [[Highly_dynamic_autonomous_system]] and [[embodied_autonomous_intelligence]], since the pursuer's competence depends on coupling sensing, motion, and strategic action tightly enough to work in the wild.

Compared with racing papers such as [[champion_level_drone_racing_using_deep_reinforcement_learning]], the interaction is slower and the task is different, but the shared issue is familiar: learned policies become most interesting when they must act through partial observations on real hardware rather than from privileged simulator state.

## Notes / Critique

The best part of the paper is the supervision structure. Using a stronger fully observable policy to train a weaker but deployable visual policy is a clean way to tame a hard interactive learning problem.

The main limitation is transfer breadth. The paper shows one compelling strategic interaction setting, but it remains an open question how well the same approach scales to faster, denser, or more adversarial embodied domains.
