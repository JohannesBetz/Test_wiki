---
tags: [technique]
date: 2026-05-08
sources: 1
---

# Asymmetric Recurrent Actor-Critic

## Definition

An asymmetric recurrent actor-critic trains a policy with partial, deployment-realistic observations while allowing the critic to use privileged simulator information, and it adds recurrence so the actor can retain latent context over time.

In racing, this is especially useful when the agent must infer track layout and opponent state from limited egocentric sensing under occlusion.

## Key Approach

[[a_champion_level_vision_based_reinforcement_learning_agent_for_competitive_racing_in_gran_turismo_7]] uses this design for competitive racing in Gran Turismo 7.

Its three key ingredients are:

- an actor limited to onboard visual and sensor input,
- a critic with access to privileged global features during training,
- and a recurrent memory module for partial observability.

This makes the method a stronger fit for vision-based racing than a feedforward policy trained on fully privileged state.

## Relationship to End-to-End Racing

This technique belongs near [[end_to_end_autonomous_racing]] and extends the broader idea in [[asymmetric_actor_critic]].

Compared with a standard asymmetric actor-critic, it adds explicit temporal memory, which is especially important in racing because occluded opponents and hidden track geometry must be inferred over time rather than from one frame alone.

## Representative Papers

- [[a_champion_level_vision_based_reinforcement_learning_agent_for_competitive_racing_in_gran_turismo_7]]

## Open Problems

Open problems include transferring the same setup to physical racecars, handling stronger appearance shift, and understanding how much recurrence versus explicit state estimation is needed in different racing conditions.
