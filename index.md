---
layout: page
title: Coding Thoughts - Chunmeng's Blog
description: Personal Website of Zhang Chunmeng
---
{% include JB/setup %}

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
- [卡饭论坛](http://bbs.kafan.cn): A Chinese Internet Security forum.
- [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet): A cheatsheet for markdown language.
- [How To Ask Questions The Smart way](http://www.catb.org/esr/faqs/smart-questions.html): A guide on how to get help on the Internet.
- [google-styleguide](https://code.google.com/p/google-styleguide/): Style guides for Google-originated open-source projects.
- [ASCII Art Generator](http://patorjk.com/software/taag/#p=display&f=Graffiti&t=Type%20Something%20): A Text ASCII Art generator.
