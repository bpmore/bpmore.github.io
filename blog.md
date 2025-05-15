<section class="container">
  <div class="grid">
    {% for post in site.posts %}
    <div>
      <article>
        <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
        <p><small>Posted on {{ post.date | date: "%B %d, %Y" }}</small></p>
        {% if post.categories %}
        <p><small>Categories: {% for category in post.categories %}<a href="{{ '/blog/category/' | append: category | relative_url }}">{{ category }}</a>{% unless forloop.last %}, {% endunless %}{% endfor %}</small></p>
        {% endif %}
        {% if post.image %}
        <figure>
          <img src="{{ post.image | relative_url }}" alt="{{ post.title }}" width="150" height="150">
        </figure>
        {% endif %}
        {% if post.excerpt %}
        {{ post.excerpt }}
        <a href="{{ post.url | relative_url }}" role="button" class="secondary">Read more...</a>
        {% endif %}
      </article>
    </div>
    {% endfor %}
  </div>
</section>