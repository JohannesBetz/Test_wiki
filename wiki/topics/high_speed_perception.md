---
tags: [topic]
date: 2026-05-06
sources: 5
---

# High Speed Perception

## Definition

High-speed perception covers mapping, localization, object detection, free-space detection, and state estimation when an autonomous system moves fast enough that sensing range, latency, motion blur, synchronization, and sparse landmarks directly constrain safety and performance.

## Key Approaches

In [[autonomous_vehicles_on_the_edge]], autonomous racing perception includes:

- SLAM and mapping, including LiDAR-based racetrack mapping.
- Localization with AMCL, EKF, GraphSLAM, NDT, Kalman filters, LiDAR, odometry, GPS, and vehicle sensors.
- Cone/object detection for [[formula_student_driverless]] using camera-based deep detectors such as YOLO variants and SSD MobileNet.
- Free-space detection with semantic segmentation.
- LiDAR distortion compensation for high-speed operation.

In [[champion_level_drone_racing_using_deep_reinforcement_learning]], high-speed perception appears in an aerial setting: [[visual_inertial_odometry]] drifts under aggressive flight and motion blur, so gate detections are used as landmarks and fused with VIO through a Kalman filter.

In [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]], high-speed perception appears in table tennis: APS cameras localize a fast ball in 3D, while [[event_based_vision]] estimates spin at low latency for high-speed, high-spin returns.

In [[a_champion_level_vision_based_reinforcement_learning_agent_for_competitive_racing_in_gran_turismo_7]], high-speed perception is folded directly into a learned racing policy: egocentric camera input and onboard sensors must support competitive multi-agent driving without explicit global localization at inference time.

In [[safety_assured_high_speed_navigation_for_mavs]], high-speed perception appears in a different aerial form: long-range 3D LIDAR is used not only for obstacle detection but also to distinguish known free space directly on point clouds, which is what makes [[safety_assured_high_speed_aerial_navigation]] practical at speeds above 20 m/s.

[[autonomous_drone_racing_a_survey]] broadens the aerial perspective by showing how camera models, IMU calibration, motion blur, dynamic range, and sensor placement interact with planning and control at racing speeds, not only with perception in isolation.

[[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]] adds a multimodal variant: FPV perception is no longer only an input to explicit estimation modules, but part of a [[vision_language_action_models|language-conditioned policy]] that must convert visual context into control under tight timing constraints.

[[vision_augmented_on_track_system_identification_for_autonomous_racing_via_attention_based_priors_and_iterative_neural_correction]] adds a different perception-to-control link: vision may matter not only for localization or obstacle awareness, but also for shaping the prior used in racing-relevant system identification.

[[race_against_the_machine_a_fully_annotated_open_design_dataset_of_autonomous_and_piloted_high_speed_flight]] adds a data-resource perspective: high-speed perception research also needs open annotated flight data that make aggressive aerial sensing failures and success cases measurable in a reproducible way.

[[how_fast_is_too_fast_the_role_of_perception_latency_in_high]] adds a harder systems-limit perspective: in fast flight, perception does not merely support control quality, it directly limits how fast a vehicle can safely move before sensing delay and sensing range make avoidance physically implausible.

[[evaluation_of_driver_reaction_time]] adds a human-factors counterpart: even in non-autonomous driving, the perception-to-action delay of the driver is itself a critical safety bottleneck, which helps explain why raw human reaction cannot be the only model for high-speed autonomous response.

[[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]] adds a legged-robotics perspective: high-speed perception is not only about detecting distant objects for cars and drones, but also about deciding whether terrain observations are reliable enough to change foot placement and body motion before contact.

[[perceptive_locomotion_through_nonlinear_model_predictive_control]] adds a control-embedded legged perspective: high-speed perception can also matter by changing the feasible set of a real-time optimizer through terrain-aware constraints, not only by feeding a learned policy.

[[legged_locomotion_in_challenging_terrains_using_egocentric_vision]] adds a compact egocentric-vision legged perspective: high-speed perception in embodied systems can also be intensely local, where the issue is not long-range sensing but whether onboard visual context is sufficient to shape the next few body motions on rough ground.

