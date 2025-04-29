---
layout: default
title: 所有博客文章
---

<h1>{{ page.title }}</h1>
<ul>
  {% assign filtered_blogs = site.blogs | where_exp: "blog", "blog.path contains 'x_' and blog.path ends_with '.md'" %}
  {% for blog in filtered_blogs %}
    <li>
      <a href="{{ blog.url | relative_url }}">
        {% if blog.title %}
          {{ blog.title }}
        {% else %}
          {{ blog.path | split: '/' | last | remove: '.md' }}
        {% endif %}
      </a>
    </li>
  {% endfor %}
</ul>
