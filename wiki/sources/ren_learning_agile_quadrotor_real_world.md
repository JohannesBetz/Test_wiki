---
tags: [source]
date: 2026-05-27
sources: 1
---

# Ren Learning Agile Quadrotor Real World Source

> Source: `raw/pdfs/Ren_Learning_Agile_Flight_In-Real_world.pdf`
> Paper: Learning Agile Quadrotor Flight in the Real World, arXiv, 2026

## Summary

This paper presents a self-adaptive quadrotor flight framework that learns agile behavior directly on real hardware. Instead of requiring a carefully identified model or an offline sim-to-real pipeline, the method updates the policy online during actual flight using residual dynamics learning and differentiable simulation.

For this vault, the key significance is that it strengthens the `real-world adaptation under aggressive dynamics` branch of autonomous drone racing.

## Core Contribution

The paper's contribution is not just that the drone flies fast. It is that adaptation happens on the real platform itself through:

- online residual learning of unmodeled disturbances,
- adaptive temporal scaling to explore limits safely,
- and RASH-BPTT for short-horizon in-flight policy updates.

That makes it a strong counterpart to simulation-heavy or model-free-only approaches in the vault.

## Why It Matters Here

This source sharpens a useful distinction inside the drone-racing branch:

- some systems rely on strong simulation and transfer,
- some rely on explicit estimation and control structure,
- and this one pushes further toward direct real-world adaptation.

It therefore belongs naturally near [[learning_agile_quadrotor_flight_in_the_real_world]], [[differentiable_simulation]], [[autonomous_drone_racing]], and [[real_world_robotic_reinforcement_learning]].

## Notes / Critique

The most interesting part is not only agility, but sample-efficient adaptation under real hardware constraints. That is one of the hardest things to do well in aggressive robotics.

Its likely limitation is that online adaptation still depends on a learned hybrid model staying stable enough during the very process of pushing toward the dynamic limit.

## Pages Created From This Source

- [[learning_agile_quadrotor_flight_in_the_real_world]]
