---
layout: single
title: Taylor Han
permalink: /
author_profile: true
header:
  show_title: false
classes: home
---
### Data Scientist · NLP / GenAI · Forecasting · Experimentation

I build practical ML systems and analytics products end-to-end — from data pipelines and modeling to deployment and decision support.

I’m especially interested in:
- applied NLP & GenAI systems
- forecasting and time-series modeling
- experimentation and causal analysis

---
### Featured Projects

{% assign featured = site.projects | sort: "date" | reverse | slice: 0, 3 %}

<ul class="projects-grid">
{% for p in featured %}
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