---
tags: [source]
date: 2026-05-08
sources: 1
---

# Xiao Multi-Pursuit Evasion Source

> Source: `raw/pdfs/Xiao_Learning_Multipursuit_Evasion_for_Safe_Targeted_Navigation_of_Drones.pdf`
> Paper: Learning Multipursuit Evasion for Safe Targeted Navigation of Drones, IEEE Transactions on Artificial Intelligence 2024

## Summary

This paper studies safe target-reaching flight for a drone that is being physically threatened by multiple pursuer drones. The core question is how an evader can learn to avoid adversarial attacks while still making progress toward a target.

For this vault, the paper is useful as a bridge between [[pursuit_evasion_robotics]], drone autonomy, and multi-agent [[reinforcement_learning]]. It is not a racing paper, but it lives in a similar part of the design space: fast embodied agents operating under uncertainty, competition, and safety pressure.

## Method

The paper proposes asynchronous multistage deep reinforcement learning (`AMS-DRL`).

The main idea is to train pursuers and evader across multiple stages rather than all at once. The agents are evolved asynchronously in a pursuit-evasion game, with one side fixed at a previously learned policy while the other side improves against it.

The authors describe this as a bipartite multi-stage training process intended to:

- let the evader learn from increasingly capable pursuers,
- let the pursuers adapt to a progressively stronger evader,
- and push the interaction toward a Nash-equilibrium-style balance rather than brittle overfitting to one opponent snapshot.

## Evaluation

The paper reports extensive simulations comparing AMS-DRL with baseline methods, focusing on navigation success under multiple pursuer attacks and on how geometry and relative speed affect outcomes.

It also includes physical drone experiments, which matter a lot for this vault. The contribution is not only algorithmic; it shows that the learned policies can be executed in real-time flight rather than only inside simulation.

## Notes / Critique

The strongest contribution is the multi-stage adversarial training structure. Multi-agent RL often becomes unstable or overly specialized, and the asynchronous staged design is a direct attempt to make that interaction more learnable.

The paper's limitation is scope realism. It validates targeted adversarial navigation, but it is still a narrower setting than the richer uncertainty and sensing messiness of open-world multi-drone autonomy. Even so, it is a strong adjacent result for understanding how competitive drone behavior might be learned safely.

## Pages Created From This Source

- [[learning_multipursuit_evasion_for_safe_targeted_navigation_of_drones]]
- [[asynchronous_multistage_deep_reinforcement_learning]]
