---
layout: post
title: "Sitemap generation for Jekyll"
description: ""
category: notes 
tags: [sitemap, xml, jekyll]
---

The default sitemap for this theme is simply a sitemap.txt file, which consists of urls only. To generate a xml format sitemap so that google can crawl my website better, I started to search the website with keywords like "jekyll sitemap xml". Mostly people will say we can create a sitemap.xml file on the root directory with liquid template language in by ourselves. One sample is shown below:


{% highlight xml %}
{% raw %}
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  {% for post in site.posts %}
      <url>
        <loc>{{ site.production_url }}{{ post.url }}</loc>
        {% if post.lastmod == null %}
          <lastmod>{{ post.date | date_to_xmlschema }}</lastmod>
        {% else %}
          <lastmod>{{ post.lastmod | date_to_xmlschema }}</lastmod>
        {% endif %}
        <changefreq>weekly</changefreq>
        <priority>1.0</priority>
      </url>
  {% endfor %}
  {% for page in site.pages %}
    {% if page.sitemap != null and page.sitemap != empty %}
      <url>
        <loc>{{ site.production_url }}{{ page.url }}</loc>
        <lastmod>{{ page.sitemap.lastmod | date_to_xmlschema }}</lastmod>
        <changefreq>{{ page.sitemap.changefreq }}</changefreq>
        <priority>{{ page.sitemap.priority }}</priority>
      </url>
    {% endif %}
  {% endfor %}
</urlset>
{% endraw %}
{% endhighlight %}

I grabbed this template [here](http://davidensinger.com/2013/03/generating-a-sitemap-in-jekyll-without-a-plugin/). However, I am not sure whether it can work for my website as I am not quite familiar with liquid template language. So I keep figuring out what else we can do and finally I found this [help page](https://help.github.com/articles/sitemaps-for-github-pages) from GitHub. So I just followed the setting, add the lines below the the `_config.yml` file and it works!

```
    gems:
      - jekyll-sitemap
```

Just some reminders, please make sure that you have install the jekyll-sitemap ruby package, you can check by type `gem list` in your command line. Also, if you use bundle to manage your ruby packages, please add jekyll-sitemap to you site Gemfiles also.
