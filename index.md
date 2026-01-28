---
layout: page
title: Taylor Han
permalink: /
---

### Data Scientist (NLP/GenAI • Forecasting • Experimentation)
I build practical ML systems and analytics products—end to end—from data pipelines to deployment.

**Links:** [Projects](/projects/) · [Resume](/resume/) · [GitHub](https://github.com/<yourhandle>) · [LinkedIn](https://linkedin.com/in/<yourhandle>)

---

## Featured Projects
{% assign featured = site.projects | sort: "date" | reverse | slice: 0, 3 %}
{% for p in featured %}
- **[{{ p.title }}]({{ p.url }})** — {{ p.subtitle }}
{% endfor %}