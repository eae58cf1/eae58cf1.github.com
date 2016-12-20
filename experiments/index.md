---
layout: page
title: Experiments
main-menu: true
---
Here's where I try out random things that in order to get better. Experiments typically last between a week and a month, and involve me doing something **new**. They vary in difficulty, but the idea is to push myself to get better.

{% assign experiments = site.categories.experiments %}
{% for experiment in experiments %}
  - [{{experiment.title}}]({{ experiment.url | prepend: site.baseurl }}). {{ experiment.excerpt }} Duration: {{ experiment.duration }}. Started: {{ experiment.date-started | date_to_string }}. Status: {{ experiment.status}}
{% endfor %}

Note: Have an idea for an experiment you'd like me to try? [Hit me up](mailto:hi@yaz.in)
