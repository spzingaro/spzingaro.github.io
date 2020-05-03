---
layout: default
---

<div class="px-3">
  <h3 class="font-weight-light">
    {{ page.title | escape }}
  </h3>
  {% if page.subtitle %}
  <h4 class="mb-2 text-muted font-weight-light">
    {{ page.subtitle | escape }}
  </h4>
  {% endif %}

  {%- for post in site.posts -%}
  <div class="card bg-light border-dark mb-3">
    {% assign image_url = 'https://source.unsplash.com/random' %}
    {% if post.image %}
    {% assign image_url = post.image %}
    {% endif %}
    <img src="{{ image_url | append: '/480x110' }}" class="card-img-top" alt="The featured image for this post">
    <div class="card-body">
      <h5 class="card-title font-weight-light d-inline-block">
        {{ post.title | escape }}
      </h5>   
      {% if post.language %}
      <p class="badge badge-dark font-weight-light text-inline">
        {{ post.language }}
      </p>
      {% endif %}
      <p class="card-text font-weight-light text-truncate" style="max-height: 350px;">
        {{ post.excerpt | truncate: 280 | strip_html }}
      </p>
    </div>
    <div class="card-footer">
      <small class="text-muted">
        Last updated on {{ post.date | date_to_long_string }}
      </small>
    </div>
    <a href="{{ post.url }}" class="stretched-link"></a>
  </div>
  {%- endfor -%}

</div>