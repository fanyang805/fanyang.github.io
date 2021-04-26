---
layout: page
title: Projects
permalink: /projects/
description: A growing collection of your cool projects.
nav: true
---

{% assign sorted_projects = site.projects | sort: "importance" %}
<ul class="post-list">
{% for project in sorted_projects %}
  <li>
      <h3><a class="project-title" {% if project.not_empty%} href="{{ project.url | relative_url }}" {% endif %}>{{ project.title }}
            {% if project.github %}
            <div class="github-icon">
              <div class="icon" data-toggle="tooltip" title="Code Repository">
                <a href="{{ project.github }}" target="_blank"><i class="fab fa-github gh-icon"></i></a>
              </div>
              {% if project.github_stars %}
              <span class="stars" data-toggle="tooltip" title="GitHub Stars">
                <i class="fas fa-star"></i>
                <span id="{{ project.github_stars }}-stars"></span>
              </span>
              {% endif %}
            </div>
            {% endif %}</a></h3>
      <p>{{project.description}}</p>
      <!-- {{project.img}} -->
      <div class="card hoverable">
        {% if project.images %}
          {% for image in project.images %}
          <img class="img-responsive" src="{{ image.path | relative_url}}" alt="project thumbnail">
            <div class="card-body">
              <!-- <h2 class="card-title text-lowercase">{{ project.title }}</h2> -->
              <p class="card-text">{{ image.text }}</p>
              <div class="row ml-1 mr-1 p-0"></div>
            </div>
          {% endfor %}
        <!-- <img src="{{ project.img | relative_url }}" alt="project thumbnail"> -->
        {% endif %}
      </div>
  </li>
{% endfor %}
</ul>
