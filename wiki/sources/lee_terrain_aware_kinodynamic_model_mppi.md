---
tags: [source]
date: 2026-05-13
sources: 1
---

# Lee Terrain-Aware Kinodynamic Model MPPI Source

> Source: `raw/pdfs/Lee_Learning_Terrain-Aware_Kinodynamic_Model_for_Autonomous_Off-Road_Rally_Driving_With_Model_Predictive_Path_Integral_Control.pdf`
> Paper: Learning Terrain-Aware Kinodynamic Model for Autonomous Off-Road Rally Driving With Model Predictive Path Integral Control, IEEE RA-L 2023

## Summary

This paper studies autonomous off-road rally driving where the same vehicle must stay controllable across rapidly changing terrain, grip, and body-motion conditions.

For this vault, the paper matters because it combines two ideas that show up repeatedly in high-dynamics autonomy: learned terrain-aware vehicle modeling and aggressive stochastic receding-horizon control through path integral methods.

## Method

The paper learns a terrain-aware kinodynamic model and uses it inside model predictive path integral control (`MPPI`).

That combination is attractive because off-road rally driving breaks many neat assumptions. Terrain changes alter the effective dynamics, and the controller still has to react at racing-like speeds. A learned model handles the terrain dependence, while MPPI gives a way to optimize aggressive behavior online without requiring a perfectly smooth analytical model.

## Evaluation

The paper is framed around autonomous off-road rally driving and appears in IEEE Robotics and Automation Letters in 2023.

For this vault, the key evaluation significance is architectural: it strengthens the branch of work that treats aggressive driving not as a fixed-road racing problem only, but as a high-speed adaptation-and-control problem under changing terrain.

## Notes / Critique

The strongest contribution is the coupling between terrain awareness and control. A high-speed controller is only as good as the model of what the surface is allowing right now.

This source also sits naturally between older off-road rally control papers such as [[high_speed_cornering_for_autonomous_off_road_rally_racing]] and more general aggressive-control work such as [[aggressive_driving_with_model_predictive_path_integral_control]].

## Pages Created From This Source

- [[learning_terrain_aware_kinodynamic_model_for_autonomous_off_road_rally_driving_with_model_predictive_path_integral_control]]
- [[model_predictive_path_integral_control]]
