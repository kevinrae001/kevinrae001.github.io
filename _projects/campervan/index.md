---
layout: post
title: Campervan Conversion
description: Campervan build focused on reliability, serviceability, and clean packaging.
skills:
  - Mechanical design
  - CAD (SolidWorks)
  - Fabrication & assembly
  - Electrical (48V DC) wiring
  - Soldering
  - CNC
  - Woodworking
main-image: /banner.jpg
---

## Summary

This project documents a campervan conversion build with an emphasis on robust mechanical design, clean integration, and practical service access.

**Quick facts :**
- **Vehicle:** 1999 GMC Savana 3500 extended
- **Use case:** Long trips (several months)
- **Constraints:** Budget, off-grid duration, winter use
- **Tools/process:** CAD, CNC cutting, soldering, electrical design, hands-on building

---

## Goals and requirements

- **Safety:** secure mounting, protected wiring, proper fusing, strain relief, and ventilation where required  
- **Serviceability:** accessible fasteners, removable panels, modular subassemblies  
- **Packaging:** efficient use of volume, sensible cable routing, minimized rattles  
- **Reliability:** vibration-aware design, robust joints, appropriate materials/finishes  
- **Documentation:** BOM, wiring map, assembly notes, and revision-friendly structure

---

## Build gallery

The block below automatically renders **all images in this project folder** (png/jpg/jpeg/webp/gif).  
If you don’t want an image to show, move it out of the folder or rename it with a prefix like `_ignore-`.

{% assign parts = page.path | split:'/' %}
{% assign project_dir = '/' | append: parts[0] | append:'/' | append: parts[1] | append:'/' %}
{% assign exts = ".png,.jpg,.jpeg,.webp,.gif" | split: "," %}
{% assign files = site.static_files | where_exp: "f", "f.path contains project_dir" | sort: "path" %}

<div class="project-gallery">
  {% for f in files %}
    {% if exts contains f.extname %}
      <figure style="margin: 0 0 1rem 0;">
        <img
          src="{{ f.path | relative_url }}"
          alt="{{ page.title }} image {{ forloop.index }}"
          loading="lazy"
          style="max-width: 100%; height: auto;"
        >
        <figcaption style="font-size: 0.9em; opacity: 0.8;">
          {{ f.name }}
        </figcaption>
      </figure>
    {% endif %}
  {% endfor %}
</div>

---
