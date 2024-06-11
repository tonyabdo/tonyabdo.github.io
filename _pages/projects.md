---
layout: page
title: projects
permalink: /projects/
description: 
nav: true
nav_order: 2
display_categories: [audio, controls, 3D printing]
horizontal: true
projects_pdf: Tony_Abdo_Portfolio.pdf
---

<p align="center">You can find a pdf of selected projects in top right for offline viewing. To see my projects before they show up here, follow on IG, YT, or Thingiverse!</p>

<div class="social">
  <div class="contact-icons">
    <a href="https://instagram.com/{{ site.instagram_id }}" title="Instagram"><i class="fa-brands fa-instagram"></i></a>
    <a href="https://youtube.com/@{{ site.youtube_id }}" title="YouTube"><i class="fa-brands fa-youtube"></i></a>
    <a href="https://www.thingiverse.com/{{ site.thingiverse_id }}/designs" title="Thingiverse"><i class="fa-solid fa-cubes"></i></a>
  </div>
</div>

  


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
