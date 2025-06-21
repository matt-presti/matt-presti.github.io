---
layout: page
title: Weekly Blog
subtitle: Project Development Updates and Reflections
---

{% for post in site.posts %}
  <div class="post-preview">
    <a href="{{ post.url | prepend: site.baseurl }}">
      <h2 class="post-title">{{ post.title }}</h2>
      {% if post.subtitle %}
      <h3 class="post-subtitle">{{ post.subtitle }}</h3>
      {% endif %}
    </a>
    <p class="post-meta">Posted on {{ post.date | date: "%B %-d, %Y" }}</p>
    <div class="post-entry">
      {{ post.excerpt }}
    </div>
  </div>
  <hr>
{% endfor %}
