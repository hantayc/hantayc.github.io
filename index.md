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

I’m a data scientist with an M.S. in Information and Data Science from UC Berkeley and over five years of experience making decisions with data across consulting and financial services. I began my career in pharmaceuticals, supporting four enterprise clients — including two Fortune 100 companies and a top-35 global pharmaceutical firm — before moving into digital, CX and operational analytics at AIG and later Corebridge Financial following the rebrand of its Individual Retirement and Life businesses.

My work at Berkeley and professionally spans applied NLP & GenAI, time-series forecasting, and causal experimentation — from problem framing and modeling to deployment and executive-level decision support. I’ve led initiatives that reversed double-digit CSAT declines, improved capacity planning through predictive forecasting, and delivered six-figure cost savings through automation.

---
### Featured Projects

{% assign featured = site.projects | sort: "date" | reverse | slice: 0, 4 %}

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
