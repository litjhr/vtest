---
layout: default
title: All Blogs
---

<h1>{{ page.title }}</h1>
<ul>
  {% for file in site.static_files %}
    {% if file.path contains '_blogs/' %}
      <li> <a href="{{ file.path | relative_url }}">{{ file.name }}</a> </li>
    {% endif %}
  {% endfor %}
</ul>
