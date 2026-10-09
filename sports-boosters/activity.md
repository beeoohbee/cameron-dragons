---
title: Activity
permalink: /sports-boosters/activity/
# What the Booster Club has funded, shown as photo cards in this order.
# Fields: title, caption, optional photo (an image path like
# /assets/images/sports-boosters/activity/batting-cages.jpg — 4:3 works best;
# leave it out to show a placeholder).
impact:
  - title: Batting Cages
    caption: Improving practice opportunities and player development.
  - title: Water Cow for Football
    caption: Keeping our athletes hydrated and ready to compete.
  - title: Cross Country Tents
    caption: Providing shade and shelter at meets.
  - title: Track and Field Tents
    caption: Supporting our athletes at every meet.
  - title: Dragon Suit
    caption: Bringing our Dragon spirit to life!
  - title: Athletic Trainer Equipment
    caption: Helping keep our athletes safe and performing their best.
  - title: Banquet Meals
    caption: Celebrating our athletes and their hard work.
  - title: Dragon Sign at Football Field
    caption: Showcasing our pride for all to see!
  - title: Softball/Baseball Concessions Update
    caption: Upgrading our stands for a better game day experience.
  - title: Softball and Tennis Parking Lot Paint
    caption: Painting balls and names in the parking lot to celebrate our athletes!
  - title: Utility Vehicle # untitled on the poster (pictured: a utility vehicle) — confirm the name
    caption: Helping maintain our fields and facilities all year long.
  - title: District Bags (Last Year)
    caption: Providing food and drink for our teams during district competition.
---

<p class="impact-tagline">Making an impact. Supporting our Dragons!</p>

Thanks to the support of our Dragon Family, the Booster Club has been able to fund and provide:

<ul class="impact-grid">
  {% for item in page.impact %}
  <li class="impact-card">
    {% if item.photo %}
      <img class="impact-photo" src="{{ item.photo | relative_url }}" alt="{{ item.title }}">
    {% else %}
      <div class="impact-photo gallery-placeholder">Photo</div>
    {% endif %}
    <div class="impact-body">
      <h3>{{ item.title }}</h3>
      <p>{{ item.caption }}</p>
    </div>
  </li>
  {% endfor %}
</ul>

<section class="thank-you-band">
  <p class="thank-you-heading">Thank you</p>
  <p>to our amazing community for believing in our athletes and our future!</p>
</section>

<div class="impact-closing">
  <p class="impact-closing-lead">Together, we build <span>champions</span> on and off the field!</p>
  <div>
    <p class="impact-closing-cta">Join. Donate. Support.<br><span>Be part of the Dragon legacy!</span></p>
    <p>Contact any Booster Club member or visit us at a home event! You can also <a href="{{ '/sports-boosters/contact/' | relative_url }}">get in touch</a> or see our <a href="{{ '/sports-boosters/members/' | relative_url }}">members</a>.</p>
  </div>
</div>

<section class="scholarships" id="scholarships">
  <h2>Scholarships</h2>
  <p>The Booster Club awards scholarships to graduating senior athletes. To be eligible:</p>
  <ul class="scholarship-requirements">
    <li>Must be an Athletics Booster Club member for 2 years, with one being your senior year.</li>
    <li>Must be an Athletics Booster Club member by December 31st of your senior year.</li>
    <li>Must participate in 4 MSHSAA approved seasons in your high school career.</li>
  </ul>
</section>
