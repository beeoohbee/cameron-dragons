---
layout: default
title: Home
hide_title: true
---

Welcome to **Cameron Dragons** — home base for the Cameron Dragons booster organizations. Pick a group below for their news, events, and how to get involved.

<div class="subsite-grid">
{% for s in site.data.subsites %}
  <a class="subsite-card" href="{{ s.url | relative_url }}">
    <h2>{{ s.name }}</h2>
    <p>{{ s.tagline }}</p>
  </a>
{% endfor %}
</div>
