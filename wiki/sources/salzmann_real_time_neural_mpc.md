---
tags: [source]
date: 2026-05-13
sources: 1
---

# Salzmann Real-Time Neural MPC Source

> Source: `raw/pdfs/Salzmann_Real-Time_Neural_MPC_Deep_Learning_Model_Predictive_Control_for_Quadrotors_and_Agile_Robotic_Platforms.pdf`
> Paper: Real-Time Neural MPC: Deep Learning Model Predictive Control for Quadrotors and Agile Robotic Platforms, IEEE RA-L 2023

## Summary

This paper studies how to make model predictive control practical for very fast robotic platforms by replacing expensive online optimization structure with a learned neural approximation.

For this vault, the paper is valuable as adjacent high-dynamics control work. It is not a racing paper, but it directly addresses a recurring problem in both racing and agile flight: MPC is powerful, but real-time solve time can become the bottleneck exactly when the system is moving fast enough that the controller matters most.

## Method

The central idea is `Neural MPC`: use deep learning to approximate the behavior of an MPC controller closely enough that the deployment-time controller can run at much higher speed than a conventional online solver.

The paper targets quadrotors and related agile robotic systems, where tight control loops and aggressive maneuvers make raw optimization latency especially costly.

Conceptually, the method sits between classical MPC and learned control:

- it keeps the structure and behavior of an MPC expert,
- but distills that behavior into a fast neural policy for execution.

## Evaluation

The work appears in IEEE Robotics and Automation Letters and is framed for quadrotors and agile robotic platforms.

For this vault, the important evaluation point is not just that the policy is learned, but that it is meant to preserve the practical benefits of MPC while improving runtime enough for agile deployment.

## Notes / Critique

The strongest contribution is the systems tradeoff it makes explicit: in agile robotics, the best controller on paper may lose to a slightly approximate controller that can run much faster.

Its limitation for this vault is domain distance. The paper is about agile flight and robotic platforms more broadly, not autonomous racing specifically. Still, it speaks directly to the same latency-performance tradeoff that racing controllers face.

## Pages Created From This Source

- [[real_time_neural_mpc_deep_learning_model_predictive_control_for_quadrotors_and_agile_robotic_platforms]]
- [[neural_mpc]]
