---
title: Join
permalink: /sports-boosters/join/
# Membership levels, from the sign-up form. Edit prices/descriptions here.
levels:
  - name: Gold Business
    price: $150
    note: For local businesses — your logo and a link on our Members page and home page.
  - name: Silver Family
    price: $75
    note: One membership for your whole family.
  - name: Bronze Individual
    price: $25
    note: An individual membership.
  - name: Student Athlete
    price: $10
    note: For Cameron student-athletes supporting their own teams.
  - name: CHS Coach & Family
    price: No charge
    note: For Cameron High School coaches and their families.
---
{% assign subsite = site.data.subsites | where: "key", page.subsite | first %}

Every membership goes straight back to Cameron Dragons athletes — equipment, facilities, banquets, scholarships, and more. Pick the level that fits you, fill out the form, and pay however is easiest.

<ul class="level-grid">
  {% for level in page.levels %}
  <li class="level-card">
    <h2>{{ level.name }}</h2>
    <p class="level-price">{{ level.price }}</p>
    <p>{{ level.note }}</p>
  </li>
  {% endfor %}
</ul>

<div class="join-steps">
  <section class="join-step">
    <h2><span class="step-num">1</span> Fill out the form</h2>
    <p>Tell us who you are, your membership level, the athletes you're enrolling, and how you'd like to help.</p>
    <img class="join-qr" src="{{ '/assets/images/sports-boosters/join-qr.png' | relative_url }}" alt="QR code linking to the Booster Club membership form" loading="lazy" decoding="async">
    <p><a class="button" href="{{ subsite.join_form }}" target="_blank" rel="noopener">Open the membership form</a></p>
  </section>

  <section class="join-step">
    <h2><span class="step-num">2</span> Pay your dues</h2>
    <ul class="contact-list">
      <li><i class="fa-solid fa-mobile-screen-button" aria-hidden="true"></i> <strong>Venmo:</strong> <a href="https://venmo.com/u/{{ subsite.venmo }}" target="_blank" rel="noopener">@{{ subsite.venmo }}</a></li>
      <li><i class="fa-solid fa-money-check" aria-hidden="true"></i> <strong>Check:</strong> payable to Cameron Sports Boosters Association</li>
      <li><i class="fa-solid fa-money-bill" aria-hidden="true"></i> <strong>Cash:</strong> to any Booster Board member</li>
      <li><i class="fa-solid fa-credit-card" aria-hidden="true"></i> <strong>Card or tap to pay</strong></li>
    </ul>
  </section>
</div>

<section class="donate-callout">
  <h2>Not ready to join? You can still help.</h2>
  <p>Any amount makes a difference for our athletes.</p>
  {% include donate-button.html %}
</section>

Questions about membership? [Contact us]({{ '/sports-boosters/contact/' | relative_url }}).
