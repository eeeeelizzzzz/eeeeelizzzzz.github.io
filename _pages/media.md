---
layout: page
title: media
permalink: /media/
nav: true
nav_order: 6
---

## Media appearances

{% if site.data.media and site.data.media.size > 0 %}
<div class="media-list">
  {% for item in site.data.media %}
  <div class="media-item card mb-3">
    <div class="card-body">
      <div class="d-flex justify-content-between align-items-start">
        <div class="flex-grow-1">
          <h5 class="card-title mb-2">
            {% if item.link %}
              <a href="{{ item.link }}" target="_blank" rel="noopener noreferrer" class="text-decoration-none">
                {{ item.title }}
                <i class="fas fa-external-link-alt fa-sm ml-1"></i>
              </a>
            {% else %}
              {{ item.title }}
            {% endif %}
          </h5>
          <div class="text-muted mb-2">
            <strong>{{ item.outlet }}</strong>
            {% if item.type %} • {{ item.type }}{% endif %}
          </div>
          {% if item.description %}
            <div class="media-description">{{ item.description | markdownify | remove: '<p>' | remove: '</p>' }}</div>
          {% endif %}
        </div>
        {% if item.date %}
          <span class="badge badge-primary ml-2">{{ item.date }}</span>
        {% endif %}
      </div>
    </div>
  </div>
  {% endfor %}
</div>

<style>
.media-item {
  border: 1px solid #e9ecef;
  border-radius: 8px;
  transition: box-shadow 0.2s ease-in-out;
}

.media-item:hover {
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}

.media-item .card-title a {
  color: #2c3e50;
}

.media-item .card-title a:hover {
  color: #3498db;
}

.media-description {
  color: #6c757d;
  font-size: 0.95em;
  line-height: 1.4;
}

.badge-primary {
  background-color: #3498db;
  color: white;
}
</style>
{% else %}
<p>No media items yet. Add them in <code>_data/media.yml</code>.</p>
{% endif %}
