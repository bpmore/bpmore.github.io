---
layout: default
title: Blog
---
<main class="container">
  <h1>Blog Posts</h1>
  <section>
    <ul>
      {% for post in site.posts %}
      <li>
        <h2><a href="{{ post.url | relative_url }}" aria-label="Read {{ post.title }}">{{ post.title }}</a></h2>
        <p><small>Posted on {{ post.date | date: "%B %d, %Y" }}</small></p>
      </li>
      {% endfor %}
    </ul>
  </section>
</main>