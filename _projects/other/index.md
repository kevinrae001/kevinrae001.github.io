---
layout: post
title: Other projects
description: A grab-bag of smaller builds and prototypes.
skills:
  - Mechanical Design
  - Electrical Design
  - SolidWorks
  - Soldering
  - CNC
  - Welding / Fabricating
  - Arduino / Raspberry Pi / ESP32
  - 3D Printing
  - C / C++ / C#
main-image: /two_speed_manual_transmission.png
---

{% assign folder_path = page.path | split: "/" | slice: 0, 2 | join: "/" %}
{% assign files_in_folder = site.static_files | where_exp: "f", "f.path contains folder_path" | sort: "name" %}

<style>
  .img-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 12px; margin: 12px 0 18px; }
  .img-grid a { display:block; }
  .img-grid img { width: 100%; height: 220px; object-fit: cover; border-radius: 10px; border: 1px solid #ddd; }
  .note { font-size: 0.95em; color: #555; }
</style>

This page collects smaller builds, repairs, and prototypes that don’t need a full standalone writeup.

## Hot tub repair + BBQ heat exchanger
I bought a broken hot tub and swapped out the heating system. Water was pumped from the tub through copper coils inside a barbeque to heat it. Built with two friends.

- Focus: practical repair, plumbing, heat transfer, and iteration in the real world
- Outcome: a working hot tub with a simple external heating approach

{% assign count = 0 %}
<div class="img-grid">
{% for f in files_in_folder %}
  {% assign n = f.name | downcase %}
  {% assign ext = f.extname | downcase %}
  {% if ext == '.png' or ext == '.jpg' or ext == '.jpeg' or ext == '.webp' or ext == '.gif' %}
    {% if n contains 'hottub' or n contains 'hot_tub' or n contains 'hot-tub' or n contains 'spa' or n contains 'bbq' or n contains 'coil' or n contains 'heater' %}
      {% assign count = count | plus: 1 %}
      <a href="{{ f.path | relative_url }}"><img src="{{ f.path | relative_url }}" alt="{{ f.name }}"></a>
    {% endif %}
  {% endif %}
{% endfor %}
</div>
{% if count == 0 %}
<p class="note">No images matched this section. If you want auto-grouping to work, include “hottub”, “spa”, “bbq”, “coil”, or “heater” in the filenames.</p>
{% endif %}

## Backyard climbing wall (32 ft)
A 32 ft climbing wall built in a backyard.

- Focus: structural layout, material selection, outdoor durability, and build logistics
- Outcome: a large outdoor wall that’s usable and holds up to the elements

{% assign count = 0 %}
<div class="img-grid">
{% for f in files_in_folder %}
  {% assign n = f.name | downcase %}
  {% assign ext = f.extname | downcase %}
  {% if ext == '.png' or ext == '.jpg' or ext == '.jpeg' or ext == '.webp' or ext == '.gif' %}
    {% if n contains 'climb' or n contains 'climbing' or n contains 'wall' %}
      {% assign count = count | plus: 1 %}
      <a href="{{ f.path | relative_url }}"><img src="{{ f.path | relative_url }}" alt="{{ f.name }}"></a>
    {% endif %}
  {% endif %}
{% endfor %}
</div>
{% if count == 0 %}
<p class="note">No images matched this section. Filenames containing “climb”, “climbing”, or “wall” will show here.</p>
{% endif %}

## Cylinder pin wrench (Dometic-marine)
Designed a new cylinder pin wrench for Dometic-marine. Manufactured at the scale of hundreds.

- Focus: design-for-manufacture, robustness, usability, and repeatable production
- Outcome: a production-ready tool that can be made consistently at volume

{% assign count = 0 %}
<div class="img-grid">
{% for f in files_in_folder %}
  {% assign n = f.name | downcase %}
  {% assign ext = f.extname | downcase %}
  {% if ext == '.png' or ext == '.jpg' or ext == '.jpeg' or ext == '.webp' or ext == '.gif' %}
    {% if n contains 'wrench' or n contains 'pin' or n contains 'cylinder' or n contains 'dometic' %}
      {% assign count = count | plus: 1 %}
      <a href="{{ f.path | relative_url }}"><img src="{{ f.path | relative_url }}" alt="{{ f.name }}"></a>
    {% endif %}
  {% endif %}
{% endfor %}
</div>
{% if count == 0 %}
<p class="note">No images matched this section. Filenames containing “wrench”, “pin”, “cylinder”, or “dometic” will show here.</p>
{% endif %}

## Two-speed manual transmission (UBC Supermileage)
Built with the UBC Supermileage team. I added a Hall sensor to measure gear RPM and automatically dictated gear changes based on RPM.

- Focus: mechanical build + instrumentation + basic control logic
- Outcome: measured RPM and automated gear-change behavior tied to the drivetrain

{% assign count = 0 %}
<div class="img-grid">
{% for f in files_in_folder %}
  {% assign n = f.name | downcase %}
  {% assign ext = f.extname | downcase %}
  {% if ext == '.png' or ext == '.jpg' or ext == '.jpeg' or ext == '.webp' or ext == '.gif' %}
    {% if n contains 'transmission' or n contains 'two_speed' or n contains 'two-speed' or n contains 'gear' or n contains 'rpm' or n contains 'hall' or n contains 'supermileage' %}
      {% assign count = count | plus: 1 %}
      <a href="{{ f.path | relative_url }}"><img src="{{ f.path | relative_url }}" alt="{{ f.name }}"></a>
    {% endif %}
  {% endif %}
{% endfor %}
</div>
{% if count == 0 %}
<p class="note">No images matched this section. Filenames containing “transmission”, “two_speed”, “gear”, “rpm”, “hall”, or “supermileage” will show here.</p>
{% endif %}

## Two-axis CNC (school project)
Two-axis CNC built as a school project.

- Focus: motion hardware, alignment, basic CAM/G-code workflow, and system bring-up
- Outcome: a working 2-axis machine used to learn CNC fundamentals end-to-end

{% assign count = 0 %}
<div class="img-grid">
{% for f in files_in_folder %}
  {% assign n = f.name | downcase %}
  {% assign ext = f.extname | downcase %}
  {% if ext == '.png' or ext == '.jpg' or ext == '.jpeg' or ext == '.webp' or ext == '.gif' %}
    {% if n contains 'cnc' or n contains 'router' or n contains 'gantry' or n contains 'axis' %}
      {% assign count = count | plus: 1 %}
      <a href="{{ f.path | relative_url }}"><img src="{{ f.path | relative_url }}" alt="{{ f.name }}"></a>
    {% endif %}
  {% endif %}
{% endfor %}
</div>
{% if count == 0 %}
<p class="note">No images matched this section. Filenames containing “cnc”, “router”, “gantry”, or “axis” will show here.</p>
{% endif %}

## Other photos in this folder
If you drop more images into this folder later, they’ll show up here automatically (as long as they’re image file types).

{% assign count = 0 %}
<div class="img-grid">
{% for f in files_in_folder %}
  {% assign n = f.name | downcase %}
  {% assign ext = f.extname | downcase %}
  {% if ext == '.png' or ext == '.jpg' or ext == '.jpeg' or ext == '.webp' or ext == '.gif' %}
    {% unless n contains 'hottub' or n contains 'hot_tub' or n contains 'hot-tub' or n contains 'spa' or n contains 'bbq' or n contains 'coil' or n contains 'heater'
      or n contains 'climb' or n contains 'climbing' or n contains 'wall'
      or n contains 'wrench' or n contains 'pin' or n contains 'cylinder' or n contains 'dometic'
      or n contains 'transmission' or n contains 'two_speed' or n contains 'two-speed' or n contains 'gear' or n contains 'rpm' or n contains 'hall' or n contains 'supermileage'
      or n contains 'cnc' or n contains 'router' or n contains 'gantry' or n contains 'axis' %}
      {% assign count = count | plus: 1 %}
      <a href="{{ f.path | relative_url }}"><img src="{{ f.path | relative_url }}" alt="{{ f.name }}"></a>
    {% endunless %}
  {% endif %}
{% endfor %}
</div>
{% if count == 0 %}
<p class="note">No extra images found beyond the project sections above.</p>
{% endif %}
