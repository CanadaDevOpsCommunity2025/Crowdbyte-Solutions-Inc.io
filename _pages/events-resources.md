---
layout: single
permalink: /events-resources/
title: "Events and Resources"
sidebar: false
classes: "full-bleed"
---

<style>
/* Hide the Previous / Next pager on this page only */
.pagination, .pagination--pager { display:none !important; }

/* ===== Full-bleed layout (edge-to-edge) ===== */
.page.full-bleed .page__inner-wrap,
.page.full-bleed .page__content {
  max-width: none !important;
  padding-left: 0 !important;
  padding-right: 0 !important;
}
.full-bleed-row {
  width: 100vw;
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
}
/* Center the page title */
.page__title {
  text-align: center !important;
  margin-left: auto;
  margin-right: auto;
}

/* ===== Hero band ===== */
.cb-hero {
  background:#2f5597;
  color:#fff;
  padding: 28px 24px;
  text-align:center;
}
.cb-hero h1{
  margin:0;
  font-weight:800;
  font-size: clamp(24px, 3.6vw, 40px);
  line-height:1.2;
}

/* ===== Body ===== */
.cb-wrap { padding: 20px 24px; }

.cb-title {
  text-align:center;
  font-weight:800;
  margin: 10px 0 10px;
  font-size: clamp(18px, 2.2vw, 24px);
}
.cb-title .hl { color:#2874c7; text-decoration: underline; }

.cb-intro { text-align:center; margin: 6px 0 14px; }
.cb-intro strong { display:block; }

/* Two-column grid */
.er-grid {
  display:grid;
  grid-template-columns: 1fr 1fr;
  gap: 28px;
  max-width: 1200px;
  margin: 0 auto;
}
@media (max-width: 880px){ .er-grid { grid-template-columns: 1fr; } }

.block { line-height:1.25; }
.block + .block { margin-top: 24px; }

.block .caps {
  font-weight: 800;
  text-transform: none;
  letter-spacing: .02em;
  margin-bottom: 4px;
}

/* Link list styles */
.inline-links { margin-top: 6px; }
.inline-links a {
  display:block;
  text-decoration: none;
  color:#2874c7;
  font-weight:600;
  font-style: italic;
  font-size: 0.80rem;
  line-height: 1.2;
}
@media (max-width: 880px){
  .inline-links a { font-size: 0.9rem; }
}
.inline-links a + a { margin-top: 8px; }
@media (min-width: 881px){
  .inline-links a + a { margin-top: 10px; }
}
.inline-links a:visited { color:#2874c7; }
.inline-links a:hover,
.inline-links a:focus { text-decoration: underline; }
.inline-links a:active { opacity: .9; }

/* ===== SPONSORS (uniform TECHSTRONG-sized tiles + seamless loop) ===== */
.sponsors-band{
  width: 100vw;
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
  background: linear-gradient(180deg, #f7f9ff 0%, #eef4ff 100%);
  border-top: 1px solid rgba(0,0,0,.06);
  border-bottom: 1px solid rgba(0,0,0,.06);
  padding: clamp(12px, 1.8vw, 18px) 0;
  margin-top: clamp(24px, 3.2vw, 48px);
}
.sponsors-inner{
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 clamp(10px, 2.6vw, 20px);
}

/* Center heading & note */
.sponsors-head{
  display:flex; flex-direction:column; align-items:center; justify-content:center;
  gap:6px; margin-bottom: clamp(8px, 1.4vw, 12px);
  text-align:center;
}
.sponsors-title{ margin:0; font-weight:900; font-size: clamp(15px, 1.8vw, 18px); color:#172b4d; }
.sponsors-note{ margin:0; font-size: clamp(.86rem, 1.3vw, .95rem); color:#51657d; }

/* Marquee */
.logo-marquee{ position:relative; overflow:hidden; }

/* Track: animation distance/duration set via CSS vars */
.logo-track{
  --loop-distance: 50%;
  --loop-duration: 26s;
  display:flex; align-items:center;
  gap: 12px;
  will-change: transform;
  animation: sponsors-marquee var(--loop-duration) linear infinite;
}
.logo-track:hover{ animation-play-state: paused; }
@keyframes sponsors-marquee{
  from{ transform: translateX(0); }
  to  { transform: translateX(calc(-1 * var(--loop-distance))); }
}

/* Uniform tiles (same footprint for each; matches home page) */
:root{ --tile-w: 170px; --tile-h: 60px; }
.logo-box{
  flex: 0 0 auto;
  width: var(--tile-w);
  height: var(--tile-h);
  display:flex; align-items:center; justify-content:center;
  background:#ffffff;
  border:1px solid rgba(23,43,77,.10);
  border-radius:10px;
  box-shadow:0 6px 18px rgba(23,43,77,.08);
  padding: 6px;
  overflow:hidden;
  transition: transform .15s ease, box-shadow .15s ease, border-color .15s ease;
}
.logo-box:hover{
  transform: translateY(-1px);
  box-shadow: 0 10px 24px rgba(23,43,77,.12);
  border-color: rgba(23,43,77,.18);
}

/* Logos fit without cropping or distortion */
.logo{
  display:block;
  max-width: 100%;
  max-height: 100%;
  width: auto; height: auto;
  object-fit: contain;
  image-rendering: auto;
  filter: saturate(1.02) contrast(1.03);
}

/* Reduced motion: stop animation */
@media (prefers-reduced-motion: reduce){ .logo-track{ animation:none; } }
</style>

<!-- HERO -->
<div class="full-bleed-row cb-hero">
  <h1>We’re more than a community—we’re a movement!</h1>
</div>

<!-- MAIN -->
<div class="full-bleed-row cb-wrap">
  <h2 class="cb-title">
    <span class="hl">Crowdbyte&nbsp;&nbsp;<em><strong>DevOps + AI</strong></em>&nbsp;&nbsp;Community of Practice</span>
  </h2>

  <p class="cb-intro">
    We’re an energetic, network of technologists, builders, and innovators shaping the future of DevOps and AI in
    <strong>Canada.</strong>
  </p>

  <div class="er-grid">
    <!-- LEFT COLUMN -->
    <div>
      <div class="block">
        <div class="caps">DevOps for GenAI,</div>
        <div class="caps">Hackathon Series Global</div>
        <div class="inline-links">
          <a href="{{ site.baseurl }}/contact/">Become a Sponsor</a>
          <a href="https://www.eventbrite.ca/e/devops-for-genai-hackathon-tickets-1407877793379" target="_blank" rel="noopener">Register on Eventbrite</a>
        </div>
      </div>

      <div class="block">
        <div class="caps">DevOps for GenAI,</div>
        <div class="caps">Hackathon Series Global</div>
        <div class="inline-links">
          <a href="{{ site.baseurl }}/contact/">Propose a Location</a>
        </div>
      </div>
    </div>

    <!-- RIGHT COLUMN -->
    <div>
      <div class="block">
        <div class="caps">DevOps Summit, Canada</div>
        <div class="caps">AI Summit, Canada</div>
        <div class="inline-links">
          <a href="{{ site.baseurl }}/contact/">Become a Sponsor</a>
          <a href="#">Submit Speaker Proposal</a>
          <a href="#">Get Tickets</a>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ===== SPONSORS (uniform tiles + seamless loop from last back to first) ===== -->
<div class="sponsors-band" aria-label="Sponsors">
  <div class="sponsors-inner">
    <div class="sponsors-head">
      <h3 class="sponsors-title">Sponsors</h3>
      <p class="sponsors-note">Thank you to our partners powering the community</p>
    </div>

    {% comment %}
      Dynamically collect all images in /assets/img/sponsors/
      (PNG/SVG/JPG/WEBP/GIF) and duplicate once for a seamless loop.
    {% endcomment %}
    {% assign all = site.static_files | where_exp: "f", "f.path contains '/assets/img/sponsors/'" %}
    {% assign img_exts = ".png,.svg,.jpg,.jpeg,.webp,.gif,.PNG,.SVG,.JPG,.JPEG,.WEBP,.GIF" %}
    {% assign paths = "" %}
    {% for f in all %}
      {% if img_exts contains f.extname %}
        {% assign paths = paths | append: f.path | append: "||" %}
      {% endif %}
    {% endfor %}
    {% assign logos = paths | split:"||" | uniq | sort | reject: "" %}

    {% if logos.size > 0 %}
      <div class="logo-marquee">
        <div class="logo-track" id="logoTrack-events">
          {%- for p in logos -%}
            {% assign name = p | split:'/' | last | split:'.' | first | replace:'-',' ' | replace:'_',' ' %}
            <div class="logo-box" title="{{ name | capitalize }}">
              <img class="logo" src="{{ p | relative_url }}" alt="{{ name | capitalize }}" loading="lazy" decoding="async">
            </div>
          {%- endfor -%}
          {%- comment -%} duplicate for seamless loop {%- endcomment -%}
          {%- for p in logos -%}
            {% assign name = p | split:'/' | last | split:'.' | first | replace:'-',' ' | replace:'_',' ' %}
            <div class="logo-box" title="{{ name | capitalize }}">
              <img class="logo" src="{{ p | relative_url }}" alt="{{ name | capitalize }}" loading="lazy" decoding="async">
            </div>
          {%- endfor -%}
        </div>
      </div>
    {% else %}
      <p style="text-align:center;"><em>Add sponsor logo files to <code>assets/img/sponsors/</code> to populate this slider.</em></p>
    {% endif %}
  </div>
</div>

<script>
(function(){
  /* ===== Sponsors: dynamic seamless marquee for this page =====
     Measure ONE SET width and set:
     --loop-distance to exact px; --loop-duration so speed ≈ 140 px/s. */
  const track = document.getElementById('logoTrack-events');
  if (track) {
    const children = Array.from(track.children);
    const half = Math.floor(children.length / 2); // one logical set
    if (half > 0) {
      let distance = 0;
      for (let i = 0; i < half; i++) {
        const el = children[i];
        const style = window.getComputedStyle(el);
        const ml = parseFloat(style.marginLeft) || 0;
        const mr = parseFloat(style.marginRight) || 0;
        distance += el.getBoundingClientRect().width + ml + mr;
      }
      track.style.setProperty('--loop-distance', distance + 'px');

      /* SPEED: higher = faster (matching home page faster setting) */
      const pxPerSec = 140; // try 120–180 for brisk; raise for faster
      const duration = Math.max(10, Math.round(distance / pxPerSec));
      track.style.setProperty('--loop-duration', duration + 's');
    }
  }
})();
</script>
