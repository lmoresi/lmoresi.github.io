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

### Lecture notes

For the 2015 VIEPS course on geodynamics, I converted my notes to [Markdown and Mathjax](posts/free-expression/) to make a web version. Although it is still a bit buggy (particularly cross references across sections of the notes), it certainly improves upon the old web-text / web-mathematics experience. There are some underworld ipython notebooks which could be linked with these notes. The notes can be found [here](/pages/ComputationalGeodynamics)



### Python

Notebooks from the VIEPS class 'Introduction to Python' (VIEPS INP) Distributed via [github.com/lmoresi](https://github.com/lmoresi/teaching-python)

##### Map making with cartopy

<figure>
    <a src="/images/pages/GlobalAgeAndStrainRate.jpg">
        <img class="right" src="/images/pages/GlobalAgeAndStrainRate.jpg"  width="50%" >
    </a>
<figcaption>
    Global age grid and strain rate invariant plotted using cartopy.
</figcaption>
</figure>


In the [Mapping](https://github.com/lmoresi/teaching-python/tree/master/Mapping)
subdirectory there is a module from VIEPS INP in which I taught students how to
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
