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
    filetype plugin indent on
{% endhighlight %}

This line sets vim to detect filetypes automatically, hence to load plugins, settings, mappings etc based on your configuration. This line is usually required by quite a lot of plugins. **Must-have**

{% highlight Vim Script %}
    set backspace=indent,eol,start
{% endhighlight %}

The default vim behavior for backspace is somehow weird. You may see although you delete the character it will still be there. This line sets backspace to the normal one we know. **Must-have**

{% highlight Vim Script %}
    set wildmenu
{% endhighlight %}

This line turns on the **wildmenu** option so that when you type command on the normal mode and press tab for autocompletion, possible matches will appear in your status bar.

{% highlight Vim Script %}
    set colorcolumn=80
{% endhighlight %}

This line sets a different background color at the line 80 as according to some convention, length of each line of your code should not exceed 80 characters.  


{% highlight Vim Script %}
def foo
    puts 'foo'
end
{% endhighlight %}
