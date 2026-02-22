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

{% assign images = site.static_files
  | where_exp: "f", "f.path contains '/_projects/other/'"
  | where_exp: "f", "f.extname == '.png' or f.extname == '.jpg' or f.extname == '.jpeg' or f.extname == '.gif' or f.extname == '.webp'"
  | sort: "path"
%}

{% if images.size > 0 %}

<div class="gallery-grid">
  {% for img in images %}
    {% assign caption = img.name
      | split: '.'
      | first
      | replace: '_', ' '
      | replace: '-', ' '
    %}
    <figure class="gallery-item">
      <a href="{{ site.baseurl }}{{ img.path }}">
        <img src="{{ site.baseurl }}{{ img.path }}" alt="{{ caption | escape }}">
      </a>
      <figcaption class="caption">{{ caption }}</figcaption>
    </figure>
  {% endfor %}
</div>

<style>
  .gallery-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
    gap:14px;
    margin-top:10px;
  }
  .gallery-item{
    margin:0;
    padding:10px;
    border:1px solid rgba(0,0,0,0.12);
    border-radius:10px;
    background: rgba(0,0,0,0.02);
  }
  .gallery-item img{
    width:100%;
    height:auto;
    display:block;
    border-radius:8px;
  }
  .caption{
    margin-top:8px;
    font-size:0.9rem;
    opacity:0.8;
  }
</style>

{% else %}

_No images found in `/_projects/other/` yet._

{% endif %}
- For clean captions/descriptions, set `image_captions:` and `image_descriptions:` in the front matter keyed by the exact filename.
