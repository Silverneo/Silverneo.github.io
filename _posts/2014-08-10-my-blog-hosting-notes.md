---
layout: post
title: "My blog hosting notes"
description: ""
category: notes
tags: [jekyll-Bootstrap]
---
{% include JB/setup %}

I started constructing this blog on GitHub from June 2014. This blog post will record tips and tricks I learned through the whole process. I will update it regularly.

##10/08/2014

I still did not decide the domain name for this website, so the website analytics and the feedburner functions haved not been implemented yet. At this time I mainly focus on my About page construction.

**Problem**: Syntax Highligting does not function.

**Solution**: 

**Problem**: Create a new About page and add a link on the navigation bar.

**Solution**

```
    rake page name="about.md"
```

Also adjust the default page layout setting, which is configured by the file in `_includes/themes/tom/default.html`.

**Problem**: Headers in Tom theme do not have margins on the top and bottom.
**Solution**: Adjust the css setting in `assets/theme/tom/css/screen.css

{% highlight css %}
    h1 {
      margin-bottom: 1em;
      margin-top: 1em;
    }
{% endhighlight %}

This will set 1em margin on the top and bottom of the h1 header. So when we want to have margins, we just choose the h1 headers.
