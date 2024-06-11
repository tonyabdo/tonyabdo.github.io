---
layout: page
title: photography
permalink: /photography/
description:
nav: true
nav_order: 3
display_categories: [nature, urban, bands]
horizontal: false
---


<p align="center">See my photos before they show up here on IG!</p>

<div class="social">
  <div class="contact-icons">
    <a href="https://instagram.com/{{ site.instagram_id }}" title="Instagram"><i class="fa-brands fa-instagram"></i></a>
  </div>
</div>

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_photography_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_photos = site.photography | where: "category", category %}
  {% assign sorted_photos = categorized_photos | sort : "importance" %}

  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_photos %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_photos %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_photos = site.photography | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for song in sorted_photos %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for song in sorted_photos %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
