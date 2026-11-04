---
layout: single
title: Taylor Han
permalink: /
author_profile: true
header:
  show_title: false
classes: home
---
### Summary

I’m a Data Scientist with an M.S. in Information and Data Science from UC Berkeley and 5+ years of experience driving decisions through data across consulting and financial services. I started my career in pharmaceuticals, supporting four enterprise clients, including two Fortune 100 companies and a top 35 global pharmaceutical firm, before transitioning into digital, CX, and operational analytics at [AIG](https://www.aig.com) and later [Corebridge Financial](https://www.corebridgefinancial.com) following the spin off of its Individual Retirement and Life businesses.

My work spans applied NLP and GenAI, time series forecasting, and causal experimentation, with a focus on taking problems from initial framing through modeling to deployment and executive level decision making. I have led initiatives that reversed double digit CSAT declines, improved workforce planning through predictive forecasting, and generated six figure cost savings through automation.

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
