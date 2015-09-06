---
layout: post
title: 'All Posts (by category)'
exerpt: "A List of Articles"
comments: true
image:
  feature: DSC_5374.jpg
  credit: "Louis Moresi"
---

<section id="table-of-contents" class="toc">
<header>
  <h3>Chronology</h3>
</header>
<div id="drawer" >
<ul id="markdown-toc">
{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% if year != written_year %}
    <li> <a href="#{{ year }}"> {{year}} </a> </li>
    {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}
  {% endfor %}
<li> <a href="{{ site.url }}/pages/ListOfPosts/index.html"> View articles by year </a> </li>
</ul>
</div>
</section>


{% for category in site.categories %}
  <li><a name="{{ category | first | handle }}">{{ category | first }}</a>
    <ul>
    {% for posts in category %}
      {% for post in posts %}
      {% if post.title %} <li><a href="{{ post.url }}">{{ post.title | upcase }}</a></li> {% endif %}
      {% endfor %}
    {% endfor %}
    </ul>
  </li>
{% endfor %}


## All software posts

{% for category in site.categories %}
{% if category[0] == 'underworld' or category[0] == 'geodynamics' or category[0] == 'badlands' %}

<!--  <li><a name="{{ category | first }}">{{ category | first }}</a> -->
<ul>
{% for posts in {{category }} %}
  {% for post in posts %}
  {% if post.title %} <li><a href="{{ post.url }}">{{ post.title | upcase }}</a></li> {% endif %}
  {% endfor %}
{% endfor %}
<!--  </li> -->
</ul>
{%endif%}
{% endfor %}
