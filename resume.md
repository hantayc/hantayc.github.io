---
layout: page
title: Resume
permalink: /resume/
---

## Experience
{% for job in site.data.experience %}
### {{ job.title }} — {{ job.company }}
**{{ job.dates }}**

{% for b in job.bullets %}
- {{ b }}
{% endfor %}

{% endfor %}