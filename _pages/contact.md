---
title: "Contact Us"
permalink: /contact/
layout: single
classes: wide
---

<!-- Contact form (static, no backend needed) -->
<form
  action="https://formsubmit.co/info@capitalcarbonconsulting.com"
  method="POST"
  class="contact-form"
>
  <!-- Required by formsubmit.co on first submit: you'll get a verification email -->
  <input type="hidden" name="_subject" value="New Contact — Community / Events">
  <input type="hidden" name="_template" value="table">
  <!-- Redirect back to this page with a success flag -->
  <input type="hidden" name="_next" value="{{ '/contact/?submitted=1' | relative_url }}">
  <!-- (Optional) disable captcha -->
  <input type="hidden" name="_captcha" value="false">

  <div class="field">
    <label for="name">Full name *</label>
    <input id="name" name="Full name" type="text" required>
  </div>

  <div class="field">
    <label for="email">Email *</label>
    <input id="email" name="Email" type="email" required>
  </div>

  <fieldset class="field">
    <legend>What is this about? *</legend>
    <label><input type="radio" name="Topic" value="Participate / be part of the community" required> Participate / be part of the community</label>
    <label><input type="radio" name="Topic" value="Organize an event" required> Organize an event</label>
    <label><input type="radio" name="Topic" value="Other" required> Other</label>
  </fieldset>

  <div class="field">
    <label for="message">Tell us more *</label>
    <textarea id="message" name="Message" rows="6" required></textarea>
  </div>

  <!-- simple spam honeypot -->
  <div style="display:none;">
    <label>Leave this empty: <input name="_honey" type="text"></label>
  </div>

  <button type="submit" class="btn-primary">Send</button>

  <p class="form-note">We’ll reply from <b>info@capitalcarbonconsulting.com</b> within 1–2 business days.</p>
</form>

<!-- Success message (shows after redirect) -->
<div id="form-success" class="form-success" hidden>
  <h3>Thanks — we’ve received your message.</h3>
  <p>We’ll get back to you soon from <b>info@capitalcarbonconsulting.com</b>.</p>
</div>

<script>
  // Show the thank-you message if redirected with ?submitted=1
  (function () {
    const params = new URLSearchParams(location.search);
    if (params.get('submitted') === '1') {
      document.querySelector('.contact-form')?.setAttribute('hidden','');
      document.getElementById('form-success')?.removeAttribute('hidden');
      // clean the URL
      const url = new URL(location.href); url.search = ''; history.replaceState({}, '', url);
    }
  })();
</script>

<style>
/* Minimal, on-brand styling */
.contact-form { max-width: 880px; margin: 0 auto; padding: 12px; }
.field { margin: 12px 0; display: grid; gap: 6px; }
.field input[type="text"],
.field input[type="email"],
.field textarea {
  padding: 10px 12px;
  border: 1px solid #d7dfef;
  border-radius: 10px;
  font-size: 16px;
}
fieldset.field { border: 1px solid #d7dfef; border-radius: 12px; padding: 10px 12px; }
fieldset.field legend { padding: 0 6px; font-weight: 700; color: #305890; }
.field label { font-weight: 600; }
.field input[type="radio"] { margin-right: 6px; }
.btn-primary {
  appearance: none; border: 0; cursor: pointer;
  padding: 10px 16px; border-radius: 12px;
  background: #305890; color: #fff; font-weight: 700; font-size: 16px;
}
.btn-primary:hover { filter: brightness(1.08); }
.form-note { font-size: 14px; color: #555; margin-top: 8px; }
.form-success { max-width: 680px; margin: 0 auto; padding: 16px; background: #f3f6fb; border: 1px solid #d7dfef; border-radius: 12px; }
</style>
