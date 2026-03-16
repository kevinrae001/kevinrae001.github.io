---
layout: post
title: "Vacuum Distillation Unit"
description: >
  Designed and built a vacuum distillation unit (kettle + column + condenser/receiver loop) to separate
  temperature-sensitive liquids under reduced pressure—taking the system from process sizing through
  mechanical design, fabrication support, and commissioning.
skills:
  - Mechanical design
  - SolidWorks
  - Mass & energy balances
  - Distillation theory (Fenske)
  - Fabrication support for welding and assembly
  - Test & commissioning
  - MATLAB
main-image: /banner.jpg
---

{% assign project_folder = page.path | split: "/" | slice: 0, 2 | join: "/" %}
{% assign img = "/" | append: project_folder | append: "/" | relative_url %}

## Summary
This project involved designing a general-purpose vacuum distillation system intended to lower boiling temperatures and protect product quality by operating under reduced pressure. I owned the end-to-end mechanical design, supported fabrication and assembly, and brought the unit through commissioning in a working industrial environment.

**Core outcomes**
- Reduced boiling temperature using a vacuum to protect temperature-sensitive product
- Built a serviceable, stable mechanical assembly (alignment, access, routing, drainability)

## System overview

**Major subsystems that I designed**
- **Kettle / reboiler (batch vessel):** heated vessel providing vapor generation
- **Mixer / feed handling:** supports batch preparation and consistent boiling behavior
- **Distillation column:** separation section mounted to a structural frame
- **Structural frame:** supports the system, provides access and mounting points, and keeps alignment under load

![Labeled overview of the build]({{ img }}Vac_dis_labels.png)


![Installed unit showing access and structure]({{ img }}VacDistillation2.jpg)


## Design approach

### 1) Process sizing (vacuum distillation fundamentals)
- Defined the operating pressure range and temperature targets to achieve separation at reduced boiling temperature
- Estimated condenser duty and cooling requirements from mass/energy balance assumptions
- Considered operability constraints (startup, steady operation, shutdown, draining/cleaning)

### 2) Column design (stage estimation)
- Used the Fenske equation as an initial sizing tool to estimate theoretical stage requirements and guide column configuration decisions
- Translated stage requirements into a practical column build (packing/plates, height, mounting, insulation, serviceability)

![Distillation schematic (context for column sizing)]({{ img }}fenske.png)


### 3) Mechanical design and buildability
- Structured the assembly for shop fabrication and field integration (mounting strategy, access points, and routing)
- Designed the frame and supports to keep the column aligned and stable while allowing safe operator access
- Built in maintenance needs: cleaning access, drainability, and component replacement considerations

## What I delivered
- 3D CAD assembly and key part models
- Detailed drawing package for fabrication and assembly
- Bill of materials and build notes
- Commissioning support

## Notes / lessons learned
- Vacuum systems reward obsessive attention to sealing, routing, and service access
- Designing for cleaning/draining early saves major rework later
