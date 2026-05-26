---
tags: [paper]
date: 2026-05-22
task: robotics
venue: "Robotics: Science and Systems (RSS) 2021"
sources: 1
year: "2021"
doi: "10.48550/arXiv.2107.04034"
url: "https://doi.org/10.48550/arXiv.2107.04034"
topic:
  - Highly_dynamic_autonomous_system
  - real_world_robotic_reinforcement_learning
  - quadrupedal_locomotion
tech_backbone: [reinforcement_learning]
tech_representation: [rapid_motor_adaptation, sim_to_real_transfer]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [quadrupeds]
simulators_used: []
---

# RMA: Rapid Motor Adaptation for Legged Robots

> RMA: Rapid Motor Adaptation for Legged Robots | Robotics: Science and Systems (RSS) 2021 | Ashish Kumar, Zipeng Fu, Deepak Pathak, and Jitendra Malik | DOI: 10.48550/arXiv.2107.04034

## Summary

This paper asks how a legged robot can stay competent when the terrain or effective dynamics change faster than a fixed locomotion policy can tolerate.

Its answer is `RMA`, a learned locomotion architecture that separates a base policy from an online adaptation module so the controller can infer latent terrain and dynamics conditions on the fly.

## Method

The central idea is [[rapid_motor_adaptation]].

The architecture contains:

- a base policy for locomotion control,
- and an adaptation module that predicts a latent variable from recent state-action history.

That latent represents hidden factors the controller needs but does not observe directly, such as terrain condition, payload shifts, or other changes in effective system dynamics.

The result is a policy that can adapt rapidly without requiring explicit terrain labels or hand-designed regime switches.

The paper is trained fully in simulation and deployed on the physical Unitree A1 quadruped without real-world fine-tuning, which makes it a strong example of structured [[sim_to_real_transfer]].

## Key Results

The paper reports successful adaptation to a variety of unseen real-world conditions including rocky, slippery, deformable, and stair-like terrain.

For this vault, the key result is broader than locomotion robustness alone:

**fast quadruped locomotion can include a learned online adaptation loop rather than only a fixed policy or a fixed controller.**

## Hardware Used

- [[quadrupeds]]

## Related Work

This paper belongs directly near [[quadrupedal_locomotion]], where it provides an adaptation-centric complement to the current quadruped entries.

Compared with [[rapid_locomotion_via_reinforcement_learning]], this paper is less about pushing one fast locomotion policy to high speed and more about making the policy adapt online when the world shifts.

Compared with [[highly_dynamic_quadruped_locomotion_via_whole_body_impulse_control_and_model_predictive_control]], it represents a much more learning-heavy answer to the same broad problem of dynamic legged competence.

It also belongs near [[real_world_robotic_reinforcement_learning]], because it is one of the clearest physical-RL examples where strong performance depends on more than an RL objective alone. The adaptation architecture is part of the main contribution.

## Notes / Critique

The strongest contribution is the decomposition. Instead of forcing one policy to absorb every condition implicitly, the paper explicitly reserves capacity for latent online adaptation.

That makes it a strong piece of evidence for a broader vault thesis:

**high-performance embodied intelligence may depend not only on learning a good controller, but on learning how to infer hidden changes in the world quickly enough to stay effective.**
