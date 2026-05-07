---
tags: [source]
date: 2026-05-07
sources: 1
---

# Werner GripMap Source

> Source: `raw/pdfs/Werner_GripMap.pdf`
> Paper: GripMap: An Efficient, Spatially Resolved Constraint Framework for Offline and Online Trajectory Planning in Autonomous Racing, arXiv:2504.12115

## Summary

This arXiv paper introduces [[gripmap]], a framework for spatially resolving vehicle-dynamics constraints across a race track. The motivation is that autonomous racing planners often assume a single global vehicle model, while real grip varies by location because of rubber buildup, dust, debris, rain, track banking, and the software stack's own local control limitations.

GripMap stores local constraint-scaling factors in a Frenet-frame grid around the track centerline. These factors scale baseline [[g_g_g_v_diagrams|G-G-G-V]] acceleration limits so offline raceline optimization and online trajectory planning can adapt to local grip availability without carrying a full spatially varying vehicle model in the planner.

## Method

The track is discretized in Frenet coordinates `(s, n)`, where `s` is distance along the reference line and `n` is lateral offset. Each grid cell stores a dimensionless scaling factor `theta_ij`. For a point-mass model constrained by baseline G-G-G-V limits, the local acceleration limits become:

- `ax,max(si, nj) = theta_ij * ax,max,base(v, az)`
- `ay,max(si, nj) = theta_ij * ay,max,base(v, az)`

The lookup is implemented as a dense matrix with direct index computation from `(s, n)`, described as a perfect-hash-like mechanism. This gives constant-time access and low memory overhead compared with Cartesian grids, because the Frenet grid avoids large off-track regions.

The framework is integrated into:

- Offline minimum-lap-time optimization, where the raceline is optimized under locally scaled acceleration constraints.
- A high-frequency sampling-based online planner, where sampled candidate trajectories are evaluated against local GripMap-scaled G-G-G-V limits.

In the online planner, grip-limit exceedance is treated as a soft cost rather than a strict rejection, allowing the planner to trade small limit exceedances against collision avoidance or racecraft constraints.

## Evaluation

The paper reports real-world autonomous racing experience from A2RL at Yas Marina Circuit. The final GripMap used local scaling factors between 75% and 100% of the baseline G-G-G-V estimate. Compared with a globally conservative 75% scaling factor, the spatially resolved map improved lap time by 5.2%.

Runtime evaluation in a ROS2 Python sampling-based planner showed little overhead. With 1,000 sampled trajectories per planning step and 40 discretization points per trajectory, GripMap-informed planning averaged 0.1565 s versus 0.1553 s without GripMap, an overhead of about 0.77%.

The paper also analyzes a real Indy Autonomous Challenge spin-out at Las Vegas Motor Speedway, where a high-speed outside overtake entered a lower-grip dusty region. A resimulation suggests that GripMap-informed planning would reduce corner-entry speed by up to 7 m/s and keep tire utilization within the local grip limit.

## Notes / Critique

GripMap is useful for this vault because it turns grip variability from an implicit failure mode into an explicit planning constraint. It also extends the previous G-G-G-V discussion: [[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]] can generate acceleration envelopes, while GripMap makes those envelopes spatially local.

The main limitation is parametrization. The paper uses iterative tuning from real racing data and empirical extrapolation away from the raceline. The current GripMap is static during runtime and does not separate physical tire-road friction limits from software-driver limitations, since both are lumped into the local scaling factor.

## Pages Created From This Source

- [[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]]
- [[gripmap]]
