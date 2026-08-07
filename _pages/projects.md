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
.projects .grid-sizer, .projects .grid-item {
  width: 300px;
}
.projects .card {
  display: flex;
  flex-direction: column;
  height: 100%;
  min-height: 340px;
}
.projects .card figure {
  margin: 0;
}
.projects .card img {
  width: 100%;
  height: 170px;
  object-fit: cover;
}
.projects .card-body {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
}
.projects .card:not(:has(figure)) .card-body {
  justify-content: center;
  padding-top: 170px;
  position: relative;
}
.projects .card:not(:has(figure)) .card-body::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 170px;
  background: var(--global-divider-color, rgba(128,128,128,0.12));
}
.projects .card-title {
  font-size: 1.1rem;
}
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
