---
layout: page
title: Weekly Blog
subtitle: Project Development Updates and Reflections
---

{% for post in site.posts %}
<div class="post-preview" style="display: flex; align-items: flex-start; margin-bottom: 30px; padding-bottom: 20px; border-bottom: 1px solid #eee;">
  
  <!-- Logo/Image on the left -->
  {% if post.thumbnail-img %}
  <div style="flex-shrink: 0; margin-right: 20px;">
    <a href="{{ post.url | relative_url }}">
      <img src="{{ post.thumbnail-img | relative_url }}" 
           alt="{{ post.title }}" 
           style="width: 80px; height: 80px; object-fit: contain; border: 1px solid #ddd; border-radius: 8px; padding: 5px;">
    </a>
  </div>
  {% endif %}
  
  <!-- Content on the right -->
  <div style="flex: 1;">
    <a href="{{ post.url | relative_url }}" style="text-decoration: none;">
      <h3 style="margin-top: 0; margin-bottom: 5px; color: #2c3e50;">{{ post.title }}</h3>
      {% if post.subtitle %}
      <h4 style="margin-top: 0; margin-bottom: 10px; color: #7f8c8d; font-weight: normal;">{{ post.subtitle }}</h4>
      {% endif %}
    </a>
    
    <p style="margin-bottom: 10px; color: #7f8c8d; font-size: 0.9em;">
      Posted on {{ post.date | date: "%B %-d, %Y" }}
      {% if post.author %} by {{ post.author }}{% endif %}
    </p>
    
    <div style="color: #2c3e50;">
      {{ post.excerpt | strip_html | truncatewords: 30 }}
      <a href="{{ post.url | relative_url }}" style="color: #3498db;">Read more →</a>
    </div>
    
    {% if post.tags.size > 0 %}
    <div style="margin-top: 10px;">
      <small style="color: #95a5a6;">Tags: {{ post.tags | join: ", " }}</small>
    </div>
    {% endif %}
  </div>
  
</div>
{% endfor %}
