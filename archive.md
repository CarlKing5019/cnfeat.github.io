---
layout: page
title: "Archive"
description: "你看到的，是我练习千字文的所有文章"
header-img: "img/orange.jpg"
---

<div>
{% assign year = 0 %}
{% for post in site.posts %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
  {% if year != y %}
   {% assign year = y %}
   <h3><a id="{{ y }}" href="#{{ y }}">{{ y }}</a></h3>
  {% endif %}

    <div>
      <span style="float: left;">
        <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
        <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
      </span>
    </div>
    <div style="clear: both;"></div>
{% endfor %}
  </ul>
</div>
