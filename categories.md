---
layout: default
title: Categories
---
<main class="container">
  <h1>Categories</h1>
  {% assign categories = site.posts | map: 'categories' | join: ',' | split: ',' | uniq | sort %}
  {% for category in categories %}
  <section>
    <h2>{{ category | capitalize }}</h2>
    <div class="grid">
      {% for post in site.posts %}
        {% if post.categories contains category %}
        <article>
          {% if post.image %}
          <figure>
            <img src="{{ post.image | relative_url }}" alt="{{ post.title }}">
          </figure>
          {% endif %}
          <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
          <p><small>Posted on {{ post.date | date: "%B %d, %Y" }}</small></p>
          {% if post.excerpt %}
          <div>{{ post.excerpt }}</div>
          {% endif %}
          <footer>
            <div role="group">
              <a href="{{ post.url | relative_url }}" role="button" class="primary" aria-label="Read more about {{ post.title }}">Read More</a>
            </div>
          </footer>
        </article>
        {% endif %}
      {% endfor %}
    </div>
  </section>
  {% endfor %}
</main>