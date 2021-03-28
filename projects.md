---
layout: default
Title: PRojects
---

<h1>Latest Posts</h1>

<ul>
  {% for project in site.projects %}
    <li>
      <h2><a href="{{ project.url }}">{{ project.title }}</a></h2>
    </li>
  {% endfor %}
</ul>