---
layout: page
title: "Vorschung"
permalink: /vorschung/
author_profile: false
gallery:
  - url: ../research/compton
    image_path: ../assets/images/research/euclid.jpg
    alt: "Owl Nebula. 2023-01-14"
  - url: ../assets/images/research/DES.jpg
    image_path: ../assets/images/research/DES.jpg
    alt: "Owl Nebula. 2023-01-14"
  - url: ../assets/images/research/g4.png
    image_path: ../assets/images/research/g4.png
    alt: "Owl Nebula. 2023-01-14"
toc: true
horizontal: false
---
{% include base_path %} 

{% include gallery id="gallery"  caption="CORROPOPOLA" %}

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
