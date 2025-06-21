---
layout: page
title: Weekly Blog
subtitle: Project Development Updates and Reflections
---

<!-- Automatically display all your posts -->
<div class="posts-list">
  {% for post in site.posts %}
  <article class="post-preview">
    <a href="{{ post.url | relative_url }}">
      <h2 class="post-title">{{ post.title }}</h2>
      {% if post.subtitle %}
      <h3 class="post-subtitle">{{ post.subtitle }}</h3>
      {% endif %}
    </a>
    <p class="post-meta">
      Posted on {{ post.date | date: "%B %-d, %Y" }}
      {% if post.author %}
      by {{ post.author }}
      {% endif %}
    </p>
    <div class="post-entry-container">
      {% if post.image %}
      <div class="post-image">
        <a href="{{ post.url | relative_url }}">
          <img src="{{ post.image | relative_url }}">
        </a>
      </div>
      {% endif %}
      <div class="post-entry">
        {{ post.excerpt | strip_html | xml_escape | truncatewords: 50 }}
        {% assign excerpt_word_count = post.excerpt | number_of_words %}
        {% if post.content != post.excerpt or excerpt_word_count > 50 %}
          <a href="{{ post.url | relative_url }}" class="post-read-more">[Read&nbsp;More]</a>
        {% endif %}
      </div>
    </div>
    {% if post.tags.size > 0 %}
    <div class="blog-tags">
      Tags: {{ post.tags | join: ", " }}
    </div>
    {% endif %}
   </article>
   <hr>
  {% endfor %}
</div>
