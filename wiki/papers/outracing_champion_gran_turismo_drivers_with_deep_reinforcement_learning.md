---
tags: [paper]
date: 2026-05-07
task: autonomous_racing
venue: "Nature 2022"
sources: 1
year: "2022"
topic:
  - autonomous_racing
  - reinforcement_learning
  - multi_agent_racing
  - racing_etiquette
  - end_to_end_learning
tech_backbone: []
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: [gt_sophy]
hardware_used: [drones]
simulators_used: [gran_turismo_sport]
doi: "10.1038/s41586-021-04357-7"
---

# Outracing Champion Gran Turismo Drivers With Deep Reinforcement Learning (2022)

> Outracing champion Gran Turismo drivers with deep reinforcement learning | Nature 2022 | Wurman et al.

## Summary

This paper presents [[gt_sophy]], a deep reinforcement learning racing agent for [[gran_turismo_sport]] that defeated top human Gran Turismo drivers. The work frames racing as a combination of four skills: race-car control, racing tactics, [[racing_etiquette]], and racing strategy.

GT Sophy achieved superhuman time-trial performance and, after an initial loss in July 2021, won an October 2021 four-versus-four team rematch against top human players by a score of 104-52.

## Method

GT Sophy uses model-free off-policy deep [[reinforcement_learning]], specifically [[quantile_regression_soft_actor_critic]]. It outputs continuous throttle/brake and steering actions at 10 Hz. The policy observes vehicle state, track geometry, and nearby opponent state through the Gran Turismo Sport API.

The track is represented by upcoming left-edge, centerline, and right-edge course points in the agent's egocentric frame. Opponents are represented in front and rear lists ordered by distance. Racing features include collision flags and a slipstream indicator.

Training combines several ingredients:

- Progress reward for fast lap advancement.
- Passing reward for gaining position relative to nearby opponents.
- Off-course, wall, tyre-slip, collision, rear-end, and unsporting-collision penalties.
- [[mixed_scenario_training]] across full-track races and specialized situations such as grid starts, slipstream passing, and difficult chicanes.
- Mixed opponent populations, including previous agents and built-in AI, rather than pure self-play.
- Multi-table stratified sampling so rare but important skills do not disappear from the replay buffer.
- Human-reviewed policy selection balancing speed, team score, collisions, and sportsmanship.

## Key Results

GT Sophy reached superhuman time-trial performance on all three evaluated car-track combinations: Dragon Trail Seaside, Lago Maggiore GP, and Circuit de la Sarthe. In the July 2021 time-trial event, it beat Emily Jones, Valerio Gallo, and Igor Fraga.

In the July 2021 head-to-head team race, human drivers beat GT Sophy 86-70. The authors then improved training, network size, rewards, features, and opponent populations. In the October 2021 rematch, GT Sophy won 104-52.

The agent learned tactical behaviors including contextual corner passing, slipstream use, draft disruption, blocking, and emergency maneuvers. The paper emphasizes that these were not hand-coded maneuvers; they emerged from scenario exposure and reward design.

## Datasets Used

The paper reports no static dataset. Training data are generated from scratch during learning. Race videos are available through the public GT Sophy project page.

## Hardware Used

- [[drones]]


## Related Work

This paper extends the racing-RL line represented by [[super_human_performance_in_gran_turismo_sport_using_deep_reinforcement_learning]] and [[autonomous_overtaking_in_gran_turismo_sport_using_curriculum_reinforcement_learning]]. It also addresses open challenges from [[autonomous_vehicles_on_the_edge]], especially multi-vehicle interaction, adversarial driving, and balancing safety/performance.

Compared with [[champion_level_drone_racing_using_deep_reinforcement_learning]], GT Sophy operates in simulation rather than on a physical robot, but it tackles richer multi-agent racing and explicit human-norm constraints.

## Notes / Critique

GT Sophy is strongest as a demonstration of integrated tactical racing under imprecise human norms. Its reward engineering and scenario design matter as much as the RL algorithm.

The main limitation is strategy. GT Sophy could pass, block, and exploit slipstream, but still lacked long-horizon race judgment, such as waiting for an opponent with a pending penalty or avoiding passes that immediately allow a slipstream counterattack.

The fairness comparison is nuanced. GT Sophy had exact track and opponent state, equal rear/front observability, and low reaction latency. Human drivers had smoother 60 Hz control, visual context, gear shifting, traction control, and richer interpretation of racing situations.
