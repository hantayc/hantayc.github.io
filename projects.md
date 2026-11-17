---
layout: page
title: Projects
permalink: /projects/
description: Selected data science, NLP/GenAI, and ML systems projects by Taylor Han.
---

{% assign items = site.projects | sort: "date" | reverse %}
<ul class="projects-grid">
  {% for p in items %}
    <li class="project-card">
      <a class="project-thumb" href="{{ p.url | relative_url }}">
        {% if p.thumbnail %}
          <img src="{{ p.thumbnail | relative_url }}" alt="{{ p.title }} thumbnail">
        {% else %}
          <span class="project-thumb-fallback" aria-hidden="true"></span>
        {% endif %}
      </a>
      <div class="project-body">
        <h3><a href="{{ p.url | relative_url }}">{{ p.title }}</a></h3>
        {% if p.subtitle %}<p class="project-sub">{{ p.subtitle }}</p>{% endif %}
        {% if p.tags %}
          <div class="project-tags">
            {% for tag in p.tags limit: 5 %}<span class="tag">{{ tag }}</span>{% endfor %}
          </div>
        {% endif %}
      </div>
    </li>
  {% endfor %}
</ul>
