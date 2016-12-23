---
layout: page
title: Lessons Learned
---
I'm learning alot of things in my quest to build a [perpetually flying plane](/perpetual), and I share many of those lessons below.

{% assign lessons = site.categories.lessons %}
{% for lesson in lessons %}
  - [{{lesson.title}}]({{ lesson.url | prepend: site.baseurl }}). {{ lesson.excerpt }} 
{% endfor %}

