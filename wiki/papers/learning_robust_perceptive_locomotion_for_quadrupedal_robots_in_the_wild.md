---
tags: [paper]
date: 2026-05-22
task: robotics
venue: "Science Robotics"
sources: 1
year: "2022"
doi: "10.1126/scirobotics.abk2822"
url: "https://doi.org/10.1126/scirobotics.abk2822"
topic:
  - Highly_dynamic_autonomous_system
  - high_speed_perception
  - real_world_robotic_reinforcement_learning
  - quadrupedal_locomotion
tech_backbone: [reinforcement_learning]
tech_representation: [perceptive_locomotion, sim_to_real_transfer]
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

# Learning robust perceptive locomotion for quadrupedal robots in the wild

> Learning robust perceptive locomotion for quadrupedal robots in the wild | Science Robotics 2022 | Takahiro Miki, Joonho Lee, Jemin Hwangbo, Lorenz Wellhausen, Vladlen Koltun, and Marco Hutter | DOI: 10.1126/scirobotics.abk2822

## Summary

This paper asks whether exteroceptive perception can be used robustly enough for fast legged locomotion in the wild, rather than being abandoned in favor of purely proprioceptive controllers whenever sensing becomes unreliable.

Its answer is yes: perception can help a quadruped move faster and more robustly, but only if the policy learns how to fuse noisy terrain observations with proprioceptive state instead of trusting the map naively.

## Method

The central idea is [[perceptive_locomotion]].

The controller uses height samples from a robot-centric elevation map together with proprioceptive state, and fuses them through an attention-based recurrent encoder.

The training pipeline matters just as much as the network structure:

- a privileged teacher policy is learned in simulation with [[reinforcement_learning]],
- then a student policy is trained to imitate the teacher and reconstruct useful environment state from noisy deployment-like observations,
- and the student is deployed zero-shot on hardware.

For this vault, the important systems lesson is that perception enters locomotion as a control-relevant latent representation, not just as a standalone mapping module.

## Key Results

The paper reports robust high-speed and long-duration locomotion on real ANYmal quadrupeds across challenging natural and urban environments, including stairs, vegetation, slippery terrain, degraded sensing, and long outdoor routes.

One especially useful vault takeaway is broader than any single benchmark:

**high-performance quadruped locomotion can improve when the robot learns to use imperfect perception before contact rather than waiting to discover terrain structure only through impact and proprioceptive error.**

## Hardware Used

- [[quadrupeds]]

## Related Work

This paper belongs directly near [[quadrupedal_locomotion]], where it adds a perception-centric complement to the current quadruped branch.

Compared with [[rapid_locomotion_via_reinforcement_learning]], this paper is less about maximizing one rapid learned gait and more about making locomotion robust when terrain must be perceived before contact.

Compared with [[rma_rapid_motor_adaptation_for_legged_robots]], it solves a different hidden-state problem: RMA infers latent dynamics from recent experience, while this paper tries to make noisy exteroceptive input useful enough to shape behavior ahead of time.

It also belongs near [[high_speed_perception]], because it shows that high-speed perception is not only about racing cars, drones, or fast ball tracking. In legged robotics, perception quality directly changes what motions remain executable.

## Notes / Critique

The strongest contribution is the refusal to choose between perception and robustness. Instead of assuming that exteroception is too brittle for real deployment, the paper learns a controller that can exploit perception when it helps and remain stable when it degrades.

The main caveat is embodiment specificity. ANYmal on rough terrain is a very strong testbed, but it still leaves open how far this exact fusion strategy transfers across robot bodies, sensing stacks, and terrains with very different geometry or failure modes.
