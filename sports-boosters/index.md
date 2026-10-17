---
title: Home
permalink: /sports-boosters/
seo_title: "Cameron Sports Boosters Association | Cameron, MO"
description: "The Cameron Sports Boosters Association supports Cameron Dragons athletics in Cameron, Missouri with fundraising, volunteers, and scholarships. Join today."
hide_title: true
# Centered logo hero (see _includes/hero.html). The logo is the page's <h1>,
# so image_alt is the org's full name.
hero:
  style: centered
  image: /assets/images/sports-boosters/logo.webp
  image_alt: Cameron Sports Boosters Association
  text: Supporting Cameron Dragons athletics — fundraising, concessions, and game-day volunteers.
---
{% assign subsite = site.data.subsites | where: "key", page.subsite | first %}

<section class="join-section">
  <p class="join-tagline">Support today. <span aria-hidden="true">&#9733;</span> Impact tomorrow.</p>

  <div class="join-grid">
    <div class="join-why">
      <h2>Together, we can <span>make a difference!</span></h2>
      <ul class="benefit-list">
        <li>
          <span class="benefit-icon" aria-hidden="true">
            <svg viewBox="0 0 24 24"><circle cx="12" cy="8" r="3"/><circle cx="5" cy="10" r="2.2"/><circle cx="19" cy="10" r="2.2"/><path d="M6.5 20v-1.5a5.5 5.5 0 0 1 11 0V20zM1 20v-1a4 4 0 0 1 5-3.9A7 7 0 0 0 5 18.5V20zM23 20v-1a4 4 0 0 0-5-3.9 7 7 0 0 1 1 3.4V20z"/></svg>
          </span>
          <div>
            <h3>Support our student-athletes</h3>
            <p>Help provide opportunities and resources for success on and off the field.</p>
          </div>
        </li>
        <li>
          <span class="benefit-icon" aria-hidden="true">
            <svg viewBox="0 0 24 24"><path d="M3 10v4h3l7 4V6L6 10zM15 9.5v5a3 3 0 0 0 0-5zM6.5 15l1.5 5h2.5l-1.6-5z"/><path d="M18 7.5a6 6 0 0 1 0 9" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round"/></svg>
          </span>
          <div>
            <h3>Enhance our programs</h3>
            <p>Fund equipment, facilities, travel, and essential needs.</p>
          </div>
        </li>
        <li>
          <span class="benefit-icon" aria-hidden="true">
            <svg viewBox="0 0 24 24"><path d="M7 3h10v5a5 5 0 0 1-10 0zM7 4.5H3.5V7A3.5 3.5 0 0 0 7 10.5zM17 4.5h3.5V7a3.5 3.5 0 0 1-3.5 3.5zM10.8 12.8h2.4V17h-2.4zM7.5 17.5h9V21h-9z"/></svg>
          </span>
          <div>
            <h3>Build a stronger community</h3>
            <p>Join other Cameron supporters in making a lasting impact.</p>
          </div>
        </li>
      </ul>
    </div>

    <div class="join-card">
      <h2>Join today!</h2>
      <img class="join-qr" src="{{ '/assets/images/sports-boosters/join-qr.png' | relative_url }}" alt="QR code linking to the Booster Club membership form" loading="lazy" decoding="async">
      <p class="join-scan">Scan to join and support Cameron Athletics!</p>
      <div class="button-row">
        <a class="button" href="{{ subsite.join_form }}" target="_blank" rel="noopener">Join online</a>
        {% include donate-button.html %}
      </div>
      <p class="join-levels"><a href="{{ subsite.url | relative_url }}join/">See membership levels &amp; ways to pay</a></p>
    </div>
  </div>
</section>

{% include sponsor-strip.html %}

<section class="one-cameron">
  <p class="one-cameron-lead">One team. One community.</p>
  <p class="one-cameron-big">One Cameron.</p>
  <p class="one-cameron-foot"><span aria-hidden="true">&#9733;</span> Our athletes. Our school. Our future. <span aria-hidden="true">&#9733;</span></p>
</section>
