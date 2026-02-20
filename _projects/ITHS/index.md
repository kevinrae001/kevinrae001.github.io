---
layout: post
title: Autonomous Mobile Energy System (AMES)
description: Solar + waste-heat system for relocatable temporary camps—providing warmed air and potable water with a sun-tracking telescoping mast.
skills:
  - Mechanical Design
  - SolidWorks
  - FEA
  - Structural Sizing (members/fasteners)
  - DFM/DFA
  - Manufacturer Feedback Iteration
  - PFD / P&ID
main-image: /ISTS_panoramic.jpeg
---

> **Note:** I signed an NDA for this project, so the details below are intentionally high-level and limited to what I’m able to share publicly.

## Overview

This project was a **proof-of-concept mobile energy and heating system** intended to reduce fuel usage for relocatable temporary camps by leveraging **solar power** and **waste heat recovery** to support:
- **Warmed air**
- **Heated potable water**

A key subsystem was a **telescoping, sun-tracking mast** supporting the solar array.

---

## My Role & Contributions

I owned the mechanical engineering design work end-to-end, including:

- Ownership of the **SolidWorks CAD model** and **drawing package**
- **Engineering hand calculations** (members, joints, fasteners)
- **FEA** to validate critical components and loading cases
- Iterating the design based on **manufacturer feedback** (DFM/DFA, fit-up, practicality)
- Supporting integration decisions informed by **PFD/P&ID-level thinking** (interfaces, routing, serviceability)

---

## Engineering Highlights

### Sun-tracking telescoping mast
- Supported **~1.8 kW** of solar panels
- **Tilt capability:** up to **80°**
- **Rotation:** **360°** for sun-tracking
- Demonstrated survivability in testing up to **~80 km/h winds**

---

## Testing & Outcome

The system was field tested for approximately **two weeks in Suffield, Alberta**, and the proof-of-concept was successful enough to meaningfully contribute to a **$1.5M prize** outcome for the broader effort.

---

## Key Lessons Learned (from the POC)

1. **Mast tolerance/clearance design**
   - Excess clearance between telescoping stages led to **rattle in high winds**
   - Cabling/wiring approach needed improved routing and strain relief

2. **Sheet metal wall stiffness / form control**
   - Wall thickness and/or reinforcement strategy was insufficient, leading to **form retention issues**
   - Misalignment occurred due to **design decisions that didn’t adequately control datum structure and stack-up**

3. **Weatherproofing**
   - The system required improved sealing, ingress protection strategy, and environmental considerations

These issues were addressed and improved in a subsequent iteration.

---

## Image Gallery

### Featured image
{% assign folder_path = page.path | split: "/" | slice: 0, 2 | join: "/" %}
{% assign img_dir = "/" | append: folder_path | append: "/" %}
<img src="{{ img_dir }}ISTS_panoramic.jpeg" alt="AMES panoramic view" style="width:100%; height:auto; border-radius:12px;" />

### All project images (auto-pulled from this folder)
{% assign folder_path = page.path | split: "/" | slice: 0, 2 | join: "/" %}
{% assign imgs = site.static_files
  | where_exp: "f", "f.path contains folder_path"
  | where_exp: "f", "f.extname == '.jpg' or f.extname == '.jpeg' or f.extname == '.png' or f.extname == '.webp' or f.extname == '.gif'" %}

{% if imgs and imgs.size > 0 %}
<div style="display:grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 12px; align-items:start;">
  {% for f in imgs %}
    <figure style="margin:0;">
      <img
        src="{{ f.path }}"
        alt="{{ f.name | replace: '-', ' ' | replace: '_', ' ' }}"
        style="width:100%; height:auto; border-radius:12px;"
        loading="lazy"
      />
      <figcaption style="font-size:0.9em; opacity:0.8; padding:6px 2px 0;">
        {{ f.name }}
      </figcaption>
    </figure>
  {% endfor %}
</div>
{% endif %}
