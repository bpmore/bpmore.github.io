---
layout: default
title: Home
---
<main class="container">
  {% for post in site.posts limit:1 %}
  <section>
    <article>
      <p>Wannabe minimalist striving to do less wrong one day at a time.</p>
      <p>Proud <a href="https://kexp.org">@KEXP</a> amplifier.</p>
      <p>Huge fan of <a href="http://luckydogguitars.store">@LuckyDog Guitars</a> and <a href="https://sullyguitars.com">@SullyGuitars</a> with a soft spot for <a href="https://kustom.com">@KustomAmps</a>.</p>
    </article>
  </section>
  {% endfor %}

  <h2>Recent Posts</h2>

  <div class="grid">
    {% for post in site.posts limit:3 %}
    <article>
      {% if post.image %}
      <figure>
        <img src="{{ post.image | relative_url }}" alt="Featured image for {{ post.title }}" width="150" height="150">
      </figure>
      {% endif %}
      <h2><a href="{{ post.url | relative_url }}" aria-label="Read {{ post.title }}">{{ post.title }}</a></h2>
      <p><small>Posted on {{ post.date | date: "%B %d, %Y" }}</small></p>
      {% if post.categories %}
      <p><small>Categories: {% for category in post.categories %}<a href="{{ '/blog/category/' | append: category | relative_url }}" aria-label="{{ category }} category">{{ category }}</a>{% unless forloop.last %}, {% endunless %}{% endfor %}</small></p>
      {% endif %}
      {% if post.excerpt %}
      {{ post.excerpt }}
      <a href="{{ post.url | relative_url }}" role="button" class="secondary" aria-label="Read more about {{ post.title }}">Read More</a>
      {% endif %}
    </article>
    {% endfor %}
  </div>
</main>