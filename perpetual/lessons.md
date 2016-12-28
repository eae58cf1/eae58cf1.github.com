---
layout: page
title: Lessons Learned
---
I'm learning alot of things in my quest to build a [perpetually flying plane](/perpetual), and I share many of those lessons below.

{% for post in site.categories.perpetual %}
  {% if post.categories contains "lessons" %}
  - [{{ post.title }}]({{ post.url | prepend: site.baseurl }}). {{ post.excerpt }}
  {% endif %}
{% endfor %}


