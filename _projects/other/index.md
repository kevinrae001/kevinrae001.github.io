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
    {% unless f.name == "two_speed_manual_transmission.png" %}
      {% assign alt = f.name | split: "." | first | replace: "_", " " | replace: "-", " " %}
      <a href="{{ f.path | relative_url }}" target="_blank" rel="noopener">
        <img src="{{ f.path | relative_url }}" alt="{{ alt }}" loading="lazy">
        <div class="cap">{{ alt }}</div>
      </a>
    {% endunless %}
  {% endfor %}
</div>
{% else %}
_No images detected in this folder. Put images (png/jpg/jpeg/webp/avif) directly in `_projects/other/` and they’ll show up here automatically._
{% endif %}
