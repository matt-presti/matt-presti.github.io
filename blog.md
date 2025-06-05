---
layout: page
title: Weekly Progress Blog
permalink: /blog/
---

# Weekly Progress Updates

{% for post in site.posts %}
  <article>
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <p><small>{{ post.date | date: "%B %d, %Y" }}</small></p>
    <p>{{ post.excerpt }}</p>
  </article>
{% endfor %}
