---
layout: page
title: ""
permalink: /forschung/
# author_profile: false
toc: true
nav: true
nav_order: 2
horizontal: false
# classes: wide-page
---
{% include base_path %} 

# Research Projects

<div class="projects">
{%- assign research_projects = site.projects | where_exp: "project", "project.category != 'industry'" | sort: "importance" -%}
{%- if page.horizontal -%}
<div class="container">
  <div class="row row-cols-2">
  {%- for project in research_projects -%}
    {% include projects_horizontal.html %}
  {%- endfor %}
  </div>
</div>
{%- else -%}
<div class="grid">
  {%- for project in research_projects -%}
    {% include projects.html %}
  {%- endfor %}
</div>
{%- endif -%}
</div>

# Industry Projects

<div class="projects">
{%- assign industry_projects = site.projects | where: "category", "industry" | sort: "importance" -%}
{%- if page.horizontal -%}
<div class="container">
  <div class="row row-cols-2">
  {%- for project in industry_projects -%}
    {% include projects_horizontal.html %}
  {%- endfor %}
  </div>
</div>
{%- else -%}
<div class="grid">
  {%- for project in industry_projects -%}
    {% include projects.html %}
  {%- endfor %}
</div>
{%- endif -%}
</div>
