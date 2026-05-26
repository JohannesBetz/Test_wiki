---
tags: [paper]
date: 2026-05-08
task: autonomous_racing
venue: "arXiv"
sources: 1
year: "2025"
eprint: "2504.11717"
url: "https://arxiv.org/abs/2504.11717"
topic:
  - autonomous_racing
  - shared_autonomy
  - autonomous_racing_control
tech_backbone: []
tech_representation: []
tech_generation: [human_centered_safety_filter]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [drones]
simulators_used: []
---

# Safety with Agency: Human-Centered Safety Filter with Application to AI-Assisted Motorsports

> Safety with Agency: Human-Centered Safety Filter with Application to AI-Assisted Motorsports | arXiv:2504.11717 | Donggeon David Oh, Justin Lidard, Haimin Hu, Himani Sinhmar, Elle Lazarski, Deepak Gopinath, Emily S. Sumner, Jonathan A. DeCastro, Guy Rosman, Naomi Ehrich Leonard, and Jaime Fernandez Fisac

## Summary

This paper asks how an AI co-pilot should assist a human driver in a safety-critical racing setting. The authors argue that conventional safety filters often protect the system at the cost of the driver's agency, comfort, and trust, because they intervene abruptly and without preserving the human's strategic intent.

Their answer is a shared-autonomy safety filter that tries to keep the driver in the loop while still enforcing strong safety guarantees.

## Method

The core technique is the [[human_centered_safety_filter]].

The method first learns a neural safety value function from black-box interaction data. That learned value function is then used to enforce a novel state-action control barrier constraint, which the paper calls a `Q-CBF`. The important engineering claim is that both learning and deployment avoid requiring an explicit analytical model of system dynamics.

This matters because high-performance racing simulators and real vehicles are often effectively black boxes at the level needed for shared-autonomy safety intervention.

A second key choice is intervention style. Rather than issuing abrupt last-resort corrections, the filter is designed to modify human control inputs minimally and smoothly, so the driver remains comfortable and aware of the AI assistant's intent.

## Key Results

The paper evaluates the method in Assetto Corsa under high-speed edge-driving conditions and compares three settings: no assistance, a conventional safety filter, and the proposed HCSF.

The abstract reports two main findings. First, relative to no assistance, HCSF improves both safety and user satisfaction without compromising agency or comfort. Second, relative to a conventional safety filter, HCSF improves agency, comfort, and satisfaction while maintaining at least the same robustness.

The experimental setup is also notable: the paper includes an in-person user study with 83 human participants. That makes the work stronger on human-factors evidence than many racing-safety papers, which usually stop at simulated trajectory metrics alone.

## Hardware Used

- [[drones]]


## Related Work

This paper is closely related to the racing interaction and safety literature already touching the vault. It complements [[think_deep_and_fast_learning_neural_nonlinear_opinion_dynamics_from_inverse_dynamic_games_for_split_second_interactions]] by focusing not on autonomous tactical decision making alone, but on how an AI assistant should intervene on behalf of a human.

It also pairs naturally with motorsports works such as [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]] and [[champion_level_drone_racing_using_deep_reinforcement_learning]], which expose the safety-performance tension, but do not directly address preserving human agency under assistance.

At the control-method level, the paper sits near modern control-barrier-function safety work, but pushes those ideas into a black-box shared-autonomy setting.

## Notes / Critique

The strongest contribution is the reframing of safety as a human-centered design problem rather than a pure constraint-enforcement problem. In racing, that distinction really matters: a safe assistant that ruins the driver's feel and tactical intent is not an acceptable copilot.

The main limitation is transfer. Even with a strong simulator and a real user study, the jump from Assetto Corsa to physical AI-assisted motorsports remains nontrivial because latency, actuation limits, and human trust calibration all become harsher outside simulation.
