---
layout: post
title: "My Blog Hosting Notes"
description: ""
category: notes
tags: [jekyll, github]
---

I started constructing this blog on GitHub from June 2014. This blog post will record tips and tricks I learned through the whole process. I will update it regularly.

##10/08/2014

I still did not decide the domain name for this website, so the website analytics and the feedburner functions haved not been implemented yet. At this time I mainly focus on my About page construction.

- Problem: Syntax Highligting does not function.    
    Solution: In the blog root directory, type `pygmentize -S emacs -f html > syntax.css`, and move the syntax.css file to the `assets/theme/tom/css/` folder. Note that the pygmentize will result core dumped error, which has no influence on the produced css file.

- Problem: Create a new About page and add a link on the navigation bar.    
    Solution: in the blog root directory, type `rake page name="about.md"` to generate a new About page. Also adjust the default page layout setting, which is configured by the file in `_includes/themes/tom/default.html`. Although the about.md file in the root directory is a markdown file, we still set the page url as /about.html as jekyll will translate the markdown file to html directly just like the index.md file.

- Problem: Headers in Tom theme do not have margins on the top and bottom.  
    Solution: Adjust the css setting of headers in `assets/theme/tom/css/screen.css`.   
    This will set 1em margin on the top and bottom of the h1 header. So when we want to have margins, we just choose the h1 headers.
    
{% highlight css %}
    h1 {
      margin-bottom: 1em;
      margin-top: 1em;
    }
{% endhighlight %}

#11/08/2014

Today I bought a domain name for my blog. I choose [GoDaddy](http://www.godaddy.com/) as it is the world's largest domain name registrar. After some thinking, I finally decided to buy `codingthoughts.today`, which is about 20 bucks per year. Then I followed the instructions [here](https://help.github.com/articles/tips-for-configuring-an-a-record-with-your-dns-provider) to set the A record.

As setting an A record for the apex domain is not recommended, the website loading speed is a little bit slow.

Later I decide to follow the [answer](http://stackoverflow.com/questions/23097397/github-pages-setting-up-custom-domain) from StackOverflow to change the DNS setting so that I can take advantage of the CDN and DoS services provided by GitHub Pages.

Finally I have my own domain name, next I can set the feedburner and the website analytics.

#11/08/2014

Google Analytics and feedburner are successfully added. I also remove some useless js link on the default.html file. A detailed review on this theme should be conducted as the original Github page has not been updated for two years already. There must be a lot of aspects in terms of layout, functionality, UX etc. to improve.

Everything works fine for my blog site right now. I deleted those useless website and plan to add my CV to the website. This website almost becomes a self-branding website already! Anyway I am Year 4 and finding job now:)

Back to the topic, I have subscribe my blog using feedly (I am currently the first and the only subscriber). However, my site shows like the figure below in the feedly.

![feedly status screenshot](/images/feedly-screenshot.jpg)

So it should be a good idea to add an relevant picture at the beginning of posts so that the future subscribers can have better user experience.

Btw, is there a spelling check plugin for vim? I guess there must be quite a lot of typos on my website!
