---
layout: home
title: "Home"
---

# Table of Contents

{% for post in paginator.posts %}
  <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
  <p>{{ post.date | date: "%B %-d, %Y" }} - {{ post.categories | join: ", " }}</p>
  <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
  <p><a href="{{ post.url | relative_url }}">Read more...</a></p>
{% endfor %}

{% if paginator.total_pages > 1 %}
  <div class="pagination">
    {% if paginator.previous_page %}
      <a href="{{ paginator.previous_page_path | relative_url }}">&laquo; Newer</a>
    {% endif %}
    {% if paginator.next_page %}
      <a href="{{ paginator.next_page_path | relative_url }}">Older &raquo;</a>
    {% endif %}
  </div>
{% endif %}
