---
layout: page
title: research
permalink: /research/
description: Research foci, field deployments, and code
nav: true
nav_order: 3
display_categories: [research, field deployments]
horizontal: false

---
My research focuses on observing and understanding the lower atmosphere—the boundary layer—where most high-impact weather develops. I specialize in designing and deploying advanced observing systems to fill critical data gaps, with a primary goal of improving the prediction of severe convection, tornadoes, and other hazardous weather.

To do this, I lead and participate in complex field campaigns and R&D projects. My work integrates state-of-the-art mobile profilers (like the CLAMPS systems), Doppler lidars, and next-generation Uncrewed Aircraft Systems (UAS). My efforts range from foundational boundary layer physics and hardware development (including a co-invented patent on UAS technology) to operational forecast improvement (testing data in the Warn-on-Forecast system) and post-storm damage assessment. 

Field deployments and research foci are described here. 
---
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

---

{% if site.data.repositories.github_repos %}

## GitHub Repositories

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
{% endif %}

---

