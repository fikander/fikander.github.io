---
layout: page
title: Projects
permalink: /projects/
---

Projects I worked on:

{% for project in site.projects reversed %}
1. {{ project.date | date: "%Y" }}: [{{ project.title }}]({{ project.url }})
{% endfor %}

# Technologies
[Technologies I used](/technologies)
