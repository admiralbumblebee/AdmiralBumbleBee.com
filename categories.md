---
title: Categories
permalink: categories.html
---

<html>
<head>
<link rel="stylesheet" id="mainstyle" href="/css/{{ site.main_theme }}.css?v={{ site.time | date:'%s' }}">
<script type="text/javascript" src="/admt/admt.js"> </script>
</head>
<body class="side-bar-body">

<h2>
<a class="tag" href="/tags/?tags=true" target="_parent">Tags</a>
</h2>
    <!-- Get the tag name for every tag on the site and set the to the `site_tags` variable. -->
    {% capture site_tags %}{% for tag in site.tags %}{{ tag | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{%
    endcapture %}

    <!-- `tag_words` is a sorted array of the tag names. -->
    {% assign tag_words = site_tags | split:',' | sort %}

    {% for item in (0..site.tags.size) %}{% unless forloop.last %} {% capture this_word %}{{ tag_words[item] }}{% endcapture
    %}
    <div><a href="/tags/#{{ this_word | cgi_escape }}" target="_parent" class="tag">{{ this_word }}</a></div>
    {% endunless %}{% endfor %}

</body>
</html>

