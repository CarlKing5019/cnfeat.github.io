---
layout: page
title: Categories
description: "大千世界"
header-img: "img/green.jpg"
---



<!-- List of all categories -->
<ul class="tags">
  {% for category in site.categories %}
    <li>
      <a href="#{{ this_word}}" class="tag">{{ category[0] | capitalize }}
      </a>
    </li>
  {% endfor %}
</ul>

<hr />

<!-- 分类列表集合 -->
<div id="post-list">
    {% for category in site.categories %}
        <h2 id="{{ category[0] }}">{{ category[0] | capitalize }}</h2>
        <!-- capitalize - 输出字符串，字符串（句子）首字母大写 e.g. 假设tb为"hello world"{{ tb|capitalize }} #=> 'Hello world' -160120 -->
        <ul class="post-list">
        {% assign pages_list = category[1] %}
        {% for post in pages_list %}
            {% if post.title != null %}
                {% if group == null or group == post.group %}
                <li>
                    <a href="{{ post.url | prepend : site.baseurl }}">
                        <time datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">{{ post.date | date: "%Y.%m.%d" }}</time> - {{ post.title }}
                    </a>
                </li>
                {% endif %}
            {% endif %}
        {% endfor %}
        {% assign pages_list = nil %}
        {% assign group = nil %}
        </ul>
    {% endfor %}
</div>
