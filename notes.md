---
layout: default
title: 研究笔记
permalink: /notes/
description: 高能理论物理与量子场论的研究笔记。
---
<header class="page-header">
  <p class="eyebrow">Notes</p>
  <h1>研究笔记</h1>
  <p>对物理主题进行较系统的梳理。内容可能持续修订，欢迎交流。</p>
</header>

{% assign notes = site.categories.notes %}
{% if notes.size > 0 %}
<div class="post-list">
  {% for post in notes %}
  <article class="post-list-item">
    <div class="post-list-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y.%m.%d" }}</time></div>
    <div>
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p>{{ post.excerpt | strip_html | truncatewords: 35 }}</p>
    </div>
  </article>
  {% endfor %}
</div>
{% else %}
<div class="empty-state">
  <p>第一篇系统笔记正在整理中。</p>
  <p><small>以后可以在文章的 <code>categories</code> 中加入 <code>notes</code>，文章就会自动出现在这里。</small></p>
</div>
{% endif %}
