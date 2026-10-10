---
title: Contact
permalink: /sports-boosters/contact/
---

{% assign subsite = site.data.subsites | where: "key", page.subsite | first %}
Have a question or want to get involved with the Cameron Sports Boosters Association? Reach out.

<ul class="contact-list">
  <li><i class="fa-solid fa-envelope" aria-hidden="true"></i> <strong>Email:</strong> [email protected]</li>
  <li><i class="fa-brands fa-facebook" aria-hidden="true"></i> <strong>Facebook:</strong> <a href="{{ subsite.social.facebook }}" target="_blank" rel="noopener">Cameron Sports Boosters Association<span class="visually-hidden"> (opens in a new tab)</span></a></li>
</ul>

<p><em>Note: Jekyll builds static HTML, so a working contact form needs a form backend service (e.g. Formspree, Netlify Forms) since there's no server-side code to process submissions.</em></p>
