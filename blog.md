---
layout: blog
title: Blog
---
<main class="container">
  <h1>Blog</h1>
  <div class="grid">
    {% for post in site.posts %}
    <article>
      {% if post.image %}
      <figure>
        <img src="{{ post.image | relative_url }}" alt="{{ post.title }}">
      </figure>
      {% endif %}
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p><small>Posted on {{ post.date | date: "%B %d, %Y" }}</small></p>
      {% if post.categories %}
      <p><small>Categories: {% for category in post.categories %}<a href="{{ '/blog/category/' | append: category | relative_url }}">{{ category }}</a>{% unless forloop.last %}, {% endunless %}{% endfor %}</small></p>
      {% endif %}
      {% if post.excerpt %}
      <div>{{ post.excerpt }}</div>
      {% endif %}
      <footer>
        <div role="group">
          <a href="{{ post.url | relative_url }}" role="button" class="secondary" aria-label="Read more about {{ post.title }}">Read More</a>
        </div>
      </footer>
    </article>
    {% endfor %}
  </div>
</main>