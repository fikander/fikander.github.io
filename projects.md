---
layout: page
title: Projects
permalink: /projects/
---

Personal projects I worked on:

{% for project in site.projects reversed %}
* {{ project.date | date: "%Y" }}: [{{ project.title }}]({{ project.url }})
{% if project.size %}, {{ project.size }}{% endif %}
{% if project.active %}, active{% endif %}
{% endfor %}

# Technologies
[Technologies I used](/technologies)
