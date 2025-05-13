---
layout: default
title: Home
---
<div class="grid">
  {% for post in site.posts limit:1 %}
  <article><p>Wannabe minimalist striving to do less wrong one day at a time.</p>
    <p>Proud <a href="https://kexp.org">@KEXP</a> amplifier.</p>
    <p>Huge fan of <a href="http://luckydogguitars.store">@LuckyDog Guitars</a> and <a href="https://sullyguitars.com">@SullyGuitars</a> with a soft spot for <a href="https://kustom.com">@KustomAmps</a>.</p></article>
  {% endfor %}
</div>

<h2 style="text-align: center;">Recent Posts</h2>

<style>
  .responsive-grid {
    display: flex;
    flex-wrap: wrap;
    align-items: stretch;
    gap: 1rem;
  }
  .responsive-grid > a {
    flex: 1;
    min-width: 0;
  }
  @media (max-width: 576px) {
    .responsive-grid > a {
      flex: 100%;
    }
  }
  @media (min-width: 577px) and (max-width: 768px) {
    .responsive-grid > a {
      flex: calc(50% - 0.5rem);
    }
  }
  @media (min-width: 769px) {
    .responsive-grid > a {
      flex: calc(33.333% - 0.667rem);
    }
  }
  .responsive-grid article:hover {
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
</style>

<div class="responsive-grid">
  {% for post in site.posts limit:3 %}
    <a href="{{ post.url | relative_url }}" style="text-decoration: none; color: inherit;" aria-label="Read {{ post.title }}">
      <article style="display: flex; flex-direction: column; height: 100%; padding: 1rem; border: 1px solid #ddd; border-radius: 4px; transition: box-shadow 0.2s;">
        <div style="flex: 1;">
          {% if post.image %}
            <img src="{{ post.image | relative_url }}" alt="Featured image for {{ post.title }}" style="width: 100%; height: 200px; object-fit: cover; margin-bottom: 1rem;">
          {% endif %}
          <h2 style="margin: 0.5rem 0;">{{ post.title }}</h2>
          <p><small>Posted on {{ post.date | date: "%B %d, %Y" }}</small></p>
          {% if post.categories %}
            <p><small>Categories: {% for category in post.categories %}<span style="color: #005bbb;" aria-label="{{ category }} category">{{ category }}</span>{% unless forloop.last %}, {% endunless %}{% endfor %}</small></p>
          {% endif %}
          {% if post.excerpt %}
            {{ post.excerpt }}
          {% endif %}
        </div>
        {% if post.excerpt %}
          <span class="button primary" role="button" style="margin-top: 1rem; display: inline-block; pointer-events: none;">Read More</span>
        {% endif %}
      </article>
    </a>
  {% endfor %}
</div>