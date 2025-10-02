---
layout: page
title: projects
permalink: /projects/
description: Some cool projects that I've worked on.
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
---

## Research

* New configurations for the OMEGA laser (Nuclear Fusion – Laboratory for Laser Energetics)  
    * ISEF 3rd place grand award, 2nd place special award
* Quantum chip temperature dependence on the transmon (Quantum Computing – U of R)
* Proposal for CERN Beamline competition 2023
* Proposal for CERN Beamline competition 2022

## Other

* <a href="https://www.instagram.com/academicindex/">Academic Index</a> - Built automated social media account. 120M+ views in three months, revenue in the thousands.
* CRADLE – Contrail Reduction System and Data Live E-System. Using predictive ML to calculate contrail formation  
    * Backed by grant from MIT



{% comment %}
<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
{% endcomment %}
