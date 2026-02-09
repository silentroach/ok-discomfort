---
layout: default
title: ОК Дискомфорт
---

# ОК Дискомфорт

{% assign posts = site.pages | where_exp: "page", "page.date" | sort: "date" | reverse %}
{% for post in posts %}

<article class="post-preview">
  <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
  <p class="post-date">{{ post.date | date: "%d.%m.%Y" }}</p>
  
  {% if post.excerpt %}
  <div class="post-excerpt">
    {{ post.excerpt }}
  </div>
  {% endif %}
  
  <a href="{{ post.url | relative_url }}" class="read-more">Читать далее →</a>
</article>

{% unless forloop.last %}

<hr>
{% endunless %}
{% endfor %}
