---
tags: [technique]
date: 2026-05-22
sources: 1
---

# Motion Matching

## Definition

Motion matching selects or blends motion segments from a structured motion library based on the current state and desired future behavior, rather than relying on one single fixed controller or one hand-scripted transition graph.

## Key Approaches

In [[perceptive_humanoid_parkour_chaining_dynamic_human_skills_via_motion_matching]], motion matching is used as the organizing principle for chaining dynamic humanoid skills under perception. For this vault, the key point is not only that motions are matched, but that dynamic embodied competence is framed as skill composition and transition quality rather than only as steady-state control.

In [[animal_gaits_on_quadrupedal_robots_using_motion_matching_and_model_based_control]], motion matching is used in a quadruped setting to retrieve animal-inspired gait fragments that can be tracked by a model-based controller. That makes the technique less about extreme parkour and more about generating diverse, natural gait structure under robotic constraints.

## Representative Papers

- [[perceptive_humanoid_parkour_chaining_dynamic_human_skills_via_motion_matching]]
- [[animal_gaits_on_quadrupedal_robots_using_motion_matching_and_model_based_control]]

## Open Problems

Motion matching becomes much harder in robots than in animation: skill libraries must remain physically executable, transitions must tolerate sensing and actuation error, and the retrieval logic must be fast enough that the robot can commit to the next behavior before the world changes again.

The quadruped paper adds a second question: once motion matching is paired with model-based tracking, how much of the final behavior quality really comes from the library and retrieval logic, and how much still comes from the controller underneath?
