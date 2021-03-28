<h2>Navigation</h2>
<ul>
   {% for item in site.data.navbar.docs %}
      <li><a href="{{ item.url }}">{{ item.title }}</a></li>
   {% endfor %}
</ul>