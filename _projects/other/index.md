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
---
layout: default
title: Image Gallery
---

## Sub-projects in this folder
{% if site.projects %}
{% assign children = site.projects
  | where_exp: "p", "p.path contains '_projects/hottub/'"
  | where_exp: "p", "p.url != page.url"
  | sort: "title" %}

{% if children.size > 0 %}
<ul>
  {% for p in children %}
    <li>
      <a href="{{ p.url | relative_url }}">{{ p.title | default: p.name }}</a>
      {% if p.description %} — {{ p.description }}{% endif %}
    </li>
  {% endfor %}
</ul>
{% else %}
<p><em>No sub-pages detected yet.</em></p>
{% endif %}
{% endif %}

---

## Gallery (auto-categorized)
{% comment %}
Auto-detect all image files under this folder and group them by the first subfolder name.
Examples:
- _projects/hottub/plumbing/*.jpg  -> category "plumbing"
- _projects/hottub/electrical/*.png -> category "electrical"
- _projects/hottub/*.jpg -> category "overview"
{% endcomment %}

{% assign root = page.path | replace: "index.md", "" %}
{% assign imgs = site.static_files | where_exp: "f", "f.path contains root" %}
{% assign imgs = imgs | where_exp: "f", "f.extname == '.png' or f.extname == '.jpg' or f.extname == '.jpeg' or f.extname == '.gif' or f.extname == '.webp'" %}

{% if imgs.size == 0 %}
> No images found under `{{ root }}`. Add images anywhere inside this folder (or subfolders) and they will appear here automatically.
{% else %}

{% assign grouped = imgs | group_by_exp: "f", "f.path | remove: root | split:'/' | first" %}

{% comment %}Optional hero image (first image found){% endcomment %}
{% assign hero = imgs | first %}
{% if hero %}
<div style="margin: 12px 0 18px 0;">
  <img src="{{ hero.path | relative_url }}" alt="Hot tub build hero image" style="width:100%;max-height:520px;object-fit:cover;border-radius:12px;">
</div>
{% endif %}

{% for group in grouped %}
  {% assign category = group.name %}
  {% comment %}
  If the image is directly under hottub/ (no subfolder), group.name becomes the filename.
  Treat that case as "overview".
  {% endcomment %}
  {% if category contains "." %}
    {% assign category = "overview" %}
  {% endif %}

  {% assign cat_title = category | replace: "-", " " | replace: "_", " " %}
  <h3 style="margin-top:28px;">{{ cat_title | capitalize }}</h3>

  {% comment %}Category description priority: front matter mapping -> heuristic fallback{% endcomment %}
  {% assign cat_desc = page.category_descriptions[category] %}
  {% if cat_desc %}
    <p>{{ cat_desc }}</p>
  {% else %}
    {% if category contains "plumb" or category contains "hydro" or category contains "water" %}
      <p>Plumbing layout, manifolds, unions/valves, leak mitigation, and serviceability choices.</p>
    {% elsif category contains "elect" or category contains "wire" or category contains "panel" %}
      <p>Electrical distribution, grounding/bonding, enclosure layout, wiring management, and safety considerations.</p>
    {% elsif category contains "control" or category contains "sensor" or category contains "pcb" %}
      <p>Controls and instrumentation: sensing, switching, interlocks, and system behavior.</p>
    {% elsif category contains "cad" or category contains "model" or category contains "design" %}
      <p>CAD/modeling snapshots: packaging, constraints, interfaces, and iterations.</p>
    {% elsif category contains "frame" or category contains "structure" or category contains "mount" %}
      <p>Mechanical mounting and structure: brackets, fasteners, stiffness, and assembly approach.</p>
    {% else %}
      <p><em>Add a category description by defining <code>category_descriptions.{{ category }}</code> in the front matter.</em></p>
    {% endif %}
  {% endif %}

  <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:14px;align-items:start;">
    {% for f in group.items %}
      {% comment %}If this “group” was actually the overview filename case, still render it under overview{% endcomment %}
      {% if group.name contains "." and category == "overview" %}
        {% assign f = group.items[forloop.index0] %}
      {% endif %}

      {% assign fname = f.name %}
      {% assign base = fname | split: "." | first %}
      {% assign auto_caption = base | replace: "-", " " | replace: "_", " " %}
      {% assign caption = page.image_captions[fname] | default: auto_caption %}

      <figure style="margin:0;">
        <a href="{{ f.path | relative_url }}">
          <img src="{{ f.path | relative_url }}" alt="{{ caption | escape }}" style="width:100%;border-radius:10px;">
        </a>
        <figcaption style="font-size:0.95em;line-height:1.25;margin-top:6px;">
          <strong>{{ caption }}</strong>
          {% if page.image_descriptions and page.image_descriptions[fname] %}
            <div style="margin-top:4px;">{{ page.image_descriptions[fname] }}</div>
          {% else %}
            <div style="margin-top:4px;"><em>Add a better per-image description by defining <code>image_descriptions.{{ fname }}</code> in the front matter.</em></div>
          {% endif %}
        </figcaption>
      </figure>
    {% endfor %}
  </div>

{% endfor %}
{% endif %}

---

## Notes (optional)
- Put images into subfolders like `overview/`, `plumbing/`, `electrical/`, `controls/`, `cad/` to automatically create categories.
- For clean captions/descriptions, set `image_captions:` and `image_descriptions:` in the front matter keyed by the exact filename.
