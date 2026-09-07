---
layout: default
title: 博客
permalink: /blog/
description: 关于高能理论物理、学习与研究的文章。
---
<header class="page-header">
  <p class="eyebrow">Writing</p>
  <h1>博客</h1>
  <p>关于物理、学习与研究的阶段性记录。</p>
</header>

<div class="post-list">
  {% for post in site.posts %}
    <article class="post-list-item">
      <div class="post-list-date">
        <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y.%m.%d" }}</time>
      </div>
      <div>
        <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
        {% if post.categories.size > 0 %}<p class="post-meta">{{ post.categories | join: " · " }}</p>{% endif %}
        <p>{{ post.excerpt | strip_html | truncatewords: 35 }}</p>
      </div>
    </article>
  {% else %}
    <p class="empty-state">文章正在准备中。</p>
  {% endfor %}
</div>
