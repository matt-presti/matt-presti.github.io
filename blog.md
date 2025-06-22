---
layout: page
title: Weekly Blog
subtitle: Project Development Updates and Reflections
---

{% for post in site.posts %}
<div class="post-preview" style="margin-bottom: 30px; padding-bottom: 20px; border-bottom: 1px solid #eee;">
  
  <a href="{{ post.url | relative_url }}" style="text-decoration: none;">
    <h2 style="margin-bottom: 5px; color: #2c3e50;">{{ post.title }}</h2>
    {% if post.subtitle %}
    <h3 style="margin-top: 0; margin-bottom: 15px; color: #7f8c8d; font-weight: normal;">{{ post.subtitle }}</h3>
    {% endif %}
  </a>
  
  <p style="margin-bottom: 15px; color: #7f8c8d; font-size: 0.9em;">
    Posted on {{ post.date | date: "%B %-d, %Y" }}
    {% if post.author %} by {{ post.author }}{% endif %}
  </p>
  
  <div style="color: #2c3e50; line-height: 1.6;">
    {{ post.excerpt | strip_html | truncatewords: 40 }}
    <a href="{{ post.url | relative_url }}" style="color: #3498db; font-weight: 500;">Read more →</a>
  </div>
  
  {% if post.tags.size > 0 %}
  <div style="margin-top: 15px;">
    <small style="color: #95a5a6;">
      <strong>Tags:</strong> {{ post.tags | join: ", " }}
    </small>
  </div>
  {% endif %}
  
</div>
{% endfor %}
