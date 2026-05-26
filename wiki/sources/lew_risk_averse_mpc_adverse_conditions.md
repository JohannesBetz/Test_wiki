---
tags: [source]
date: 2026-05-13
sources: 1
---

# Lew Risk-Averse MPC Adverse Conditions Source

> Source: `raw/pdfs/Lew_Risk-Averse_Model_Predictive_Control_for_Racing_in_Adverse_Conditions.pdf`
> Paper: Risk-Averse Model Predictive Control for Racing in Adverse Conditions, ICRA 2025

## Summary

This paper studies a brittle point in autonomous racing control: standard MPC can look strong under nominal tire assumptions and then fail badly when friction or tire parameters are overestimated in adverse conditions.

For this vault, the paper matters because it reframes "fast racing control" as a risk allocation problem under model mismatch. Instead of planning with one optimistic vehicle model, it plans over uncertainty in friction limits and tire parameters.

## Method

The paper proposes a risk-averse MPC framework with a conditional value at risk (`CVaR`) constraint.

Its formulation is sample-based: multiple expressive vehicle dynamics models with different tire parameters are considered during planning, allowing the controller to reason over a structured family of plausible low-friction behaviors rather than only one nominal prediction.

The paper also emphasizes tractability. The resulting optimization is solved with sequential quadratic programming and GPU parallelization so that uncertainty-aware nonlinear racing control can still run in real time.

## Evaluation

Experiments are reported on a Lexus LC 500 in adverse road conditions.

The key practical result is that risk-averse MPC preserves reliable performance where a deterministic baseline that plans with a single dynamics model can lose control.

## Notes / Critique

The strongest contribution is not merely adding conservatism. It is identifying a failure mode that matters specifically at the handling limit: when the model is optimistic about available friction, the controller can generate plans that are fast on paper and unstable on asphalt.

This source also connects cleanly to [[risk_averse_model_predictive_control]] as a reusable control idea and to [[one_model_to_drift_them_all_physics_informed_conditional_diffusion_model_for_driving_at_the_limits]], which tackles a related uncertainty problem through multimodal online model adaptation.

## Pages Created From This Source

- [[risk_averse_model_predictive_control_for_racing_in_adverse_conditions]]
- [[risk_averse_model_predictive_control]]
