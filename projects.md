---
layout: single
title: Projects
permalink: /projects/
author_profile: false
---

{% assign items = site.projects | sort: "date" | reverse %}

<ul class="projects-grid">
{% for p in items %}
  <li class="projects-item">
    <a class="projects-thumb" href="{{ p.url | relative_url }}">
      {% if p.thumbnail %}
        <img src="{{ p.thumbnail | relative_url }}" alt="{{ p.title }} thumbnail">
      {% else %}
        <div class="projects-thumb-fallback" aria-hidden="true"></div>
      {% endif %}
    </a>

    <div class="projects-body">
      <h3 class="projects-title">
        <a href="{{ p.url | relative_url }}">{{ p.title }}</a>
      </h3>

      {% if p.subtitle %}
        <p class="projects-subtitle">{{ p.subtitle }}</p>
      {% endif %}

      {% if p.tags %}
        <p class="projects-tags">
          {% for tag in p.tags %}
            <span class="badge badge--primary">{{ tag }}</span>
          {% endfor %}
        </p>
      {% endif %}
    </div>
  </li>
{% endfor %}
</ul>