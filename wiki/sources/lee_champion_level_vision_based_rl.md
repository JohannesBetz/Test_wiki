---
tags: [source]
date: 2026-05-08
sources: 1
---

# Lee Champion-Level Vision-Based RL Source

> Source: `raw/pdfs/Lee_A_Champion-Level_Vision-Based_Reinforcement_Learning.pdf`
> Paper: A Champion-Level Vision-Based Reinforcement Learning Agent for Competitive Racing in Gran Turismo 7, RA-L 2025

## Summary

This paper presents a competitive autonomous racing agent for Gran Turismo 7 that relies only on egocentric camera views and onboard sensor data at inference time. The key claim is that champion-level multi-car racing performance is possible without the precise global state and opponent localization typically used by top simulator-only racing agents.

For this vault, the paper is important because it closes part of the gap between high-performance simulator RL and deployable perception-limited autonomy.

## Method

The agent uses an asymmetric recurrent actor-critic setup. During training, the critic receives privileged global features, while the actor is restricted to deployment-realistic observations. The actor combines visual input, proprioceptive features, and recurrence so it can retain track layout and opponent information under partial observability and occlusion.

The paper also emphasizes training regularization and efficiency, including data augmentation and periodic network reinitialization, plus a reward that combines time-trial progress with multi-opponent racing incentives from earlier GT Sophy work.

## Evaluation

The system is evaluated in Gran Turismo 7 against the built-in AI field. The headline result is strong: the agent consistently finishes first against 19 built-in AI opponents even when starting from the last position.

The paper also reports ablation studies supporting the asymmetric setup, recurrent memory, and regularization choices. The authors position the result as the first vision-based autonomous racing agent to achieve champion-level performance in competitive racing scenarios.

## Notes / Critique

The strongest aspect is the realism shift. The paper keeps the advantages of simulator RL while reducing reliance on privileged localization signals at deployment.

The main limitation is that the policy is still validated in simulation and still uses privileged critic information during training. That makes it more realistic than pure global-feature racing agents, but not yet a direct recipe for physical racecars.

## Pages Created From This Source

- [[a_champion_level_vision_based_reinforcement_learning_agent_for_competitive_racing_in_gran_turismo_7]]
- [[asymmetric_recurrent_actor_critic]]
