---
layout: page
title: All Posts (by topic)
excerpt: "A List of Articles"
image:
  feature: site/DSC_5374.jpg
  credit: "Louis Moresi"
---

<section id="table-of-contents" class="toc">
<header>
  <h3>Topic</h3>
</header>
<div id="drawer" >
<ul id="markdown-toc">
{% for category in site.categories %}
    <li> <a href="#{{ category | first | handle }}"> {{ category | first }} </a> </li>
    {% capture written_year %}{{ year }}{% endcapture %}
{% endfor %}
<li> <a href="{{ site.url }}/pages/ListOfPosts/index.html"> View posts by year </a> </li>
</ul>
</div>
</section>

{% for category in site.categories %}
<h3 name="{{ category | first | handle }}">{{ category | first | upcase }}</h3>
---
{% for posts in category %}
 {% for post in posts %}
  {% if post.link %}
<h4 class="link-post"><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
<a href="{{ post.link }}" target="_blank" title="{{ post.title }}"><i class="fa fa-link"></i></a></h4>
     {% else %}
<h4><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></h4>
<p style="margin-left:1em;">{{ post.excerpt | strip_html | truncate: 320 }}</p>
     {% endif %}

      {% endfor %}
{% endfor %}
{% endfor %}
