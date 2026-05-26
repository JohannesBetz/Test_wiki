---
tags: [paper]
date: 2026-05-13
task: autonomous_racing
venue: "2025 IEEE International Conference on Robotics and Automation (ICRA)"
sources: 1
year: "2025"
doi: "10.1109/ICRA55743.2025.11127729"
topic:
  - autonomous_racing
  - autonomous_racing_control
  - motion_control
  - learning_based_control
tech_backbone: []
tech_representation: [risk_averse_model_predictive_control]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [cars_and_race_cars]
simulators_used: []
---

# Risk-Averse Model Predictive Control for Racing in Adverse Conditions

> Risk-Averse Model Predictive Control for Racing in Adverse Conditions | 2025 IEEE International Conference on Robotics and Automation (ICRA) | Thomas Lew, Marcus Greiff, Franck Djeumou, Makoto Suminaka, Michael Thompson, and John Subosits

## Summary

This paper addresses a common but dangerous mismatch in racing control: MPC can become overconfident when its vehicle model overestimates the available friction or tire-force capability, especially on wet or otherwise degraded surfaces.

The proposed answer is a risk-averse MPC framework that explicitly reasons over uncertainty in friction limits and tire parameters instead of trusting one nominal model.

## Method

The method uses a sample-based approximation of an optimal control problem with a conditional value at risk (`CVaR`) constraint.

That choice matters because adverse-condition racing is not just noisy in a generic sense. The uncertainty is structured and physically meaningful: tire parameters and friction limits can shift in ways that stay correlated over time and directly change whether an aggressive plan is feasible.

By planning over a set of expressive vehicle dynamics models with different tire parameters, the controller can account for worse but plausible regimes rather than implicitly assuming the most optimistic one.

The paper also makes a systems contribution by keeping the method numerically practical through sequential quadratic programming and GPU parallelization.

## Key Results

Experiments on a Lexus LC 500 show that risk-averse MPC enables reliable performance in adverse road conditions, while a deterministic baseline that plans with a single dynamics model may lose control.

For this vault, the central result is conceptual as well as empirical: it shows that near-limit racing control under uncertainty is not only a model-accuracy problem, but also a risk-measure design problem.

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

This paper belongs directly near [[model_predictive_control]] and [[autonomous_racing_control]], since the contribution is a different way of formulating what the controller should optimize under uncertainty.

Compared with [[lipschitz_regularized_learned_dynamics_for_autonomous_racing_mpc]], the overlap is controller robustness under model mismatch, but the emphasis is different. The Lipschitz paper shapes the learned model to be more optimizer-friendly, while this paper keeps multiple plausible models in play and explicitly controls tail risk.

Compared with [[one_model_to_drift_them_all_physics_informed_conditional_diffusion_model_for_driving_at_the_limits]], this paper is less about online multimodal adaptation and more about conservative decision-making under known uncertainty families. Together they form a nice pair: one paper tries to infer the right dynamics regime, the other tries to remain safe when the regime is uncertain.

## Notes / Critique

The strongest idea is that racing in adverse conditions should not be treated as nominal racing plus a safety margin. The CVaR formulation acknowledges that the real danger lies in tail events where optimistic tire assumptions become wrong at exactly the moment the vehicle is using nearly all available grip.

It also gives the vault a more mature uncertainty story: not all robustness comes from better prediction; some of it comes from optimizing the right risk-sensitive objective in the first place.