[[learning_visual_parkour_from_generated_images]] adds a generated-visual-data legged perspective: high-speed perception can also bottleneck on whether the training world is visually rich enough for RGB-only transfer, not only on the runtime sensor stack.

[[hiking_in_the_wild_a_scalable_perceptive_parkour_framework_for_humanoids]] adds a depth-driven humanoid perspective: high-speed perception in embodied systems can also mean whether raw depth input is stable and actionable enough for foothold-safe whole-body control in unstructured outdoor terrain.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[champion_level_drone_racing_using_deep_reinforcement_learning]]
- [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]
- [[a_champion_level_vision_based_reinforcement_learning_agent_for_competitive_racing_in_gran_turismo_7]]
- [[safety_assured_high_speed_navigation_for_mavs]]
- [[autonomous_drone_racing_a_survey]]
- [[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]]
- [[race_against_the_machine_a_fully_annotated_open_design_dataset_of_autonomous_and_piloted_high_speed_flight]]
- [[how_fast_is_too_fast_the_role_of_perception_latency_in_high]]
- [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]]
- [[perceptive_locomotion_through_nonlinear_model_predictive_control]]
- [[legged_locomotion_in_challenging_terrains_using_egocentric_vision]]
- [[learning_visual_parkour_from_generated_images]]
- [[hiking_in_the_wild_a_scalable_perceptive_parkour_framework_for_humanoids]]

## Open Problems

The survey argues that racing-specific high-speed perception remains thin. Open issues include long-range detection beyond 100 m, motion blur, sensor synchronization, robust camera/radar/LiDAR fusion, sparse racetrack landmarks, and lack of public high-speed racing perception datasets.

Swift adds an appearance-generalization caution: a perception stack can be fast enough for champion-level racing but still brittle when illumination or visual conditions differ from training.

Vision-based GT7 racing adds an occlusion-memory challenge: perception may be local and incomplete, so competitive behavior depends on remembering track and opponent context rather than only reading the current frame.

SUPER adds a long-range obstacle-resolution challenge: at high speed, even small objects such as wires become mission-critical, so perception systems need both sufficient range and enough spatial fidelity to keep safety guarantees meaningful.

The ADR survey adds a sensor-stack realism challenge: high-speed flight pushes not just algorithms but the calibration, latency, and physical placement of sensors, so perception quality can degrade for reasons that are partly hardware and partly algorithmic.

RaceVLA adds a grounding challenge: once perception is folded into a large multimodal action model, it becomes harder to separate whether failures come from sensing, language conditioning, latent world modeling, or action decoding.

The Race Against the Machine dataset adds an evaluation challenge: without sufficiently open and well-annotated aggressive-flight datasets, it is hard to know whether a perception system is genuinely robust or simply tuned to one private experimental setup.

How Fast Is Too Fast adds a latency-budget challenge: even a strong controller may be irrelevant if sensing delay and sensing range together leave too little time for avoidance at the target speed.

Perceptive quadruped locomotion adds a reliability-allocation challenge: when sensing fails intermittently, should a fast embodied system slow down, trust learned fusion, or fall back to proprioceptive control until perception becomes usable again?

Perceptive NMPC adds an optimizer-interface challenge: if perception is turned into constraints, how coarse can those constraints become before the controller remains fast but stops respecting the real terrain?

Egocentric-vision locomotion adds a compactness challenge: if one wants perception to stay lightweight enough for small embodied systems, how much terrain structure can be omitted before locomotion robustness starts to fail?

Visual parkour from generated images adds a realism-generation challenge: if RGB-only transfer depends on generated imagery, what visual inaccuracies are harmless and what inaccuracies quietly poison real-world deployment?

Hiking in the Wild adds a depth-stability challenge: if raw depth drives the policy directly, how sensitive is the whole control loop to viewpoint jitter, partial observations, and terrain-edge ambiguity in the wild?
