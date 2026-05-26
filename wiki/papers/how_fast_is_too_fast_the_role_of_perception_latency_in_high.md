---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "IEEE Robotics and Automation Letters 2019"
sources: 2
bibtex_key: "Falanga2019"
bibtex_type: "article"
year: "2019"
doi: "10.1109/lra.2019.2898117"
url: "https://doi.org/10.1109/lra.2019.2898117"
topic:
  - autonomous_drone_racing
  - high_speed_perception
  - Highly_dynamic_autonomous_system
tech_backbone: []
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [drones]
simulators_used: []
---

# How Fast Is Too Fast? The Role of Perception Latency in High-Speed Sense and Avoid

> How Fast Is Too Fast? The Role of Perception Latency in High-Speed Sense and Avoid | IEEE Robotics and Automation Letters 2019 | Davide Falanga, Suseong Kim, and Davide Scaramuzza

## Summary

This paper studies a core limit in aggressive aerial autonomy: how perception latency constrains the safe speed of a vehicle performing sense-and-avoid behavior.

For this vault, the paper matters because it makes a systems-level point that cuts across drone racing and other highly dynamic robots: speed is not only a control problem. If perception is too slow or sensing range is too short, the dynamic envelope collapses before the controller even gets a fair chance.

## Method

The paper analyzes the coupling among perception latency, sensing range, and maximum safe velocity in high-speed obstacle avoidance.

The PDF traces make the structure fairly clear even though the local text layer is weak: the authors compare maximum latency and maximum velocity relationships, discuss monocular and stereo sensing range, and examine event-camera latency as an alternative operating point.

That framing is especially useful for this vault because it sits one level below typical racing claims. Rather than asking whether a full stack is fast, the paper asks what sensing assumptions must be true before high-speed avoidance is physically plausible at all.

## Key Results

The main result is conceptual and design-oriented: safe high-speed flight depends directly on the latency and range of the perception system.

That makes the paper a strong complement to performance papers such as [[champion_level_drone_racing_using_deep_reinforcement_learning]] and [[safety_assured_high_speed_navigation_for_mavs]]. Those papers show what fast aerial systems can do; this paper helps explain what their sensing stack must overcome to make that speed sustainable.

It also pairs well with [[race_against_the_machine_a_fully_annotated_open_design_dataset_of_autonomous_and_piloted_high_speed_flight]], because both papers care about aggressive flight realism, but from different angles: one from the limits imposed by sensing latency, the other from open data for measuring aggressive flight.

## Datasets Used

No dataset is the central contribution on the current page. The paper is better understood as an analysis of sensing and flight constraints than as a benchmark-resource paper.

## Hardware Used

- [[drones]]

## Funding / Grants

- Supported by the European Research Council (ERC) Consolidator Grant [[agileflight]].

## Related Work

This paper belongs naturally near [[autonomous_drone_racing]], [[high_speed_perception]], and [[Highly_dynamic_autonomous_system]].

It is also a useful bridge to [[event_based_vision]] and to the drone branch more broadly, because one obvious route to pushing the speed ceiling is reducing sensing latency rather than only improving planning or control.

## Notes / Critique

The strongest contribution is clarity. High-speed autonomy papers often imply that faster perception is better, but this paper foregrounds the harder systems question: how much latency is still tolerable before collision avoidance becomes physically unrealistic?

The main limitation in this vault is that the local PDF text layer is weak, so the current note is written as a careful method-level placement rather than a full experimental deep read. Even so, the core role of the paper is clear: it gives the aerial branch a direct argument that perception latency is part of the speed limit itself.
