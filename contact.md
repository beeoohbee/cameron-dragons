---
layout: default
title: Contact
permalink: /contact/
description: "Contact Cameron Dragons with questions, or let us know about a Cameron, Missouri youth organization that's missing from the site."
# Contact form is handled by Formspree (https://formspree.io), which emails
# submissions to mocamerondragons@gmail.com. Manage the form, spam settings,
# and past messages in the Formspree dashboard.
formspree_url: https://formspree.io/f/myekdabr
---

Have a question, or think an organization is missing from the site? Send us a message.

<ul class="contact-list">
  <li><i class="fa-solid fa-envelope" aria-hidden="true"></i> <strong>Email:</strong> <a href="mailto:mocamerondragons@gmail.com">mocamerondragons@gmail.com</a></li>
</ul>

Or use the form below:

<form class="contact-form" id="contact-form" action="{{ page.formspree_url }}" method="POST">
  <label for="cf-name">Name</label>
  <input id="cf-name" name="name" type="text" autocomplete="name" required>

  <label for="cf-email">Your email</label>
  <input id="cf-email" name="email" type="email" autocomplete="email" required>

  <label for="cf-subject">Subject</label>
  <input id="cf-subject" name="subject" type="text" required>

  <label for="cf-message">Message</label>
  <textarea id="cf-message" name="message" rows="6" required></textarea>

  <!-- Subject line of the email Formspree sends (filled in from the Subject field). -->
  <input type="hidden" name="_subject" value="Cameron Dragons website message">

  <!-- Honeypot: hidden from people, but bots fill it in; Formspree discards those submissions. -->
  <div class="form-honeypot" aria-hidden="true">
    <label for="cf-gotcha">Leave this field empty</label>
    <input id="cf-gotcha" name="_gotcha" type="text" tabindex="-1" autocomplete="off">
  </div>

  <button type="submit">Send message</button>
  <p class="form-status" id="form-status" role="status" aria-live="polite"></p>
</form>

<script>
  // Send the form to Formspree in the background and show the result on this
  // page. Without JavaScript the form still works: it posts normally and
  // Formspree shows its own thank-you page.
  (function () {
    var form = document.getElementById('contact-form');
    var status = document.getElementById('form-status');
    var button = form.querySelector('button[type="submit"]');

    form.addEventListener('submit', function (e) {
      e.preventDefault();
      var subject = form.elements['subject'].value.trim();
      form.elements['_subject'].value = 'Cameron Dragons website: ' + (subject || 'New message');

      button.disabled = true;
      button.textContent = 'Sending…';
      status.className = 'form-status';
      status.textContent = '';

      fetch(form.action, {
        method: 'POST',
        body: new FormData(form),
        headers: { 'Accept': 'application/json' }
      }).then(function (response) {
        if (response.ok) {
          form.reset();
          status.className = 'form-status is-success';
          status.textContent = 'Thanks! Your message was sent — we\'ll get back to you soon.';
        } else {
          return response.json().then(function (data) {
            var detail = data && data.errors ? data.errors.map(function (x) { return x.message; }).join(' ') : '';
            throw new Error(detail);
          });
        }
      }).catch(function (err) {
        status.className = 'form-status is-error';
        status.textContent = 'Sorry, your message couldn\'t be sent' + (err.message ? ' (' + err.message + ')' : '') +
          '. Please email us at mocamerondragons@gmail.com instead.';
      }).finally(function () {
        button.disabled = false;
        button.textContent = 'Send message';
      });
    });
  })();
</script>
