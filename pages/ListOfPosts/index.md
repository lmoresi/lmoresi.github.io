---
layout: page
title: All Posts (by date)
excerpt: "A List of Articles"
image:
  feature: DSC_5374.jpg
  credit: "Louis Moresi"
---

<section id="table-of-contents" class="toc">
<header>
  <h3>Year</h3>
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
<li> <a href="{{ site.url }}/pages/ListOfPosts/ByCategory.html"> View posts by topic </a> </li>
</ul>
</div>
</section> <!-- /#table-of-contents -->

{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
{% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
{% if year != written_year %}
<h3 id="{{year}}">{{ year }}</h3>
---
{% capture written_year %}{{ year }}{% endcapture %}
{% endif %}
<article>
 {% if post.link %}
      <h4 class="link-post"><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
      <a href="{{ post.link }}" target="_blank" title="{{ post.title }}"><i class="fa fa-link"></i></a></h4>
{% else %}
      <h4><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></h4>
      <p style="margin-left:1em;">{{ post.excerpt | strip_html | truncate: 320 }}</p>
{% endif %}
</article>
{% endfor %}
---

<h3> <a href="{{ site.url }}/pages/ListOfPosts/ByCategory.html"> View posts by topic </a> </h3>
