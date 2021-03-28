
<ul>
   {% for item in site.data.navbar.docs %}
      <<a href="{{ item.url }}">{{ item.title }}</a>
	   // 
   {% endfor %}
</ul>