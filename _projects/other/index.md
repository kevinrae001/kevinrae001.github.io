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

<style>
  .gallery {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 12px;
    margin: 12px 0 24px;
  }
  .thumb {
    margin: 0;
    border: 1px solid rgba(0,0,0,.12);
    border-radius: 10px;
    padding: 10px;
    background: rgba(0,0,0,.02);
  }
  .thumb img {
    width: 100%;
    height: 160px;
    object-fit: cover;
    border-radius: 8px;
    display: block;
  }
  .thumb figcaption {
    margin-top: 8px;
    font-size: 0.9rem;
    opacity: 0.85;
    word-break: break-word;
  }
  .folder-title { margin-top: 28px; }
</style>

# {{ page.title }}

{% assign exts = "jpg,jpeg,png,gif,webp,svg" | split: "," %}
{% assign base_dir = page.dir %}

{%- comment -%}
Collect unique subdirectories (relative to this page's folder).
We represent the page folder itself as "."
{%- endcomment -%}
{% capture dirs_raw %}
{% for f in site.static_files %}
  {% if f.path contains base_dir %}
    {% assign ext = f.extname | downcase | remove: "." %}
    {% if exts contains ext %}
      {% assign rel_dir = f.path | remove_first: base_dir | remove: f.name %}
      {% if rel_dir == "" %}{% assign rel_dir = "." %}{% endif %}
      {{ rel_dir }}|
    {% endif %}
  {% endif %}
{% endfor %}
{% endcapture %}

{% assign dirs = dirs_raw | split: "|" | uniq | sort %}
{% assign total_images = 0 %}

{%- comment -%}Count total images{%- endcomment -%}
{% for f in site.static_files %}
  {% if f.path contains base_dir %}
    {% assign ext = f.extname | downcase | remove: "." %}
    {% if exts contains ext %}
      {% assign total_images = total_images | plus: 1 %}
    {% endif %}
  {% endif %}
{% endfor %}

{% if total_images == 0 %}
No images found under `{{ base_dir }}`.
{% else %}
Found **{{ total_images }}** image(s) under `{{ base_dir }}` (including subfolders).

{% for d in dirs %}
  {% if d != "" %}
    <h2 class="folder-title">
      {% if d == "." %}
        Folder: (root)
      {% else %}
        Folder: {{ d }}
      {% endif %}
    </h2>

    <div class="gallery">
      {% for f in site.static_files %}
        {% if f.path contains base_dir %}
          {% assign ext = f.extname | downcase | remove: "." %}
          {% if exts contains ext %}
            {% assign rel_dir = f.path | remove_first: base_dir | remove: f.name %}
            {% if rel_dir == "" %}{% assign rel_dir = "." %}{% endif %}

            {% if rel_dir == d %}
              <figure class="thumb">
                <a href="{{ f.path | relative_url }}" target="_blank" rel="noopener">
                  <img src="{{ f.path | relative_url }}" alt="{{ f.basename | escape }}" loading="lazy">
                </a>
                <figcaption>{{ f.name }}</figcaption>
              </figure>
            {% endif %}
          {% endif %}
        {% endif %}
      {% endfor %}
    </div>
  {% endif %}
{% endfor %}
{% endif %}
