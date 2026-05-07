---
tags: [source]
date: 2026-05-07
sources: 1
---

# Werner GGGV Diagrams Source

> Source: `raw/pdfs/Werner_GGGV-diagramms.pdf`
> Paper: A Quasi-Steady-State Black Box Simulation Approach for the Generation of g-g-g-v Diagrams, arXiv:2504.10225
> Code: https://github.com/TUM-AVS/GGGVDiagrams

## Summary

This arXiv paper presents an open-source, simulation-based method for generating [[g_g_g_v_diagrams]] from high-fidelity or proprietary vehicle models. The core problem is that autonomous racing planners and controllers often need simple acceleration-envelope constraints, but real race vehicles have nonlinear tire behavior, aerodynamic effects, speed-dependent load transfer, and 3D track effects that are difficult to capture with hand-derived optimization models.

The paper proposes a [[quasi_steady_state_vehicle_simulation|quasi-steady-state black-box simulation]] workflow: apply virtual longitudinal and vertical inertial forces to the vehicle model, hold speed constant with a wheel-torque controller, then run adaptive ramp-steer maneuvers to measure the maximum open-loop-stable lateral acceleration for each combination of speed, longitudinal acceleration, and vertical acceleration.

## Method

The approach treats the vehicle simulator as a black box and requires only forward simulation. For a desired longitudinal acceleration `ax`, it applies an external force `Fx,ext = -m ax` at the center of gravity. For a desired vertical acceleration `az`, it applies `Fz,ext = m(az - g)`. A PID wheel-torque controller then keeps the vehicle at a fixed speed while the virtual forces reproduce the tire-load and tire-slip conditions corresponding to the target acceleration state.

For each `(v, ax, az)` grid point, the algorithm:

- Initializes the model at target speed.
- Applies the virtual inertial forces.
- Waits for the speed controller to reach quasi-steady state.
- Performs a small steering step to estimate lateral acceleration gain.
- Runs a steering ramp with an adaptive rate.
- Detects the maximum open-loop-stable lateral acceleration before understeer or oversteer instability.
- Corrects the resulting lateral acceleration into the velocity-vector frame.

The implementation uses Open Car Dynamics as the demonstrated high-fidelity model, but the method is designed to work with any simulator that can expose the necessary vehicle states and accept wheel-torque inputs.

## Evaluation

The authors validate the method against a simplified force-constrained point-mass model with an analytical circular G-G envelope. The simulation points match the analytical boundary with very small reported lateral-acceleration error.

They then demonstrate the workflow on a high-fidelity two-track race-car model with speed- and pitch-dependent aerodynamics. The resulting envelopes show that aerodynamic changes can affect forward acceleration, braking potential, and combined longitudinal-lateral maneuvers in ways that would be awkward to reproduce with a simplified optimization formulation.

## Notes / Critique

The paper is especially useful for this vault because it bridges vehicle dynamics modeling and autonomous racing planning/control. It gives a practical way to produce constraint maps that can be consumed by point-mass planners, trajectory optimizers, MPC controllers, and other high-level racing stacks without forcing the planner to contain the full high-fidelity vehicle model.

The main caveat is that a simulation-generated G-G-G-V diagram is only as valid as the vehicle model, tire parameters, aerodynamic model, and sampling strategy used to generate it. The authors also note that uniform sampling over longitudinal acceleration can be inefficient and suggest adaptive sampling as future work.

## Pages Created From This Source

- [[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]]
- [[g_g_g_v_diagrams]]
- [[quasi_steady_state_vehicle_simulation]]
