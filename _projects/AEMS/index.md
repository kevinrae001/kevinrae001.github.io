---
layout: post
title: "Autonomous Monitoring & Surveillance Unit"
description: "Autonomous, self-contained station that uses drones, cameras, and sensors to monitor remote airstrips."
skills:
  - SolidWorks
  - ASME Y14 drawings
  - GD&T ASME Y14.5
  - DFM/DFA
  - Structural analysis
  - FEA
  - Mechanism design
  - Kinematics
  - Prototyping
  - Field-test support
main-image: /AEMS03.jpg
---

{% assign project_folder = page.path | split: "/" | slice: 0, 2 | join: "/" %}
{% assign img = "/" | append: project_folder | append: "/" %}

![AEMS deployed in snow]({{ img }}AEMS03.jpg)

## My role (NDA)

I was the lead mechanical engineer on this project. Because of an NDA, I’m limited in how much I can share publicly, but my scope included:

- Turning stakeholder requirements into mechanical architectures and manufacturable designs
- Owning the SolidWorks models for assemblies/parts
- Producing engineering drawings to ASME Y14 standards (including GD&T where appropriate)
- Supporting prototype builds, field testing, and iterative design improvements

## System overview

The station is designed to operate unattended in remote locations and run 24/7 year-round. It houses cameras, drones, and sensors for continuous monitoring, and is powered primarily by solar with a backup diesel generator.

{% include youtube-video.html id="XpqmTLX5Jws" autoplay= "false"%}

Key constraints and design drivers:

- **Cold weather operation:** down to -40°C
- **Energy-limited environment:** minimize steady-state loads and avoid wasting energy on actuation
- **Weatherproofing:** precipitation, freeze/thaw cycles, wind-driven snow/rain, and ingress protection
- **Serviceability:** field access for maintenance, repairs, and component replacement

![AEMS in the field (solar array deployed)]({{ img }}AEMS04.jpg)

## Mechanical highlights (high-level)

### Solar tracking mast + array

- Custom 3-stage telescoping mast (extends to roughly 2x stowed height)
- Supports a ~1.8 kW solar array with high wind survivability (tested in 80 km/h winds)
- Enables 360° rotation and high tilt range (up to ~80°) to support sun tracking
- Structural checks performed on the mast, array, supporting structures, and all interfaces

### Doors, access panels, and mechanisms

- Mechanism sizing and kinematic checks for major moving subsystems
- Designed for reliable motion without fighting gravity whenever possible
- Considered alignment tolerance, icing risk, and repeatability in field conditions

### Weatherproofing strategy

- Applied “automotive-style” sealing concepts where relevant:
  - Overlapping joints to reduce direct ingress
  - Controlled drainage paths for water management
  - Seal placement selected to reduce snow/ice packing at critical interfaces
- Side-wall geometry and interfaces required multiple iterations to balance manufacturability, stiffness, and sealing

## Analysis and validation work

At a high level, I supported validation with simulation-driven checks, including:

- FEA on key structures (walls, array, mast support structure, skid, frame) to verify safety factors under expected loads
- Thermal/heat-retention considerations to reduce generator runtime and improve winter performance

## Prototyping and iteration

We built smaller prototypes for risk reduction and then progressed to full-scale prototype work. Iterations focused on:

- Side-wall manufacturability and stiffness
- Sealing performance and water management
- Assembly sequence and service access
- Tolerance realities in fabrication

![Close-up of station exterior + integrated hardware]({{ img }}AEMS01.jpg)

---

## Photo gallery

![AEMS in snow]({{ img }}AEMS03.jpg)
![AEMS in the field (solar array deployed)]({{ img }}AEMS04.jpg)
![AEMS deployed in snow]({{ img }}AEMS02.jpg)
![Close-up of station exterior + integrated hardware]({{ img }}AEMS01.jpg)
