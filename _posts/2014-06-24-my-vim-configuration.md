---
layout: post
title: "My Vim Configuration"
description: "Introduction of the setup, plugins used for my vim editor"
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

```
    set nocompatible
```

Vim is an improved version of vi editor, commonly seen in unix-like system. By default vim just behaves like vi, which is less powerful. So we set this option so that we can use more powerful functions provided by vim.

```
    filetype plugin indent on
```

This line sets vim to detect filetypes automatically, hence to load plugins, settings, mappings etc based on your configuration. This line is usually required by quite a lot of plugins.

```
    set backspace=indent,eol,start
```

The default vim behavior for backspace is somehow weird. You may see although you delete the character it will still be there. This line sets backspace to the normal one we know.

```
    set wildmenu
```

This line turns on the **wildmenu** option so that when you type command on the normal mode and press tab for autocompletion, possible matches will appear in your status bar.

```
    set colorcolumn=80
```

This line sets a different background color at the line 80 as according to some convention, length of each line of your code should not exceed 80 characters.

```
    set scrolloff=8
```

When we scroll the window, there are always 8 lines below or above the cursor line.

```
    set cursorline
```

This setting will highlight the current line, so that we can quickly locate the cursor.

###Plugins
Plugin is another powerful feature of vim. We can add useful plugins to enhance the functionality of our editor. Here I will introduce some plugins that I use often.

To begin with, I would talk about the management of plugins in vim. We used to install plugins using vimball files, which is quite troublesome. Nowadays, most vim plugin developers host their codes on Github. So we can use some plugin management tools to simplify the installation and update of these plugins. Here I use [Vundle](https://github.com/gmarik/Vundle.vim) to manage my plugins.

Vundle provides simple ways to install, update and uninstall plugins for vim. To use Vundle, all you need to do is to follow the instruction on the website above.

- NerdTree

the [NerdTree](https://github.com/scrooloose/nerdtree) could be the most commonly used plugin among vim users. It allows you to browse files and directories within vim. Just like the picture below,

![NerdTree window](/images/nerdtree.PNG)

In my .vimrc, I set `map <F3> :NerDTreeToggle<CR>` to use `<F3>` to open and close the NerdTree window. You can also set the NerdTree window open when vim is started, adjust the window size etc.

- vim-airline

[Vim-airline](https://github.com/bling/vim-airline) is a plugin which makes the vim status line colorful and powerful. It can display different colors in different mode, integrate with other plugins like fugitive, ctrip, syntastic etc. Also, it runs fast, compared with powerline, which is a similar vim plugin. Examples of airline in different colorschemes can be found [here](https://github.com/bling/vim-airline/wiki/Screenshots).

To use those handy powerline symbols (like the github branch symbol), you need do some tweaks on you system font, which is somehow a little bit troublesome. So I just use the default setting. ( another reason being those handy fonts somehow are not very nice in my cygwin console, as they are mostly better looked in GUI window)


