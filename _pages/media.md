---
layout: page
title: media
permalink: /media/
nav: true
nav_order: 6
---

## Media appearances

{% if site.data.media and site.data.media.size > 0 %}
<ul class="list-group list-group-flush">
  {% for item in site.data.media %}
  <li class="list-group-item">
    <div class="d-flex justify-content-between align-items-start">
      <div>
        <h5 class="mb-1">{% if item.link %}<a href="{{ item.link }}" target="_blank" rel="noopener noreferrer">{{ item.title }}</a>{% else %}{{ item.title }}{% endif %}</h5>
        <div class="text-muted">
          {% if item.outlet %}{{ item.outlet }}{% endif %}
          {% if item.type %} • {{ item.type }}{% endif %}
        </div>
        {% if item.description %}
          <div class="mt-1">{{ item.description | markdownify | remove: '<p>' | remove: '</p>' }}</div>
        {% endif %}
      </div>
      {% if item.date %}
        <span class="badge badge-pill badge-secondary">{{ item.date }}</span>
      {% endif %}
    </div>
  </li>
  {% endfor %}
</ul>
{% else %}
<p>No media items yet. Add them in <code>_data/media.yml</code>.</p>
{% endif %}
