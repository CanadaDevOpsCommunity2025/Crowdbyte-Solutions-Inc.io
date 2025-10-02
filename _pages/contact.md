---
title: "Contact Us"
permalink: /contact/
layout: single
classes: wide
---

<section class="contact-hero">
  <div class="contact-hero__icon">🤝</div>
  <h1>Let’s build together</h1>
  <p class="contact-hero__tag">Tell us what you need—we’ll reply from <b>info@capitalcarbonconsulting.com</b>.</p>
</section>

<form
  action="https://formsubmit.co/info@capitalcarbonconsulting.com"
  method="POST"
  class="contact-card"
  aria-labelledby="contactHeading"
>
  <!-- FormSubmit helpers -->
  <input type="hidden" name="_subject" value="New Contact — Community / Events">
  <input type="hidden" name="_template" value="table">
  <input type="hidden" name="_next" value="{{ '/contact/?submitted=1' | relative_url }}">
  <input type="hidden" name="_captcha" value="false">
  <!-- Honeypot -->
  <input type="text" name="_honey" style="display:none">

  <h2 id="contactHeading" class="contact-card__title">How can we help?</h2>

  <div class="grid">
    <div class="field">
      <label for="name">Full name <span class="req">*</span></label>
      <input id="name" name="Full name" type="text" required placeholder="Jane Doe">
    </div>

    <div class="field">
      <label for="email">Email <span class="req">*</span></label>
      <input id="email" name="Email" type="email" required placeholder="you@company.com">
    </div>

    <fieldset class="field field--span2">
      <legend>What is this about? <span class="req">*</span></legend>
      <div class="chips" role="radiogroup" aria-label="Topic">
        <label class
