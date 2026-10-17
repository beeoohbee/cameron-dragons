---
layout: default
title: Home
seo_title: "Cameron Dragons — Booster Clubs & Youth Organizations | Cameron, MO"
description: "Find Cameron, Missouri booster clubs, sports teams, and youth programs — Sports Boosters, swim, baseball, youth football, soccer, band, PTSA, and more."
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
    Welcome to **Cameron Dragons** — home base for Cameron Dragons organizations,
    from booster clubs to sports teams and youth programs. Pick a group below for their news, events,
    and how to get involved.
  button_text: Find your organization
  button_url: "#organizations"
---

<h2 id="organizations">Find the Cameron Dragons you’re looking for</h2>

<div class="subsite-grid">
{% for s in site.data.subsites %}
  {% if s.coming_soon %}
  <div class="subsite-card subsite-card-placeholder">
    <h2>{{ s.name }}</h2>
    <p>{{ s.tagline }}</p>
    <span class="card-label coming-soon">Coming soon</span>
  </div>
  {% else %}
  {% comment %}
    The org name is the card's main link, stretched over the whole card (see
    .card-main-link in style.css). Extra links, like a sub-site's Facebook
    page, sit above it as their own label pills.
  {% endcomment %}
  {% if s.external %}
    {% assign main_url = s.external_url | default: s.url %}
    {% assign main_label = s.external_label | default: "Website" %}
  {% else %}
    {% assign main_url = s.url | relative_url %}
    {% assign main_label = "Website" %}
  {% endif %}
  <div class="subsite-card">
    <h2><a class="card-main-link" href="{{ main_url }}"{% if s.external %} target="_blank" rel="noopener"{% endif %}>{{ s.name }}{% if s.external %}<span class="visually-hidden"> on {{ main_label }} (opens in a new tab)</span>{% endif %}</a></h2>
    <p>{{ s.tagline }}</p>
    <div class="card-labels">
      <span class="card-label" aria-hidden="true">{% include card-icon.html label=main_label %} {{ main_label }} {% if s.external %}&#8599;{% else %}&rarr;{% endif %}</span>
      {% unless s.external %}{% for link in s.social %}{% assign network = link[0] %}
      <a class="card-label card-label-link" href="{{ link[1] }}" target="_blank" rel="noopener">{% include card-icon.html label=network %} {{ network | capitalize }} <span aria-hidden="true">&#8599;</span><span class="visually-hidden"> — {{ s.name }} (opens in a new tab)</span></a>
      {% endfor %}{% endunless %}
    </div>
  </div>
  {% endif %}
{% endfor %}
</div>

<section class="missing-org">
  <h2>Don't see your organization?</h2>
  <p>If you can't find the organization you're looking for and believe it's missing, <a href="{{ '/contact/' | relative_url }}">contact Cameron Dragons</a> and we'll investigate.</p>
</section>
