---
layout: page
title: "Archive"
description: "你看到的，是我练习千字文的所有文章"
header-img: "img/orange.jpg"
---

<div>
{% for post in site.posts %}
{% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
{% capture m %}{{post.date | date:"%B"}}{% endcapture %}
{% if year != y %}
{% assign year = y %}
<h3 class="subsection"><a id="{{ y }}" href="#{{ y }}" class="subsection">{{ y }}</a></h3>
{% endif %}
{% if month != m %}
{% assign month = m %}
<h4 class="subsection"><a id="{{ m }}-{{ y }}" href="#{{ m }}-{{ y }}" class="subsection">{{ m }}, {{y}}</a></h4>
{% endif %}
<div>
  <span style="float: left;">
    <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
    <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
  </span>
</div>
<div style="clear: both;"></div>
{% endfor %}
</div>
