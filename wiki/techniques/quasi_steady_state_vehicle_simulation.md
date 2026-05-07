---
tags: [technique]
date: 2026-05-07
sources: 1
---

# Quasi-Steady-State Vehicle Simulation

## Definition

Quasi-steady-state vehicle simulation estimates near-equilibrium vehicle behavior at specified operating points without simulating an entire transient maneuver or lap.

For autonomous racing, the technique is useful when the goal is not to reproduce a full trajectory, but to measure stable acceleration limits that can later constrain a planner or controller.

## Key Approach

In [[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]], quasi-steady-state simulation is used to generate [[g_g_g_v_diagrams]]. The method fixes a target speed, emulates desired longitudinal and vertical acceleration states with virtual forces, and uses wheel-torque control to keep the vehicle at that operating point while a steering ramp probes lateral acceleration limits.

The method is black-box in the sense that it does not require differentiating or reformulating the vehicle model. This is valuable for high-fidelity simulators, proprietary models, and vehicle models with complex subsystems such as aerodynamics, active differentials, electronic stability control, or learned dynamics modules.

## Representative Papers

- [[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]]

## Open Problems

The main risks are simulator dependence and sampling efficiency. A quasi-steady-state envelope can be misleading if the vehicle model is not well validated, and dense sampling across speed, longitudinal acceleration, and vertical acceleration can become expensive without adaptive strategies.
