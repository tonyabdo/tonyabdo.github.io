---
layout: page
title: music
permalink: /music/
description:
nav: true
nav_order: 3
display_categories: [piano, guitar]
horizontal: true
---

<p align="center">Watch my videos before they show up here on IG and YT!</p>

<div class="social">
  <div class="contact-icons">
    <a href="https://instagram.com/{{ site.instagram_id }}" title="Instagram"><i class="fa-brands fa-instagram"></i></a>
    <a href="https://youtube.com/@{{ site.youtube_id }}" title="YouTube"><i class="fa-brands fa-youtube"></i></a>

  </div>
</div>


<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_music_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_music = site.music | where: "category", category %}
  {% assign sorted_music = categorized_music | sort : "importance" %}

  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_music %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-sm-3">
    {% for project in sorted_music %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_music = site.music | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for song in sorted_music %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for song in sorted_music %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
