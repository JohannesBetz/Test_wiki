---
tags: [source]
date: 2026-05-08
sources: 1
---

# Donggeon Safety with Agency Source

> Source: `raw/pdfs/Donggeon_Safety_with_Agency.pdf`
> Paper: Safety with Agency: Human-Centered Safety Filter with Application to AI-Assisted Motorsports, arXiv:2504.11717

## Summary

This paper studies shared autonomy in high-performance driving, asking how an AI co-pilot can improve safety without stripping the human driver of agency, comfort, or competitive edge. The central claim is that many conventional safety filters intervene too abruptly and too late, which keeps the system safe but makes the human feel overridden.

The paper proposes a human-centered safety filter that tries to preserve the driver's intent while still enforcing robust safety constraints in a black-box motorsports environment.

## Method

The method introduces a `Human-Centered Safety Filter` (`HCSF`) built on a learned neural safety value function. That value function is first learned through black-box interaction, then used at deployment to enforce a novel state-action control-barrier-function constraint, called `Q-CBF`.

The key design choice is that both synthesis and runtime deployment are model free with respect to system dynamics. This makes the approach usable for complex shared-autonomy systems where accurate analytical models are hard to obtain.

The paper also emphasizes that the filter modifies human inputs minimally and smoothly, aiming to avoid the abrupt last-moment corrections common in many last-resort safety filters.

## Evaluation

The evaluation is unusually strong for this part of the literature. The paper validates the method in Assetto Corsa, a high-fidelity racing simulator with black-box vehicle dynamics, and runs an in-person user study with 83 participants across diverse skill levels.

The main results reported in the abstract are:

- Compared with no assistance, HCSF improves both safety and user satisfaction without compromising human agency or comfort.
- Compared with a conventional safety filter, HCSF improves agency, comfort, and satisfaction while maintaining at least the same robustness, and sometimes exceeding it.

## Notes / Critique

The strongest contribution is the explicit shift from safety alone to safety plus human agency. That makes the paper especially relevant for AI-assisted motorsports rather than only autonomous racing.

Its main limitation is that it is still simulator based, even if the simulator is strong and the user study is substantial. The open question is how much of the same smooth-intervention behavior survives on a physical racecar with real sensing, latency, and vehicle uncertainty.

## Pages Created From This Source

- [[safety_with_agency_human_centered_safety_filter_with_application_to_ai_assisted_motorsports]]
- [[human_centered_safety_filter]]
