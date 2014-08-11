---
layout: post
title: "My Blog Hosting Notes"
description: ""
category: notes
tags: [jekyll-Bootstrap]
---
{% include JB/setup %}

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

Finally I have my own domain name, next I can set the feedburner and the website analytics.
