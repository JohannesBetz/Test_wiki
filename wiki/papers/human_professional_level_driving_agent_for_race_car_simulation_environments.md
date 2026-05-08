---
tags: [paper]
date: 2026-05-08
task: autonomous_racing
venue: "AI Open"
sources: 1
year: "2026"
doi: "10.1016/j.aiopen.2026.02.007"
url: "https://doi.org/10.1016/j.aiopen.2026.02.007"
topic:
  - autonomous_racing
  - autonomous_racing_simulation
  - end_to_end_autonomous_racing
tech_backbone: [reinforcement_learning]
tech_representation: [vehicle_state_reinforcement_learning]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
simulators_used: [torcs]
---

# Human Professional Level Driving Agent for Race Car Simulation Environments

> Human Professional Level Driving Agent for Race Car Simulation Environments | AI Open | Gergely Bári and László Palkovics

## Summary

This paper presents a state-based deep reinforcement-learning racing agent trained in simulation and benchmarked against a human e-sport champion. The key question is whether an agent can learn not only competitive lap times, but also recognizable expert driving strategies, from a relatively simple reward and vehicle-state observations.

The answer is mixed in an interesting way: the agent becomes very fast and often comparable to the champion, but some of its strongest behaviors rely on simulator idealizations rather than cleanly human-like driving.

## Method

The agent uses PPO and observes vehicle dynamic signals directly, including wheel speeds, longitudinal and lateral velocities and accelerations, yaw rate, and track-relative geometric state. It outputs continuous steering and throttle/brake commands.

The reward is built around forward progress, with the paper explicitly deriving the connection between a time-difference objective and centerline-progress reward. Additional terms penalize off-track behavior, reverse motion, vehicle damage, insufficient progress, and excessively large or non-feasible control actions.

This makes the method a good example of [[vehicle_state_reinforcement_learning]]: the policy is learned end to end with respect to control, but it does not rely on raw vision.

## Key Results

The paper compares the best learned lap with the best lap of a human champion and reports a close final result: the human remains slightly faster overall, but the agent is faster in some sectors and shows clear high-speed competence.

The deeper contribution is the driving-style analysis. The authors show that the agent can learn expert-like ideas such as using track width and operating near the grip limit, but it also develops distinctly simulator-driven artifacts. These include extremely sharp steering changes enabled by missing actuator rate limits and braking patterns that can induce full wheel lock yet still remain competitive in the simulator.

That makes the result more nuanced than a simple “agent beats human” story. The paper is as much about understanding what simulator RL actually learns as it is about headline performance.

## Related Work

This paper sits near earlier simulation racing RL works such as [[super_human_performance_in_gran_turismo_sport_using_deep_reinforcement_learning]], [[autonomous_overtaking_in_gran_turismo_sport_using_curriculum_reinforcement_learning]], and [[a_champion_level_vision_based_reinforcement_learning_agent_for_competitive_racing_in_gran_turismo_7]], but it differs in two ways.

First, it uses simulator vehicle-state signals rather than image observations at inference. Second, it leans hard into human-comparison analysis, using the champion baseline to inspect whether the learned policy's style really resembles professional-level driving.

It also complements [[champion_level_drone_racing_using_deep_reinforcement_learning]] from the opposite side of the realism spectrum: Swift proves transfer to physical hardware, while this paper exposes what high simulator performance can look like when reality constraints are weaker.

## Notes / Critique

The strongest contribution is the honesty of the analysis. The paper does not hide that the agent exploits the simulator; it uses that fact to make a more careful argument about what “professional-level” should mean in racing RL.

Its main limitation is transferability. Precisely because the policy learns from state-based simulation with idealized actuators, its best behaviors should not be assumed to survive in a physical racecar.
