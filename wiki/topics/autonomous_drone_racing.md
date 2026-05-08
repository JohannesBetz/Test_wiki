---
tags: [topic]
date: 2026-05-07
sources: 1
---

# Autonomous Drone Racing

## Definition

Autonomous drone racing studies quadrotors flying through 3D racing tracks at high speed, often through gates, while perceiving and controlling from onboard sensors. It is a key subdomain of [[Highly_dynamic_autonomous_system|highly dynamic autonomous systems]].

## Key Approaches

- [[autonomous_drone_racing_a_survey]] frames ADR as a full-stack benchmark where modeling, state estimation, planning, control, learning, and onboard hardware must all co-evolve to improve one simple metric: lap time.
- Gate detection and gate-relative localization.
- [[visual_inertial_odometry]] with drift correction.
- Time-optimal trajectory generation and MPC.
- Deep [[reinforcement_learning]] policies trained in simulation.
- [[sim_to_real_transfer]] using domain randomization or real-world residual modeling.
- Perception-aware planning/control that trades pure speed against keeping gates visible.
- Safety-assured high-speed navigation in unknown clutter, where the core challenge shifts from fixed-course optimization to balancing aggression with obstacle-aware fallback safety.
- [[vision_language_action_models]] for command-conditioned FPV control, where a multimodal pretrained policy absorbs more of perception-to-action mapping directly instead of relying on a fully explicit stack.

[[champion_level_drone_racing_using_deep_reinforcement_learning]] is one of the strongest field milestones highlighted by the survey: [[swift]] shows that onboard-only perception plus sim-to-real RL can beat champion human pilots on a physical racing track.

[[safety_assured_high_speed_navigation_for_mavs]] shows a neighboring branch of the field: once systems leave fixed known race tracks, the central problem becomes how to keep high speed without sacrificing safety under occlusion and unknown clutter.

[[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]] adds a newer foundation-model branch: [[racevla]] explores whether a language-conditioned VLA can act as a usable racing-drone controller, even if current speeds and latency are still far from top-tier racing performance.

[[learning_multipursuit_evasion_for_safe_targeted_navigation_of_drones]] adds a neighboring adversarial-navigation branch: instead of racing a fixed course, a drone evader must survive and reach a target while multiple pursuers adapt against it.

## Representative Papers

- [[champion_level_drone_racing_using_deep_reinforcement_learning]]
- [[autonomous_drone_racing_a_survey]]
- [[safety_assured_high_speed_navigation_for_mavs]]
- [[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]]
- [[learning_multipursuit_evasion_for_safe_targeted_navigation_of_drones]]

## Open Problems

Open problems include robust perception under motion blur and lighting changes, onboard-only state estimation, crash recovery, opponent-aware racing strategy, sim-to-real transfer, and safety-performance tradeoffs under severe latency and actuation constraints.

The SUPER result sharpens a neighboring challenge: even outside formal racing, drone systems need ways to preserve speed in unknown clutter without relying on optimistic assumptions that quietly erase safety.

The ADR survey adds a full-stack challenge: progress in drone racing rarely comes from one module alone, so future gains likely depend on tighter co-design across aerodynamics, sensing, estimation, planning, control, and learning.

RaceVLA adds a foundation-model challenge: multimodal pretrained control may broaden task flexibility, but it also intensifies latency, interpretability, and action-grounding concerns in a domain where mistakes happen very quickly.

Multi-pursuer evasion adds an interaction challenge: future drone-racing systems may eventually need opponent-aware tactics that look less like single-agent time trials and more like adversarial aerial games.
