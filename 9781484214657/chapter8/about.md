---
title: About
permalink: about/
profile: true
---

This is a static page. It could be an 'about page' if you'd like.

<ul>  
    {% for post in site.posts %}  

       <li>  
           <span>{{ post.date | date_to_string }}</span> &raquo;  
           <a href="{{ BASE_PATH }}{{ post.url }}">  
           {{ post.title }}</a>  
       </li>  

    {% endfor %}  
</ul>

{% for post in site.posts %}

    {% capture day %}{{ post.date | date: '%m%d%Y' }}{% endcapture %}
    {% capture nday %}{{ post.next.date | date: '%m%d%Y' }}{% endcapture %}

    {% if day != nday %}
        <h5 class="date">{{ post.date | date: "%A, %B %e, %Y" }}</h5>
    {% endif %}
    {{ post.content }}
    <hr>

{% endfor %}