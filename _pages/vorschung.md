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

{% include gallery id="gallery"  caption="" %}

<!-- pages/projects.md -->
<div class="projects">
 <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {% endfor %}


<!--
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
-->
</div>
