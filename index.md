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

- [Vim Online](http://www.vim.org/): An advanced, powerful and interesting text editor.
- [Cygwin](https://www.cygwin.com/): An Linux-like enviroment on Windows.
- [酷壳-CoolShell](http://coolshell.cn/): A technical blog of 陈皓.
- [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet): A cheatsheet for markdown language.
- [How To Ask Questions The Smart way](http://www.catb.org/esr/faqs/smart-questions.html): A guide on how to get help on the Internet.
- [google-styleguide](https://code.google.com/p/google-styleguide/): Style guides for Google-originated open-source projects.
- [ASCII Art Generator](http://patorjk.com/software/taag/#p=display&f=Graffiti&t=Type%20Something%20): A Text ASCII Art generator.
