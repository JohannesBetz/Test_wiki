---
tags: [source]
date: 2026-05-13
sources: 1
---

# Djeumou One Model to Drift Them All Source

> Source: `raw/pdfs/Djoimou_One_Model_to_Drift_Them_Al.pdf`
> Paper: One Model to Drift Them All: Physics-Informed Conditional Diffusion Model for Driving at the Limits, CoRL 2024 / PMLR 2025

## Summary

This paper studies a hard version of autonomous vehicle control: reliable driving at the limits of handling, where tire forces saturate and the same controller must keep working across different cars, tires, and road conditions.

For this vault, the paper matters because it pushes autonomous drifting away from single-vehicle expert tuning and toward a more general adaptation story. Instead of learning one controller per setup, it learns a single conditional diffusion model that can adapt online inside an MPC loop.

## Method

The core idea is to learn a conditional diffusion model over the parameters of a physics-informed, data-driven vehicle-dynamics model using an unlabeled multimodal trajectory dataset.

That design choice is important for two reasons:

- it treats the variation across vehicles and environments as a multimodal modeling problem rather than noise to be averaged away,
- and it keeps the learned model tied to a structured dynamics representation that can be used inside real-time [[model_predictive_control]].

At deployment time, online measurements condition the generation process so the controller can adapt on the fly to the current vehicle and surface conditions.

## Evaluation

The paper reports experiments on a Toyota Supra and a Lexus LC 500, including different tires and varying road conditions.

For this vault, the headline result is not only that the system can drift aggressively, but that one shared model can match specialized expert models while generalizing better to unseen conditions.

## Notes / Critique

The strongest contribution is the shift in framing. Much of classic autonomous drifting is about designing or tuning a controller for one vehicle near one operating envelope. This paper instead treats at-limit control as an online adaptation problem over a family of latent dynamics regimes.

It also sits at a useful intersection of [[autonomous_drifting]], [[model_predictive_control]], and learned vehicle modeling. The paper is not end-to-end in the usual direct-policy sense; it is a structured learned model embedded inside a real-time controller.

## Pages Created From This Source

- [[one_model_to_drift_them_all_physics_informed_conditional_diffusion_model_for_driving_at_the_limits]]
- [[autonomous_drifting]]
