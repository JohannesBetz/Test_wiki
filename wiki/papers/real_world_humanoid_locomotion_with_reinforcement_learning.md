---
tags: [paper]
date: 2026-05-22
task: robotics
venue: "Science Robotics"
sources: 1
year: "2024"
doi: "10.1126/scirobotics.adi8022"
url: "https://arxiv.org/abs/2303.03381"
topic:
  - Highly_dynamic_autonomous_system
  - embodied_autonomous_intelligence
  - real_world_robotic_reinforcement_learning
tech_backbone: [reinforcement_learning]
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [humanoids]
simulators_used: []
---

# Real-World Humanoid Locomotion with Reinforcement Learning

> Real-World Humanoid Locomotion with Reinforcement Learning | Science Robotics 2024 | Ilija Radosavovic, Tete Xiao, Bike Zhang, Trevor Darrell, Jitendra Malik, and Koushil Sreenath | DOI: 10.1126/scirobotics.adi8022

## Summary

This paper asks whether model-free reinforcement learning can produce robust humanoid locomotion that transfers from simulation to hardware without requiring real-world fine-tuning.

Its answer is yes: sufficiently large-scale and structured simulation training can produce a humanoid locomotion controller that works zero-shot in the real world.

## Method

The paper uses [[reinforcement_learning]] as the main training backbone, with large-scale randomized simulation used to expose the policy to broad dynamics and environment variation before deployment.

For this vault, the important point is that the contribution is systems-level rather than a narrow new policy formula. The main claim is that real-world humanoid locomotion can emerge from scale, randomization, and disciplined sim-to-real design.

## Key Results

The paper reports zero-shot transfer of humanoid locomotion from simulation to the real world.

The most useful vault takeaway is broader than one robot:

**real-world RL success is no longer confined to drones and quadrupeds; humanoids have entered that evidence base too.**

## Hardware Used

- [[humanoids]]

## Related Work

This paper belongs directly near [[real_world_robotic_reinforcement_learning]], where it strengthens the case that legged real-world RL now spans more than one embodiment class.

Compared with [[rapid_locomotion_via_reinforcement_learning]], it gives the humanoid analogue of the same broad story: structured simulation plus RL can produce physically serious dynamic locomotion.

Compared with [[attention_based_map_encoding_for_learning_generalized_legged_locomotion]], it appears less focused on sophisticated perceptive representations and more focused on proving that the sim-to-real RL recipe itself scales to humanoid walking.

It also belongs near [[embodied_autonomous_intelligence]], because humanoid locomotion is an especially demanding test of whether learned control can survive the tight coupling of balance, contact, and body geometry in the real world.

## Notes / Critique

The strongest contribution is that it makes the humanoid branch empirically real. It moves the discussion from “humanoids might eventually learn this” toward “here is a concrete real-world RL result.”

The main caveat is scope: robust locomotion is not yet the same thing as full humanoid autonomy over rich terrain, long-horizon tasks, manipulation, or dynamic skill chaining. Still, as a real-world RL anchor, it is an important one.
