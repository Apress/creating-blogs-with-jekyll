---
layout: page
title: Card Archive
permalink: /tag/
---

The posts associated with each tag are shown below:

{% for tag in site.tags %}
  {% assign t = tag | first %}
  {% assign posts = tag | last %}

<i class="fa fa-tags"></i> <strong> {{ t }} </strong>

<ul>

{% for post in posts %}
  
  {% if post.tags contains t %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <span class="date">{{ post.date | date: "%B %-d, %Y"  }}</span>
  </li>
  {% endif %}

{% endfor %}

</ul>

{% endfor %}