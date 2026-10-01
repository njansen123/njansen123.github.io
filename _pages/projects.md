---
layout: page
title: projects
permalink: /projects/
description: My funded projects.
nav: true
nav_order: 4
display_categories: [Current, Concluded]
horizontal: false
---

<style>
/* Cards in a responsive grid that always fits the content width (overrides masonry positioning). */
.projects .grid { display: grid !important; grid-template-columns: repeat(auto-fill, minmax(230px, 1fr)); gap: 1.25rem; height: auto !important; margin-bottom: 1rem; }
.projects .grid-sizer { display: none; }
.projects .grid-item { position: static !important; left: auto !important; top: auto !important; width: auto !important; margin: 0 !important; }
.projects .grid-item > a { display: block; height: 100%; color: inherit; text-decoration: none; }
.projects .card { display: flex; flex-direction: column; height: 100%; overflow: hidden; border-radius: 10px; border: 1px solid var(--global-divider-color, rgba(128,128,128,0.2)); }
.projects .card figure { margin: 0; }
.projects .card picture, .projects .card img { display: block; width: 100%; }
.projects .card img { aspect-ratio: 16 / 9; height: auto; object-fit: contain; box-sizing: border-box; max-width: 100%; background: #ffffff; padding: 10px; border-bottom: 1px solid var(--global-divider-color, rgba(128,128,128,0.2)); }
.projects .card-body { flex: 1 1 auto; }
.projects .card-title { font-size: 1.1rem; }
.projects .card-text { font-size: 0.92rem; }
</style>

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
