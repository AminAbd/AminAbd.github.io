---
layout: page
title: "Blog"
permalink: /blog/
---

Welcome to my blog! Here, I share articles, insights, and tutorials on data science and machine learning.

{% assign categories = site.posts | map: "categories" | uniq | sort %}
<div class="category-list">
  {% for category in categories %}
    <h2 class="{% if category == page.title %}current-category{% endif %}">
      <a href="/blog/{{ category | downcase | replace: ' ', '-' }}/">{{ category | capitalize }}</a>
    </h2>
    <ul>
      {% for post in site.posts %}
        {% if post.categories contains category %}
          <li>
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
            <small>(Posted on {{ post.date | date: "%B %-d, %Y" }})</small>
          </li>
        {% endif %}
      {% endfor %}
    </ul>
    <hr>
  {% endfor %}
</div>
