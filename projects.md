---
layout: single
title: Projects
permalink: /projects/
author_profile: false
---

{% comment %}
Projects index page.
This pulls from the _projects collection and lists everything in reverse
chronological order so newer work shows up first.
{% endcomment %}

{% assign items = site.projects | sort: "date" | reverse %}

{% for p in items %}
### [{{ p.title }}]({{ p.url }})

{% if p.subtitle %}
{{ p.subtitle }}
{% endif %}

{% if p.tags %}
{% for tag in p.tags %}
<span class="badge badge--primary">{{ tag }}</span>
{% endfor %}
{% endif %}

---
{% endfor %}