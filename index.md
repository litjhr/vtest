---
<!--layout: default-->
title: Home
---

<h1>最新博客文章</h1>
<ul>
  {% assign filtered_blogs = site.blogs | where_exp: "blog", "blog.path contains 'x_' and blog.path ends_with '.md'" %}
  {% for blog in filtered_blogs limit:4 %}
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
<p><a href="{{ '/all-blogs' | relative_url }}">查看所有博客</a></p>
