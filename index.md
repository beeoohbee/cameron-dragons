---
layout: default
title: Home
hide_title: true
# Landing-page hero (rendered by _includes/hero.html). The image sits on the
# left and fades into the hero background color behind the text on the right.
hero:
  # Placeholder art — swap for the student photo when it's ready, and change
  # image_fit to "cover" so the photo fills the left side.
  image: /assets/images/hero-placeholder.jpg
  image_alt: ""
  image_fit: contain
  title: Cameron Dragons
  text: >-
    Welcome to **Cameron Dragons** — home base for the Cameron Dragons booster
    organizations. Pick a group below for their news, events, and how to get involved.
  button_text: Find your booster club
  button_url: "#organizations"
---

<h2 id="organizations">Find the Cameron Dragons you’re looking for</h2>

<div class="subsite-grid">
{% for s in site.data.subsites %}
  {% if s.coming_soon %}
  <div class="subsite-card subsite-card-placeholder">
    <h2>{{ s.name }}</h2>
    <p>{{ s.tagline }}</p>
    <span class="coming-soon">Coming soon</span>
  </div>
  {% else %}
  <a class="subsite-card" href="{{ s.url | relative_url }}">
    <h2>{{ s.name }}</h2>
    <p>{{ s.tagline }}</p>
  </a>
  {% endif %}
{% endfor %}
</div>

<section class="missing-org">
  <h2>Don't see your organization?</h2>
  <p>If you can't find the organization you're looking for and believe it's missing, <a href="{{ '/contact/' | relative_url }}">contact Cameron Dragons</a> and we'll investigate.</p>
</section>
