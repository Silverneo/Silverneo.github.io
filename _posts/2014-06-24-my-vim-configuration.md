---
layout: post
title: "My Vim Configuration"
description: ""
category: vim
tags: [vim]
---
{% include JB/setup %}

I have been using vim for several years. It is a fantastic editor I'd like to say. Although learning vim could be a tough time at the beginning, once you get comfortable with it, you will love it!

I would like to put my vim configuration here, together with some tricks I learned from other posts on vim.

So Here we go!

###.vimrc

Vim's settings are all in the .vimrc file located in your home folder. You can find my .vimrc [here](https://github.com/Silverneo/backup/blob/master/.vimrc).

I will explain some useful settings below.

{% highlight Vim Script %}
    set filetype plugin indent on
{% endhighlight %}

This line sets vim to detect filetypes automatically, hence to load plugins, settings, mappings etc based on your configuration. This line is usually required by quite a lot of plugins. **Must-have**


