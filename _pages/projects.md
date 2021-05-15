---
layout: page
title: Projects
permalink: /projects/
description: A growing collection of your cool projects.
nav: true
display_categories:
  - title: Multi-robot System
    horizontal: false
  - title: ROS
    horizontal: false 
  - title: Machine Learning 
    horizontal: true
  - title: Computer Vision 
    horizontal: true
  - title: SLAM
    horizontal: true
  - title: Localization 
    horizontal: true
  - title: Mapping & Planning 
    horizontal: true
  - title: Cpp
    horizontal: true
---
<div class="projects">
  {% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
    {% for category in page.display_categories %}
      <h2 class="category">{{category.title}}</h2>
      {% assign categorized_projects = site.projects | where: "category", category.title %}
      {% assign sorted_projects = categorized_projects | sort: "importance" %}
      <!-- Generate cards for each project -->
      {% if category.horizontal %}
        <div class="container">
          <div class="row row-cols-2">
          {% for project in sorted_projects %}
            {% include projects_horizontal.html %}
          {% endfor %}
          </div>
        </div>
      {% else %}
        <div class="grid">
          {% for project in sorted_projects %}
            {% include projects.html %}
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
        <div class="row row-cols-2">
        {% for project in sorted_projects %}
          {% include projects_hrz.html %}
        {% endfor %}
        </div>
      </div>
    {% else %}
      <div class="grid">
        {% for project in sorted_projects %}
          {% include projects.html %}
        {% endfor %}
      </div>
    {% endif %}

  {% endif %}

</div>
