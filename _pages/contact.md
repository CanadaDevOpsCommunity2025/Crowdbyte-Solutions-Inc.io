---
title: "Contact Us"
permalink: /contact/
layout: single
classes: wide   # keep the page constrained; we'll explicitly center the inner content
---

<div class="contact-wrap">
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
          <label class="chip">
            <input type="radio" name="Topic" value="Be a Sponsor" required>
            <span>Be a Sponsor</span>
          </label>
          <label class="chip">
            <input type="radio" name="Topic" value="Participate / be part of the community" required>
            <span>Participate / be part of the community</span>
          </label>
          <label class="chip">
            <input type="radio" name="Topic" value="Organize an event" required>
            <span>Organize an event</span>
          </label>
          <label class="chip">
            <input type="radio" name="Topic" value="Other" required>
            <span>Other</span>
          </label>
        </div>
      </fieldset>

      <div class="field field--span2">
        <label for="message">Tell us more <span class="req">*</span></label>
        <textarea id="message" name="Message" rows="7" required placeholder="Briefly describe your idea, timelines, audience size, and any links."></textarea>
        <div class="field__hint">We typically respond within 1–2 business days.</div>
      </div>
    </div>

    <button type="submit" class="btn-primary">Send message</button>
    <p class="form-note">Prefer email? <a href="mailto:info@capitalcarbonconsulting.com?subject=Contact%20—%20Community%20or%20Events">Email us directly</a>.</p>
  </form>

  <!-- Success message (shown after redirect from _next) -->
  <div id="form-success" class="contact-success" hidden>
    <div class="contact-success__icon">✅</div>
    <h3>Thanks — your message is in!</h3>
    <p>We’ll get back to you soon from <b>info@capitalcarbonconsulting.com</b>.</p>
    <a class="btn-secondary" href="{{ '/' | relative_url }}">Back to Home</a>
  </div>
</div>
<p style="margin-top:16px;">
  <a class="btn btn--primary" href="https://github.com/CanadaDevOpsCommunity2025" target="_blank" rel="noopener">
    Join our GitHub Community
  </a>
</p>
<script>
  (function () {
    const params = new URLSearchParams(location.search);
    if (params.get('submitted') === '1') {
      document.querySelector('.contact-card')?.setAttribute('hidden','');
      document.getElementById('form-success')?.removeAttribute('hidden');
      const url = new URL(location.href); url.search = ''; history.replaceState({}, '', url);
    }
  })();
</script>

<style>
/* ---------- Centering wrapper (bullet-proof) ---------- */
.contact-wrap{
  /* hard-center the entire contact section */
  width: min(980px, calc(100% - 48px));
  margin-left: auto;
  margin-right: auto;
}

/* Hide default page title spacing */
.page__title{ display:none; }

/* Hero */
.contact-hero{
  text-align:center;
  padding: 18px 10px 8px;
}
.contact-hero__icon{ font-size: 32px; }
.contact-hero h1{
  margin: 8px 0 6px;
  font-weight: 800;
  font-size: clamp(22px, 3vw, 28px);
  color: #0f172a;
}
.contact-hero__tag{
  margin: 0 auto;
  color: #475569;
  font-size: 15px;
}

/* Card container */
.contact-card{
  background: #f7f9fc;
  border: 1px solid #d7dfef;
  border-radius: 14px;
  padding: clamp(16px, 3vw, 28px);
  /* full width of the centered wrapper */
  width: 100%;
  margin: 14px 0 24px;
  box-shadow: 0 6px 18px rgba(16, 24, 40, 0.06);
}
.contact-card__title{
  margin: 0 0 8px;
  font-weight: 800;
  color: #305890;
  font-size: clamp(18px, 2.2vw, 22px);
}

/* Grid */
.grid{
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 14px clamp(12px, 2vw, 18px);
  margin-top: 8px;
}
.field--span2{ grid-column: 1 / -1; }

/* Fields */
.field{ display: grid; gap: 6px; }
label, legend{ font-weight: 650; color: #0f172a; }
.req{ color: #e11d48; }

input[type="text"],
input[type="email"],
textarea{
  border: 1px solid #d7dfef;
  background: #fff;
  border-radius: 12px;
  font-size: 16px;
  padding: 12px 12px;
  outline: none;
  transition: border-color .15s ease, box-shadow .15s ease;
}
textarea{ resize: vertical; }

input:focus, textarea:focus{
  border-color: #305890;
  box-shadow: 0 0 0 3px rgba(48,88,144, .15);
}

/* Chips radio group */
.chips{ display: flex; flex-wrap: wrap; gap: 10px; margin-top: 6px; }
.chip{
  display: inline-flex; align-items: center; gap: 8px;
  border: 1px solid #d7dfef;
  border-radius: 999px;
  padding: 8px 12px;
  background: #fff;
  cursor: pointer;
  user-select: none;
  transition: all .15s ease;
}
.chip input{ appearance: none; width: 14px; height: 14px; border: 2px solid #305890; border-radius: 999px; }
.chip input:checked{ background: #305890; }
.chip:hover{ border-color: #305890; box-shadow: 0 2px 10px rgba(48,88,144,.12); }
.chip span{ font-size: 14.5px; color: #0f172a; }

/* Hint */
.field__hint{ font-size: 13px; color: #475569; }

/* Buttons */
.btn-primary,
.btn-secondary{
  display: inline-block;
  border-radius: 12px;
  font-weight: 800;
  text-decoration: none;
  padding: 10px 16px;
  transition: transform .04s ease, filter .15s ease, box-shadow .15s ease;
}
.btn-primary{
  background: #305890;
  color: #fff;
  border: 0;
}
.btn-primary:hover{ filter: brightness(1.05); }
.btn-primary:active{ transform: translateY(1px); }

.btn-secondary{
  background: #fff;
  color: #305890;
  border: 1px solid #d7dfef;
}
.btn-secondary:hover{ box-shadow: 0 2px 10px rgba(48,88,144,.12); }

/* Success panel (share the same centered width) */
.contact-success{
  width: 100%;
  max-width: 720px;
  margin: 24px auto;
  background: #f3f6fb;
  border: 1px solid #d7dfef;
  border-radius: 14px;
  padding: clamp(16px, 3vw, 28px);
  text-align: center;
}
.contact-success__icon{ font-size: 28px; margin-bottom: 6px; }

/* Responsive */
@media (max-width: 760px){
  .grid{ grid-template-columns: 1fr; }
}
</style>
