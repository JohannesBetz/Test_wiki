---
tags: [technique]
date: 2026-05-06
sources: 2
---

# Model Predictive Control

## Definition

Model predictive control repeatedly solves a finite-horizon optimization problem, applies the first control action, then replans from the updated vehicle state.

## Key Approaches

In [[autonomous_vehicles_on_the_edge]], MPC is central to both [[autonomous_racing_planning]] and [[autonomous_racing_control]]. Variants include NMPC, MPPI, stochastic MPC, sparse randomized MPC, LPV-MPC, tube MPC, learning MPC, envelope control, and MPC combined with game theory, Gaussian processes, DNNs, and reinforcement learning.

[[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]] is relevant to MPC because [[g_g_g_v_diagrams]] can provide compact acceleration-envelope constraints. This lets an MPC formulation respect near-limit vehicle behavior derived from high-fidelity simulation without directly embedding the full black-box model in the optimizer.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]]

## Open Problems

MPC for racing must handle nonlinear vehicle/tire dynamics, long enough horizons for feasibility and interaction, real-time solve times, uncertainty, changing friction, and safety constraints without becoming too conservative for racing performance.
