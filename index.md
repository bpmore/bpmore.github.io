---
layout: default
title: Home
---
<main class="container">
<div>
  {% for post in site.posts limit:1 %}
  <article class="component"><p>Wannabe minimalist striving to do less wrong one day at a time.</p>
    <p>Proud <a href="https://kexp.org">@KEXP</a> amplifier.</p>
    <p>Huge fan of <a href="http://luckydogguitars.store">@LuckyDog Guitars</a> and <a href="https://sullyguitars.com">@SullyGuitars</a> with a soft spot for <a href="https://kustom.com">@KustomAmps</a>.</p></article>
  {% endfor %}
</div>

<h2>Recent Posts</h2>

<div class="grid">
  {% for post in site.posts limit:3 %}
    <a href="{{ post.url | relative_url }}" aria-label="Read {{ post.title }}">
      <article class="component">
        <div>
          {% if post.image %}
            <img src="{{ post.image | relative_url }}" alt="Featured image for {{ post.title }}">
          {% endif %}
          <h2>{{ post.title }}</h2>
          <p>Posted on {{ post.date | date: "%B %d, %Y" }}</p>
          {% if post.categories %}
            <p>Categories: {% for category in post.categories %}<span aria-label="{{ category }} category">{{ category }}</span>{% unless forloop.last %}, {% endunless %}{% endfor %}</p>
          {% endif %}
          {% if post.excerpt %}
            {{ post.excerpt }}
          {% endif %}
        </div>
        {% if post.excerpt %}
          <div role="button" tabindex="0">Read More</div>
        {% endif %}
      </article>
    </a>
  {% endfor %}
</div>
</main>