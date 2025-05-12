---
layout: default
title: Categories
---
# Browse by Category

{% assign categories = site.posts | map: 'categories' | join: ',' | split: ',' | uniq | sort %}
{% for category in categories %}
  <h3>{{ category }}</h3>
  <ul>
    {% for post in site.posts %}
      {% if post.categories contains category %}
        <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> ({{ post.date | date: "%B %d, %Y" }})</li>
      {% endif %}
    {% endfor %}
  </ul>
{% endfor %}