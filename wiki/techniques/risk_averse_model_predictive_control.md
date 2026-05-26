---
tags: [technique]
date: 2026-05-13
sources: 1
---

# Risk-Averse Model Predictive Control

## Definition

Risk-averse model predictive control is an MPC formulation that optimizes future actions while explicitly accounting for uncertainty and tail risk, rather than planning only for a single nominal model or average-case outcome.

## Key Approach

[[risk_averse_model_predictive_control_for_racing_in_adverse_conditions]] applies this idea to autonomous racing under uncertain friction limits and tire parameters.

The core move is to use a sample-based uncertainty-aware optimal control formulation with a conditional value at risk (`CVaR`) constraint. Instead of assuming one best vehicle model, the controller plans over several plausible dynamics models and penalizes outcomes that become dangerous in the worse part of that distribution.

That makes the technique attractive when a nominal racing controller may become too optimistic under changing surface conditions, partial model mismatch, or persistent low-friction regimes.

## Relationship to Racing Control

This technique belongs near [[model_predictive_control]], [[autonomous_racing_control]], and the broader problem of robust high-performance autonomy.

Compared with classical MPC, it trades some nominal aggressiveness for better protection against rare but consequential loss-of-control events.

Compared with learned adaptation methods, it addresses a different layer of the problem: not how to infer the dynamics better, but how to make better decisions when uncertainty remains.

## Representative Papers

- [[risk_averse_model_predictive_control_for_racing_in_adverse_conditions]]

## Open Problems

Open problems include balancing lap-time loss against robustness, scaling risk-aware formulations to richer multi-agent racing settings, choosing uncertainty sets that remain realistic online, and understanding when risk aversion should yield to opportunistic aggression during competition.
