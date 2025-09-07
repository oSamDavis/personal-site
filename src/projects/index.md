---
layout: default
title: Projects
permalink: /projects/
---

<h1>Projects</h1>
<ul class="projects-list">
  {% assign sorted = site.projects | sort: "date" | reverse %}
  {% for item in sorted %}
    <li>
      <a class="project-link" href="{{ item.url | relative_url }}">
        <strong class="title">{{ item.title }}</strong>
      </a>
      {% if item.summary %}<div class="summary">{{ item.summary }}</div>{% endif %}
    </li>
  {% endfor %}
</ul>
