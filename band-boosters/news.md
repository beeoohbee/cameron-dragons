---
title: News
permalink: /band-boosters/news/
---

<ul class="post-list">
{% for post in site.band_boosters_posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span class="post-date">{{ post.date | date: "%B %-d, %Y" }}</span>
    <p>{{ post.excerpt }}</p>
  </li>
{% endfor %}
</ul>
