---
tags: [technique]
date: 2026-05-07
sources: 2
---

# Kineto-Dynamical Planning

## Definition

Kineto-dynamical planning is a minimum-time trajectory-planning approach that uses a reduced vehicle-dynamics model richer than a pure point-mass approximation but cheaper than a full high-fidelity simulator or full multibody optimal-control model.

In autonomous racing, it is useful when a planner must reason about feasibility near the handling limit, including lateral-velocity and load-transfer effects, while still replanning online.

## Key Approach

[[kineto_dynamical_planning_and_accurate_execution_of_minimum_time_maneuvers_on_three_dimensional_circuits]] formulates kineto-dynamical planning on 3D race tracks with:

- Curvilinear coordinates on a nonplanar ribbon-road model.
- First-order yaw-rate and lateral-velocity dynamics.
- Learned G-G-V-style acceleration envelopes that account for slope, banking, and vertical acceleration.
- Economic NMPC for direct minimum-time online replanning.
- Iterative closed-loop learning of model parameters and performance limits.

The design goal is to sit between two extremes: point-mass planners that may be too optimistic, and high-fidelity optimal-control models that are too expensive for repeated online use.

## Relationship to G-G-G-V Diagrams and MPC

[[g_g_g_v_diagrams]] provide one route to compact dynamic constraints for planners and controllers. Kineto-dynamical planning uses a similar compact-envelope idea, but wraps it inside a stateful planning model that also predicts yaw-rate and lateral-velocity evolution.

It is also a concrete instance of [[model_predictive_control]] for racing. The MPC is not just tracking a reference; it solves an economic minimum-time planning problem online under learned dynamic constraints.

## Representative Papers

- [[real_time_optimal_control_of_an_autonomous_rc_car_with_minimum_time]]
- [[kineto_dynamical_planning_and_accurate_execution_of_minimum_time_maneuvers_on_three_dimensional_circuits]]

## Open Problems

The main open problems are robustness under changing tires and friction, adaptation to unseen tracks, integration with obstacle-avoidance planners, and deciding how much model detail is worth the extra compute in real-time racing systems.
