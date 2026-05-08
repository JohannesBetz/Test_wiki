---
tags: [technique]
date: 2026-05-08
sources: 1
---

# Human-Centered Safety Filter

## Definition

A human-centered safety filter is a shared-autonomy control layer that intervenes on a human operator's actions only as much as needed to preserve safety, while also trying to preserve agency, comfort, and trust.

In motorsports, this means helping the driver stay safe near the handling limit without flattening the driver's strategic intent or racing feel.

## Key Approach

[[safety_with_agency_human_centered_safety_filter_with_application_to_ai_assisted_motorsports]] implements this idea with two components:

- a learned neural safety value function from black-box interaction data,
- and a state-action control barrier constraint (`Q-CBF`) that uses that value function to monitor and correct actions at deployment time.

The paper's distinctive contribution is not just the safety constraint itself, but the emphasis on smooth, minimal intervention.

## Relationship to Autonomous Racing

This technique belongs near [[autonomous_racing_control]] and the broader human-in-the-loop side of [[autonomous_vehicle_racing]].

Compared with purely autonomous racing controllers, it addresses a different question: not how the car should drive by itself, but how an AI assistant should shape a human's actions under severe safety pressure.

## Representative Papers

- [[safety_with_agency_human_centered_safety_filter_with_application_to_ai_assisted_motorsports]]

## Open Problems

Open problems include transfer to physical racecars, better calibration of human trust and intervention transparency, and handling settings where comfort, agency, and safety may temporarily come into tension.
