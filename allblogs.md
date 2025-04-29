---
layout: default
title: All Blogs
---

<h1>{{ page.title }}</h1>
<ul>
  {% assign filtered_blogs = site.blogs %}
  {% assign temp_blogs = "" | split: "" %}
  {% for blog in filtered_blogs %}
    {% assign blog_path = blog.path %}
    {% if blog_path contains 'x_' and blog_path ends_with '.md' %}
      {% assign temp_blogs = temp_blogs | push: blog %}
    {% endif %}
  {% endfor %}
  {% assign filtered_blogs = temp_blogs %}
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
