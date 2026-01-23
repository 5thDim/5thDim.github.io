---
layout: default
title: 博客文章列表
---
<h1>所有博客文章</h1>

<ul>
  {% for post in site.posts %}
    <li>
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p>
        <time datetime="{{ post.date | date_to_xmlschema }}">
          {{ post.date | date: "%Y年%-m月%-d日" }}
        </time>
        • 分类：{{ post.categories | join: ", " }}
      </p>
      <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
    </li>
  {% endfor %}
</ul>