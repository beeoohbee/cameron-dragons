---
layout: default
title: Contact
permalink: /contact/
---

Have a question, or think a booster organization is missing from the site? Send us a message.

<form class="contact-form" id="contact-form" data-to="beeohbee@gmail.com">
  <label for="cf-name">Name</label>
  <input id="cf-name" name="name" type="text" autocomplete="name" required>

  <label for="cf-email">Your email</label>
  <input id="cf-email" name="email" type="email" autocomplete="email" required>

  <label for="cf-subject">Subject</label>
  <input id="cf-subject" name="subject" type="text" required>

  <label for="cf-message">Message</label>
  <textarea id="cf-message" name="message" rows="6" required></textarea>

  <button type="submit">Open in email</button>
  <p class="form-note">Submitting opens your email app with this message ready to send to beeohbee@gmail.com. Nothing is sent until you press Send there.</p>
</form>

<script>
  // Jekyll is static, so there's no server to receive the form. Instead, build
  // a mailto: link from the fields and hand it to the visitor's email app.
  document.getElementById('contact-form').addEventListener('submit', function (e) {
    e.preventDefault();
    var f = e.target.elements;
    var body =
      'Name: ' + f['name'].value + '\n' +
      'Email: ' + f['email'].value + '\n\n' +
      f['message'].value;
    window.location.href = 'mailto:' + e.target.dataset.to +
      '?subject=' + encodeURIComponent(f['subject'].value) +
      '&body=' + encodeURIComponent(body);
  });
</script>
