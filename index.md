---
layout: single
title: Taylor Han
permalink: /
author_profile: true
---

### Data Scientist · NLP / GenAI · Forecasting · Experimentation

I build practical ML systems and analytics products end-to-end — from data pipelines and modeling to deployment and decision support.

I’m especially interested in:
- applied NLP & GenAI systems
- forecasting and time-series modeling
- experimentation and causal analysis

[Projects](/projects/) · [Resume](/resume/) · [GitHub](https://github.com/hantayc) · [LinkedIn](https://linkedin.com/in/YOUR_LINKEDIN)

---

## Featured Projects
{% assign featured = site.projects | sort: "date" | reverse | slice: 0, 3 %}
{% for p in featured %}
- **[{{ p.title }}]({{ p.url }})** — {{ p.subtitle }}
{% endfor %}