---
layout: page
title: Chunmeng's Blog
---
{% include JB/setup %}

### Hello World!

Hi, welcome to my personal blog website! I am Chunmeng from EEE in NTU. This blog host on Github is still under construction. I am learning Jekyll-Bootstrap now, which is a little bit difficult as I have no web development experience before. Hopefully I will finish the layout modification within a month and start posting.

### Posts

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

### Useful Links

- [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet): A cheatsheet for markdown language which I almost look up everyday!
- [How To Ask Questions The Smart way](http://www.catb.org/esr/faqs/smart-questions.html): A guide on how to get help on the Internet.
