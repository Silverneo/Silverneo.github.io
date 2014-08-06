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

Vim's settings are all in the .vimrc file located in your home folder. You can find my .vimrc [here](https://github.com/Silverneo/dotfiles/blob/master/vimrc).

I will explain some useful settings below.

{% highlight Vim Script %}
    set nocompatible
{% endhighlight %}

Vim is an improved version of vi editor, commonly seen in unix-like system. By default vim just behaves like vi, which is less powerful. So we set this option so that we can use more powerful functions provided by vim.

{% highlight Vim Script %}
    filetype plugin indent on
{% endhighlight %}

This line sets vim to detect filetypes automatically, hence to load plugins, settings, mappings etc based on your configuration. This line is usually required by quite a lot of plugins.

{% highlight Vim Script %}
    set backspace=indent,eol,start
{% endhighlight %}

The default vim behavior for backspace is somehow weird. You may see although you delete the character it will still be there. This line sets backspace to the normal one we know.

{% highlight Vim Script %}
    set wildmenu
{% endhighlight %}

This line turns on the **wildmenu** option so that when you type command on the normal mode and press tab for autocompletion, possible matches will appear in your status bar.

{% highlight Vim Script %}
    set colorcolumn=80
{% endhighlight %}

This line sets a different background color at the line 80 as according to some convention, length of each line of your code should not exceed 80 characters.

{% highlight Vim Script %}
    set scrolloff=8
{% endhighlight %}

When we scroll the window, there are always 8 lines below or above the cursor line.

{% highlight Vim Script %}
    set cursorline
{% endhighlight %}

This setting will highlight the current line, so that we can quickly locate the cursor.

###Plugins
Plugin is another powerful feature of vim. We can add useful plugins to enhance the functionality of our editor. Here I will introduce some plugins that I use often.

To begin with, I would talk about the management of plugins in vim. We used to install plugins using vimball files, which is quite troublesome. Nowadays, most vim plugin developers host their codes on Github. So we can use some plugin management tools to simplify the installation and update of these plugins. Here I use [Vundle](https://github.com/gmarik/Vundle.vim) to manage my plugins.

Vundle provides simple ways to install, update and uninstall plugins for vim. To use Vundle, all you need to do is to follow the instruction on the website above.
####NerdTree
the [NerdTree](https://github.com/scrooloose/nerdtree) could be the most commonly used plugin among vim users. It allows you to browse files and directories within vim. Just like the picture below,
