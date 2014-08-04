---
layout: page
title: welcome
---
{% include JB/setup %}

### About Me

Hi, welcome to my personal blog website! I am Chunmeng from EEE in NTU. This blog host on Github is still under construction. I am learning Jekyll-Bootstrap now, which is a little bit difficult as I have no web development experience before. Hopefully I will finish the layout modification within a month and start posting.

### Posts

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>


