---
tags: [paper]
date: 2026-05-07
task: autonomous_racing
venue: "arXiv 2025"
sources: 1
year: "2025"
doi: "10.48550/arXiv.2504.10225"
url: "https://arxiv.org/abs/2504.10225"
topic:
  - autonomous_racing
  - trajectory_planning
  - motion_control
  - vehicle_dynamics
tech_backbone: []
tech_representation: [g_g_g_v_diagrams]
tech_generation: [quasi_steady_state_vehicle_simulation]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [cars_and_race_cars]
simulators_used: []
---

# A Quasi-Steady-State Black Box Simulation Approach for the Generation of G-G-G-V Diagrams

> A Quasi-Steady-State Black Box Simulation Approach for the Generation of g-g-g-v Diagrams | arXiv:2504.10225 | Werner, Sagmeister, Piccinini, and Betz | Code: https://github.com/TUM-AVS/GGGVDiagrams

## Summary

This paper introduces an open-source black-box simulation workflow for generating [[g_g_g_v_diagrams]], which extend classical G-G acceleration envelopes with speed and vertical acceleration. These diagrams are useful as compact dynamic constraints for [[autonomous_racing_planning]], [[autonomous_racing_control]], and [[model_predictive_control]] when the underlying vehicle dynamics are too complex to embed directly in an optimizer.

The central idea is to emulate target longitudinal and vertical acceleration states with virtual inertial forces while holding vehicle speed constant. This lets the simulator perform quasi-steady ramp-steer tests at specific `(v, ax, az)` operating points and measure the maximum open-loop-stable lateral acceleration.

## Method

The method treats the vehicle model as a forward-simulation black box. It applies virtual forces at the vehicle center of gravity:

- `Fx,ext = -m ax` to emulate the inertial effect of longitudinal acceleration.
- `Fz,ext = m(az - g)` to emulate changes in vertical acceleration and normal load.

A PID wheel-torque controller holds the target speed and counteracts drag, rolling resistance, and the virtual longitudinal force. Positive emulated `ax` is represented by drive torque on the driven axle, while negative `ax` is represented by braking torque distributed according to brake balance. The paper intentionally omits powertrain torque limits so the generated envelope focuses on tire-force limitations rather than engine or actuator limits.

For each sampled speed, longitudinal acceleration, and vertical acceleration, the toolchain runs an adaptive ramp-steer procedure. A small steering step estimates lateral acceleration gain; this gain sets a steering-ramp rate that is slow enough to approximate quasi-steady behavior without excessive runtime. The maximum lateral acceleration is then detected differently for understeer and oversteer:

- Understeer: use the local maximum in lateral acceleration before cornering capability drops.
- Oversteer: detect the transition from quasi-steady cornering to open-loop instability by comparing lateral acceleration with speed times yaw rate.

Finally, the lateral acceleration is corrected into the velocity-vector frame so the resulting constraint can be used by simpler point-mass planning models that do not include sideslip as a state.

## Key Results

The method is validated on a simplified force-constrained point-mass vehicle with an analytical G-G envelope. The generated simulation points closely match the analytical boundary, supporting the correctness of the ramp-steer and detection procedure.

The authors also apply the workflow to a high-fidelity two-track race-car model with speed- and pitch-dependent aerodynamics. Compared with a fixed-aerodynamics baseline, the generated envelopes show small but meaningful changes in forward acceleration, braking potential, and combined acceleration regions. This demonstrates why black-box simulation can be valuable: model complexity can be added without deriving a differentiable optimization model for every subsystem.

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

The paper connects to classical G-G diagram use in vehicle dynamics and to autonomous racing papers that use acceleration envelopes as planning or control constraints, including [[path_tracking_for_autonomous_race_car_based_on_g_g_diagram]]. It also relates to minimum-lap-time trajectory optimization, online trajectory planning on 3D race tracks, and MPC methods that need compact feasibility constraints.

Within this vault, it should be read as a constraint-generation companion to [[autonomous_vehicles_on_the_edge]], especially the survey's planning and control sections.

## Notes / Critique

The strongest contribution is methodological: the virtual-force setup decouples target longitudinal acceleration from changing vehicle speed, making it possible to sample quasi-steady acceleration limits with high-fidelity vehicle models. The open-loop-stability filter is also important because planners should not treat unstable transient states as feasible steady operating points.

The method still depends on simulator fidelity. Incorrect tire parameters, aerodynamic maps, brake balance, actuator assumptions, or road-friction estimates will produce misleading constraints. The paper flags longitudinal-acceleration sampling as a future improvement area because uniform grids can waste simulation budget while undersampling the edges of the envelope.
