---
title: Activity
permalink: /sports-boosters/activity/
# What the Booster Club has funded, shown as photo cards in this order.
# Fields: title, caption, optional photo (an image path like
# /assets/images/sports-boosters/activity/batting-cages.jpg — 4:3 works best;
# leave it out to show a placeholder). Stock photos also carry credit,
# credit_url, license, and license_url — most Creative Commons licenses
# require that credit, so keep it with the photo. Replace stock photos with
# real ones of Cameron's own equipment whenever possible (then drop the credit).
impact:
  - title: Batting Cages
    caption: Improving practice opportunities and player development.
    photo: /assets/images/sports-boosters/activity/batting-cages.jpg
    credit: "Tdorante10"
    credit_url: https://commons.wikimedia.org/wiki/File:Cunningham_Ballfields_td_(2018-11-19)_22_-_Field_19_Batting_Cage.jpg
    license: "CC BY-SA 4.0"
    license_url: https://creativecommons.org/licenses/by-sa/4.0
  - title: Water Cow for Football
    caption: Keeping our athletes hydrated and ready to compete.
    photo: /assets/images/sports-boosters/activity/water-cow.jpg
    credit: "Bobak Ha'Eri"
    credit_url: https://commons.wikimedia.org/wiki/File:2026-0119_CFP_NCG_pregame_view_-_Miami_sideline.jpeg
    license: "CC BY 3.0"
    license_url: https://creativecommons.org/licenses/by/3.0
  - title: Cross Country Tents
    caption: Providing shade and shelter at meets.
    photo: /assets/images/sports-boosters/activity/cross-country-tents.jpg
    credit: "Jonathan Schilling"
    credit_url: https://commons.wikimedia.org/wiki/File:Holmdel_Park_cross-country_NJSIAA_group_championships_2019_start_of_girls_race.jpg
    license: "CC BY-SA 4.0"
    license_url: https://creativecommons.org/licenses/by-sa/4.0
  - title: Track and Field Tents
    caption: Supporting our athletes at every meet.
    photo: /assets/images/sports-boosters/activity/track-tents.jpg
    credit: "Don Williams"
    credit_url: https://commons.wikimedia.org/wiki/File:High_peak_frame_tent.JPG
    license: "Public domain"
  - title: Dragon Suit
    caption: Bringing our Dragon spirit to life!
    photo: /assets/images/sports-boosters/activity/dragon-suit.jpg # our own mascot photo, lifted onto a white-to-gold backdrop
  - title: Athletic Trainer Equipment
    caption: Helping keep our athletes safe and performing their best.
    photo: /assets/images/sports-boosters/activity/trainer-equipment.jpg
    credit: "Talento Tec"
    credit_url: https://commons.wikimedia.org/wiki/File:03042012Ccm_gamosuma_juvenilA232.JPG
    license: "CC BY-SA 3.0"
    license_url: https://creativecommons.org/licenses/by-sa/3.0
  - title: Banquet Meals
    caption: Celebrating our athletes and their hard work.
    photo: /assets/images/sports-boosters/activity/banquet-meals.jpg
    credit: "Acabashi"
    credit_url: https://commons.wikimedia.org/wiki/File:A_roast_lamb_dinner_at_Black_Horse_Inn,_Nuthurst_West_Sussex_England.jpg
    license: "CC BY-SA 4.0"
    license_url: https://creativecommons.org/licenses/by-sa/4.0
  - title: Dragon Sign at Football Field
    caption: Showcasing our pride for all to see!
  - title: Softball/Baseball Concessions Update
    caption: Upgrading our stands for a better game day experience.
    photo: /assets/images/sports-boosters/activity/concessions.jpg
    credit: "ViajeroExtraviado"
    credit_url: https://commons.wikimedia.org/wiki/File:Popcorn_9.jpg
    license: "CC0"
    license_url: http://creativecommons.org/publicdomain/zero/1.0/deed.en
  - title: Softball and Tennis Parking Lot Paint
    caption: Painting balls and names in the parking lot to celebrate our athletes!
  - title: Utility Vehicle # untitled on the poster (pictured: a utility vehicle) — confirm the name
    caption: Helping maintain our fields and facilities all year long.
    photo: /assets/images/sports-boosters/activity/utility-vehicle.jpg
    credit: "Basotxerri"
    credit_url: https://commons.wikimedia.org/wiki/File:Osnabr%C3%BCck_-_Botanischer_Garten_-_John_Deere_Gator_-BT-_01.jpg
    license: "CC BY-SA 4.0"
    license_url: https://creativecommons.org/licenses/by-sa/4.0
  - title: District Bags
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
      {% if item.credit %}
      <p class="photo-credit">Photo: <a href="{{ item.credit_url }}" target="_blank" rel="noopener">{{ item.credit }}</a>{% if item.license %}, {% if item.license_url %}<a href="{{ item.license_url }}" target="_blank" rel="noopener">{{ item.license }}</a>{% else %}{{ item.license }}{% endif %}{% endif %}</p>
      {% endif %}
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
