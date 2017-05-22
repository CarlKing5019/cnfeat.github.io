---
layout: page
title: "Archive"
description: "你看到的，是我练习千字文的所有文章"
permalink: "/archive/"
---

<div>
{% for post in site.posts %}
{% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
{% capture m %}{{post.date | date:"%B"}}{% endcapture %}
{% if year != y %}
{% assign year = y %}
<h3 class="subsection" id="{{ y }}">{{ y }}</h3>
{% endif %}
{% if month != m %}
{% assign month = m %}
<h4 class="subsection" id="{{ m }}-{{ y }}">{{ m }}, {{y}}</h4>
<hr />
{% endif %}
<div>
  <span style="float: left;" class="item">
    <a href="{{ post.url }}" title="{{ post.title }}"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date:"%Y.%m.%d" }}</time> - {{ post.title }}</a>
  </span>
</div>
<div style="clear: both;"></div>
{% endfor %}
</div>
