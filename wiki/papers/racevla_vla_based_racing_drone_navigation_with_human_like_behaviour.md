---
tags: [paper]
date: 2026-05-08
task: robotics
venue: "arXiv"
sources: 1
year: "2025"
topic:
  - autonomous_drone_racing
  - end_to_end_autonomous_racing
  - foundation_models_for_intelligent_decision_making
tech_backbone: []
tech_representation: [vision_language_action_models]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: [racevla]
simulators_used: []
---

# RaceVLA: VLA-based Racing Drone Navigation with Human-like Behaviour

> RaceVLA: VLA-based Racing Drone Navigation with Human-like Behaviour | arXiv 2025 | Valerii Serpiva, Artem Lykov, Artyom Myshlyaev, Muhammad Haris Khan, Ali Alridha Abdulkarim, Oleg Sautenkov, and Dzmitry Tsetserukou

## Summary

This paper proposes a racing-drone control system built around the vision-language-action paradigm. The central idea is that a pretrained multimodal model can be specialized to racing so that FPV visual input and natural-language commands jointly condition direct flight behavior.

That makes the paper unusual inside this vault. Instead of starting from classical planning and control, or from reinforcement learning alone, it starts from a broader pretrained action model and asks whether it can be made useful for agile embodied flight.

## Method

The system, [[racevla]], is built by fine-tuning an OpenVLA-style model for racing-drone navigation.

The paper frames the input-output structure as:

- FPV video observations,
- language prompts describing the intended behavior,
- and action prediction for drone motion commands.

The action space includes translational velocity and yaw-rate outputs, which makes the system closer to direct control than to waypoint prediction.

Training uses a racing-specific dataset and LoRA-style adaptation of the pretrained VLA backbone. Deployment uses a custom racing-drone platform with external compute support for model inference.

## Key Results

The paper reports that RaceVLA outperforms generic VLA baselines such as OpenVLA and RT-2 on several racing-relevant evaluation axes.

The main qualitative result is specialization: a VLA trained for general robotic behavior is not enough on its own, but a racing-specific fine-tuning pass produces much stronger motion and semantic generalization in a drone-racing setting.

The manuscript also reports real-flight capability with average speed around 1.04 m/s and peak speed around 2.02 m/s. Those speeds are far below elite FPV racing, but they are still meaningful as an early embodied demonstration of VLA-style control in a domain with sharp dynamics and narrow margins.

## Related Work

For this vault, the closest contrast is [[champion_level_drone_racing_using_deep_reinforcement_learning]]. Swift uses a much more specialized stack with explicit state estimation and a learned low-level policy, while RaceVLA explores whether broader multimodal pretrained priors can absorb more of the behavior directly.

The paper also belongs near [[end_to_end_autonomous_racing]], because it is a strong example of replacing intermediate stack structure with a learned sensor-to-action mapping.

It is equally relevant to [[foundation_models_for_intelligent_decision_making]], since it shows one concrete path by which foundation-model ideas might enter embodied high-speed autonomy rather than staying at the level of abstract decision support.

## Notes / Critique

The strongest contribution is conceptual reach. The paper asks a genuinely different question from most drone-racing work: not only how to make a policy faster, but whether a language-conditioned pretrained action model can become a usable agile-flight controller at all.

The clearest limitation is performance realism. Inference at about 4 Hz with server-side assistance leaves a large gap to the reaction rates and onboard autonomy standards that matter for actual competitive racing. So the result is more of a promising early bridge between VLA robotics and racing than a state-of-the-art racing system.
