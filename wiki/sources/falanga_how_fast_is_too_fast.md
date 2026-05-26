---
tags: [source]
date: 2026-05-26
sources: 1
---

# Falanga How Fast Is Too Fast Source

> Source: `raw/pdfs/Falanga_How_fast_is_too_fast.pdf`
> Paper: How Fast Is Too Fast? The Role of Perception Latency in High-Speed Sense and Avoid, IEEE Robotics and Automation Letters 2019

## Summary

This paper asks a simple but important question for high-speed aerial autonomy: when does perception latency itself become the limiting factor on safe speed?

For this vault, that matters because many fast-autonomy papers focus on control, learning, or planning, while this one makes the sensing bottleneck explicit. It argues that maximum safe speed is constrained not only by dynamics and actuation, but also by how quickly the perception stack can detect and react to obstacles.

## Method

The paper analyzes the relationship among sensing latency, sensing range, and achievable safe velocity in high-speed sense-and-avoid settings.

Its emphasis is not a full racing stack, but the physical consequences of delayed perception. The PDF traces clearly show analyses around maximum latency, maximum velocity, monocular and stereo sensing range, and event-camera latency, which is exactly the kind of systems-level framing this vault needs in the drone and high-speed-perception branches.

## Evaluation

The main contribution appears to be analytical and comparative rather than benchmark-driven in the style of a race result.

For the vault, the key significance is conceptual: the paper helps explain why some high-speed aerial systems need better sensing, lower-latency perception, or longer-range observation before any controller can safely exploit the remaining dynamics margin.

## Notes / Critique

The strongest value of this paper is that it turns a vague intuition into a clearer design constraint. "Faster" is not only about thrust, policy quality, or optimizer speed; it is also about whether the system sees far enough ahead and quickly enough to avoid what it is about to hit.

This source belongs naturally near [[autonomous_drone_racing]], [[high_speed_perception]], and [[Highly_dynamic_autonomous_system]].

## Pages Created From This Source

- [[how_fast_is_too_fast_the_role_of_perception_latency_in_high]]
