---
tags: [source]
date: 2026-05-08
sources: 1
---

# Yang Safe and Efficient Self-Evolving Source

> Source: `raw/pdfs/Yang_A_Safe_and_Efficient_Self-Evolving.pdf`
> Paper: A Safe and Efficient Self-Evolving Algorithm for Decision-Making and Control of Autonomous Driving Systems, IEEE T-ITS 2025

## Summary

This paper studies how an autonomous driving system can keep improving itself through reinforcement learning without suffering the usual cost of unsafe exploration and slow training. The focus is not racing, but safe decision making and control in dense highway traffic with lane changes, following, and overtaking.

The core motivation is that pure RL can in principle self-evolve through trial and error, but real autonomous driving cannot tolerate collision-heavy exploration or million-step training loops.

## Method

The paper proposes a hybrid Mechanism-Experience-Learning approach. The mechanism part is a constrained nonlinear optimization layer inspired by MPC, which guarantees safe actions through vehicle, collision, and following constraints.

The experience part is a learned driving tendency concept meant to mimic the vague directional preferences of human drivers. Instead of searching over all possible actions uniformly, the algorithm learns a tendency factor that biases the optimizer toward more reasonable maneuver directions and thereby shrinks the search space.

The learning part is an actor-critic RL architecture based on soft actor-critic. The critic estimates value with twin Q networks, while the actor combines a traffic interaction model, a driving-tendency network, and the constrained optimizer.

## Evaluation

The paper evaluates the method in CARLA highway lane-change scenarios with both static obstacles and dense dynamic traffic. The main reported result is that training converges in roughly 4000 to 6000 steps, remains collision-free during training, and performs better than comparison MPC and vanilla RL baselines in dynamic traffic.

The authors also report a practical training-time claim: the total training effort is said to correspond to less than 10 minutes of real-world driving time.

## Notes / Critique

The most interesting contribution is the hybridization. The paper does not ask RL to discover basic safety structure from scratch; it bakes that structure into the policy class and lets learning focus on preference shaping and adaptation.

The main limitation for this vault is domain mismatch: the work is about structured highway driving rather than autonomous racing. Still, it is useful as an adjacent example of safe self-improving decision/control loops under hard constraints.

## Pages Created From This Source

- [[a_safe_and_efficient_self_evolving_algorithm_for_decision_making_and_control_of_autonomous_driving_systems]]
- [[mechanism_experience_learning]]
