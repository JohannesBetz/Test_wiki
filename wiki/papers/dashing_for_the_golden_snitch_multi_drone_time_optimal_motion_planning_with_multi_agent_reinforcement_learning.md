---
tags: [paper]
date: 2026-05-13
task: robotics
venue: "2025 IEEE International Conference on Robotics and Automation (ICRA)"
sources: 1
year: "2025"
doi: "10.1109/ICRA55743.2025.11128442"
topic:
  - autonomous_drone_racing
  - Highly_dynamic_autonomous_system
  - real_world_robotic_reinforcement_learning
tech_backbone: [reinforcement_learning]
tech_representation: [multi_agent_time_optimal_motion_planning]
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

# Dashing for the Golden Snitch: Multi-Drone Time-Optimal Motion Planning with Multi-Agent Reinforcement Learning

> Dashing for the Golden Snitch: Multi-Drone Time-Optimal Motion Planning with Multi-Agent Reinforcement Learning | 2025 IEEE International Conference on Robotics and Automation (ICRA) | Xian Wang, Jin Zhou, Yuanli Feng, Jiahao Mei, Jiming Chen, and Shuo Li

## Summary

This paper studies how multiple drones can plan time-optimal motion jointly through a multi-agent reinforcement learning formulation.

Its main value for this vault is that it pushes high-speed aerial autonomy beyond the single-agent case. Instead of only asking how one drone should fly fast, it asks how several drones should optimize motion when their trajectories are coupled through interaction.

## Method

The paper formulates multi-drone time-optimal motion planning with multi-agent RL.

That is a meaningful shift in emphasis. High-speed drone autonomy is often framed as perception, control, or single-agent racing. Here the core problem is coordination under shared time-optimal objectives, where each drone's decision changes the feasible and optimal choices of the others.

For the vault, the key methodological idea is that learned multi-agent interaction can be used not only for adversarial pursuit-evasion but also for fast coordinated motion planning.

## Key Results

The strongest result for this vault is structural: the paper expands the space of drone-racing-adjacent autonomy from solo agility to explicitly multi-agent time-optimal planning.

That matters because future high-speed aerial systems will likely need to coordinate in dense shared airspace, not only win isolated time trials on fixed courses.

## Hardware Used

- [[drones]]


## Related Work

This paper belongs directly near [[autonomous_drone_racing]], where it broadens the branch from single-drone speed to multi-drone coordination.

It also fits with [[reinforcement_learning]] and [[real_world_robotic_reinforcement_learning]] as another example of RL being pushed into tightly coupled embodied interaction settings.

Compared with [[learning_multipursuit_evasion_for_safe_targeted_navigation_of_drones]], the overlap is multi-agent drone RL. The difference is important: the pursuit-evasion paper is adversarial and safety-driven, while this paper is centered on time-optimal coordinated motion planning.

Compared with [[champion_level_drone_racing_using_deep_reinforcement_learning]], this paper is less about single-agent sim-to-real racing excellence and more about scaling aggressive flight intelligence into interacting aerial teams.

## Notes / Critique

The strongest contribution is the interaction framing. Multi-drone time-optimality is not just many copies of single-drone planning; it is a genuinely coupled decision problem.

For the vault, this makes the paper a useful waypoint between drone racing, multi-agent autonomy, and learned motion planning.
