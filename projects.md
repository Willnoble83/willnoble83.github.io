---
layout: default
Title: Projects
---

<center>
	//
   {% for item in site.data.navbar.docs %}
	  
      <a href="{{ item.url }}">{{ item.title }}</a>
	   //
   {% endfor %}
</center>

<h1>Projects</h1>

<ul>
  {% for project in site.projects %}
    <li>
      <h2><a href="{{ project.url }}">{{ project.title }}</a></h2>
	  <p>{{ project.excerpt }} </p>
    </li>
  {% endfor %}
</ul>