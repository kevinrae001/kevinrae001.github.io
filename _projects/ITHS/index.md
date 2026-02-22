---
layout: post
title: Integrated thermal hydronic system
description: A research system consisting of three hydronic loops interacting at a thermal storage tank
skills:
  - Mechanical Design
  - SolidWorks
  - Instrumentation
  - MATLAB
  - Simulink
  - C / C++ / C#
  - PFD / P&ID
main-image: /ISTS_panoramic.jpeg
---

{% assign project_folder = page.path | split: "/" | slice: 0, 2 | join: "/" %}
{% assign asset_base = "/" | append: project_folder | append: "/" %}

![ITHS panoramic view]({{ asset_base | append: "ISTS_panoramic.jpeg" | relative_url }})

## Overview
I supported a UBC research project by building an operational integrated thermal hydronic system test setup that enabled repeatable experiments for model characterization and validation.

At a high level, the system consists of three hydronic loops that interact through a thermal storage tank, with a solar-thermal subsystem and a heat pump involved in the overall energy flow.

## My role
I owned the hands-on engineering work to get the rig operational and useful for research, including:
- Building and commissioning the physical test setup for repeatable data collection
- Working with graduate students on nonlinear, physics-based, state-space modeling in MATLAB/Simulink
- Instrumentation selection, installation, calibration, and DAQ bring-up
- Troubleshooting and repair to restore expected performance

## Key contributions
### Solar thermal array mechanical + controls work
- Designed and implemented an operational bearing/support solution to enable array rotation
- Programmed a motor control approach to:
  - Track the sun throughout the day, and/or
  - Rotate on demand for test sequences

### Instrumentation + data acquisition
- Installed and commissioned sensors including:
  - Flow sensors
  - Temperature sensors
  - Solar radiation sensors
  - Humidity sensors
- Integrated and calibrated analog-to-digital conversion hardware as required to support the sensor suite

### Heat pump troubleshooting + repair
- Diagnosed reduced performance to a refrigerant leak
- Restored operation by repairing the issue and recharging refrigerant to bring performance back up

## Tools used
- **CAD:** SolidWorks  
- **Modeling:** MATLAB, Simulink  
- **Documentation:** PFD / P&ID  
- **Controls/Software:** C / C++ / C# (as applicable for control/DAQ tasks)

---

## Image gallery

<style>
  .proj-gallery { display:grid; grid-template-columns:repeat(auto-fit,minmax(220px,1fr)); gap:12px; margin: 12px 0 4px; }
  .proj-gallery a { display:block; border:1px solid rgba(0,0,0,0.12); border-radius:10px; overflow:hidden; }
  .proj-gallery img { width:100%; height:180px; object-fit:cover; display:block; }
  .proj-gallery .cap { padding:8px 10px; font-size:0.9rem; opacity:0.85; }
</style>

{% assign exts = ".png|.jpg|.jpeg|.gif|.webp|.avif" | split: "|" %}
{% assign images = site.static_files
  | where_exp: "f", "f.path contains project_folder"
  | where_exp: "f", "exts contains f.extname"
  | sort: "name"
%}

{% if images.size > 0 %}
<div class="proj-gallery">
  {% for f in images %}
    {% unless f.name == "ISTS_panoramic.jpeg" %}
      {% assign alt = f.name | split: "." | first | replace: "_", " " | replace: "-", " " %}
      <a href="{{ f.path | relative_url }}" target="_blank" rel="noopener">
        <img src="{{ f.path | relative_url }}" alt="{{ alt }}" loading="lazy">
        <div class="cap">{{ alt }}</div>
      </a>
    {% endunless %}
  {% endfor %}
</div>
{% else %}
_No images detected in this folder. Put images (png/jpg/jpeg/webp/avif) directly in `_projects/ITHS/` and they’ll show up here automatically._
{% endif %}
