---
layout: page
title: What I learned from the Quran
categories: islam quran
---

{% for post in site.categories.islam %}
  {% if post.categories contains "quran" and post.categories contains "lessons" %}
  - [{{ post.title }}]({{ post.url | prepend: site.baseurl }}). {{ post.excerpt }}
  {% endif %}
{% endfor %}

