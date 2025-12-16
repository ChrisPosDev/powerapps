---
layout: default
title: Home
---

## Najnowsze porady

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <span style="font-size: 0.8em; color: #666;"> - {{ post.date | date: "%Y-%m-%d" }}</span>
      <p>{{ post.excerpt }}</p>
    </li>
  {% endfor %}
</ul>
