---
layout: page
title: Projects
permalink: /projects/
---

{% assign items = site.projects | sort: "date" | reverse %}

<ul style="list-style:none; padding-left:0;">
{% for p in items %}
  <li style="margin-bottom:18px; padding:14px; border:1px solid #eee; border-radius:12px;">
    <h3 style="margin:0;">
      <a href="{{ p.url }}">{{ p.title }}</a>
    </h3>
    {% if p.subtitle %}<p style="margin:6px 0 0 0;">{{ p.subtitle }}</p>{% endif %}
    {% if p.tags %}
      <p style="margin:10px 0 0 0;">
      {% for tag in p.tags %}
        <span style="border:1px solid #ddd; padding:2px 8px; border-radius:999px; margin-right:6px; font-size:12px;">{{ tag }}</span>
      {% endfor %}
      </p>
    {% endif %}
  </li>
{% endfor %}
</ul>