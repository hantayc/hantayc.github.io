---
layout: single
title: 
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

## Featured Projects
{% assign featured = site.projects | sort: "date" | reverse | slice: 0, 3 %}
{% for p in featured %}
- **[{{ p.title }}]({{ p.url }})** — {{ p.subtitle }}
{% endfor %}