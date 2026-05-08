---
tags: [technique]
date: 2026-05-08
sources: 1
---

# Dynamic Near-Potential Functions

## Definition

Dynamic near-potential functions are a game-theoretic approximation tool for multi-agent sequential decision problems. They are designed so that when one agent changes its policy unilaterally, the resulting change in its long-horizon value is closely matched by the change in a shared scalar potential-like function.

In autonomous racing, this is useful because it turns approximate Nash-equilibrium search into repeated maximization of one learned function instead of repeated solution of a full dynamic game online.

## Key Approach

[[alpha_racer_real_time_algorithm_for_game_theoretic_motion_planning_and_control_in_autonomous_racing_using_near_potential_function]] uses this idea in two phases:

- offline, it learns a neural near-potential function from simulated multi-car races;
- online, it maximizes that learned function at the current state to select maneuver parameters for an MPC-based racing policy.

The practical effect is that long-horizon competitive interaction is compressed into a tractable online optimization.

## Relationship to Racing Planning

This technique belongs primarily inside [[autonomous_racing_planning]], especially multi-agent behavioral planning, but it also depends on [[model_predictive_control]] because the selected maneuver parameters are executed through an MPC tracker.

Compared with direct receding-horizon game solvers, it moves more computation offline. Compared with self-play RL, it keeps a more explicit equilibrium-based interpretation of why the agent chooses to overtake, block, or preserve position.

## Representative Papers

- [[alpha_racer_real_time_algorithm_for_game_theoretic_motion_planning_and_control_in_autonomous_racing_using_near_potential_function]]

## Open Problems

Open problems include learning accurate near-potential functions under richer traffic patterns, extending the approximation to larger numbers of agents and more diverse maneuver spaces, and understanding how sensitive performance is to the chosen low-dimensional policy parametrization.
