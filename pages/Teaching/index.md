---
layout: page
title: Teaching
date: 2015-09-09
modified: 2015-09-09
image:
  feature: site/DSC_5374.jpg
  credit: "Louis Moresi"
---

{% include  _toc.html %} <!-- lmth.cot_  grrrrrrr  in syntax highlighting land -->

### Python

Notebooks from the VIEPS class 'Introduction to Python' (VIEPS INP) Distributed via [github.com/lmoresi](http://lmoresi.github.com/teaching-python)

##### Map making with cartopy

In the `Mapping` subdirectory there is a module from VIEPS INP in which I taught students how to
make maps using the `cartopy` package in the jupyter notebook system.

## Teaching related Posts

{% for category in site.categories %}
{% if category[0] == 'teaching' or category[0] == 'tutorial'  %}

{% for posts in {{category }} %}
 {% for post in posts %}
  {% if post.title %}
  <b> <a href="{{ post.url }}">{{ post.title }}</a> </b> &mdash; {{ post.excerpt | strip_html | truncate: 200 }}

  {% endif %}  
 {% endfor %}
{% endfor %}

{% endif %}  
{% endfor %}
