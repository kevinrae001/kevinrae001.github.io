---
layout: post
title: Vacuum Distillation Unit
description: >
  Designed and built a vacuum distillation unit (kettle + column + condenser/receiver loop) to separate temperature-sensitive liquids under reduced pressure, taking the system from process sizing through mechanical design, fabrication support, and commissioning.
skills:
  - Mechanical design (SolidWorks)
  - ASME Y14 / GD&T
  - Mass & energy balances
  - Distillation theory (Fenske)
  - Fabrication support (welding / assembly)
  - Test & commissioning
  - MATLAB
main-image: /banner.jpg
---

{% assign project_folder = page.path | split: "/" | slice: 0, 2 | join: "/" %}
{% assign img = "/" | append: project_folder | append: "/" %}

![Vacuum distillation unit (installed)]({{ img }}banner.jpg)

## Summary

This project was a full build of a vacuum distillation system intended to lower boiling temperatures and protect product quality by operating under reduced pressure. I owned the end-to-end mechanical design, supported fabrication/assembly, and brought the unit through commissioning in a working industrial environment.

## System overview

**Major subsystems**
- **Kettle / reboiler (batch vessel):** heated vessel providing vapor generation
- **Mixer / feed handling:** supports batch preparation and consistent boiling behavior
- **Distillation column:** separation section mounted to a structural frame
- **Condenser / receiver loop:** condenses overhead vapor and manages collected distillate / reflux
- **Structural frame:** supports the system, provides access and mounting points, and keeps alignment under load

![Labeled overview of the build]({{ img }}Vac_dis_labels.png)
*Labeled build photo: kettle, mixer, column, and frame.*

![Installed unit showing access and structure]({{ img }}VacDistillation2.jpg)
*Installed unit in the work area (structure, access, and routing).*

## Design approach

### 1) Process sizing (vacuum distillation fundamentals)
- Defined the operating pressure range and temperature targets to achieve separation at reduced boiling temperature.
- Estimated condenser duty and cooling requirements from mass/energy balance assumptions.
- Considered operability constraints (startup, steady operation, shutdown, draining/cleaning).

### 2) Column design (stage estimation)
- Used the **Fenske equation** as an initial sizing tool to estimate theoretical stage requirements and guide column configuration decisions.
- Translating stage requirements into a practical column build (packing/plates, height, mounting, insulation, serviceability).

![Distillation schematic (context for column sizing)]({{ img }}fenske.png)
*Reference schematic used to communicate column concepts and flow paths.*

### 3) Mechanical design and buildability
- Structured the assembly for shop fabrication and field integration (mounting strategy, access points, and routing).
- Designed the frame and supports to keep the column aligned and stable while allowing safe access for operators.
- Incorporated practical maintenance needs: cleaning access, drainability, and component replacement considerations.

## What I delivered

- 3D CAD assembly and key part models
- Detailed drawing package for fabrication and assembly
- Bill of materials (BOM) and build notes
- Commissioning support (fit-up, alignment, leak checks, and operational shakedown)

## Notes / lessons learned

- Vacuum systems reward obsessive attention to sealing, routing, and service access.
- Structural stiffness and alignment matter more than they look like they should—especially with tall columns.
- Designing for cleaning/draining early saves major rework later.

---
