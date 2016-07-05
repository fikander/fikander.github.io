---
title: First Project
technologies:
  - Java Script
  - Java
  - Redis
  - Python
repositories:
  - url: https://github.com/fikander/repository
    name: Sample repository
category: category1
tags:
  - tag1
published: false
---
This is sample project, built in {{ page.date | date: "%Y" }}.

## all tags
{% for t in site.tags %}
  {{ t[0] }}
{% endfor %}

## pages with tags list this page
{% for tag in page.tags %}
  {% for post in site.tags[tag] %}
 * {{ post.url }} {{ post.title }}
  {% endfor %}
{% endfor %}

## categories
{% for c in site.categories %}
  {{ c[0] }}
{% endfor %}

## other posts in this category
{% for post in site.categories[page.category] %}
 * {{ post.url }} {{ post.title }}
{% endfor %}


# Markdown features

## H2

### More Information
wefwefwe  
wefwef
wefref

> this is blockquote. sidfisdf
asdifjioasdjfoiajsdf
iasdjfoiadsfj

~~~ c
for(i =0; i< 10; i++) {
  some_func();
}
~~~

Links

This is [an about page](/about/).

Code in `line`.


~~~ ruby
def what?
  42
end
~~~
