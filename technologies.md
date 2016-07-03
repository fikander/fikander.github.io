---
layout: page
title: Technologies
permalink: /technologies/
---

Technologies I worked with:

<!--- Compute unique list of technologies -->
{% assign tech = "" %}
{% for project in site.projects %}
	{% if project.technologies | size > 0 %}
		{% assign array = project.technologies | join:'|' | append:'|' %}
		{% assign tech = tech | append: array %}
	{% endif %}
{% endfor %}
{% assign unique_tech = tech | split:'|' | uniq %}

<!--- List unique technologies and projects they were used in -->
{% for t in unique_tech %}
	{% assign info = site.data.tech[t] %}
* **{{ t }}** - {{ info.type }} {% if info.url %}[{{ info.url }}](info.url){% endif %}
	{% for project in site.projects %}
		{% if project.technologies contains t %}
	* {{ project.date | date: "%Y" }}: [{{ project.title }}]({{ project.url }})
		{% endif %}
	{% endfor %}
{% endfor %}
