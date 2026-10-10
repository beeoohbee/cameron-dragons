---
title: News
permalink: /sports-boosters/news/
# Hidden for now: not built, and the sub-site nav drops its News link.
# Delete this line (and set the collection's output back to true in
# _config.yml) to bring the News page back.
published: false
---

<ul class="post-list">
{% for post in site.sports_boosters_posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span class="post-date">{{ post.date | date: "%B %-d, %Y" }}</span>
    <p>{{ post.excerpt }}</p>
  </li>
{% endfor %}
</ul>
