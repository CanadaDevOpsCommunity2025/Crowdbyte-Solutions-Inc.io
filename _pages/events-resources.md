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
  color:#2874c7;        /* keep your blue */
  font-weight:600;
  font-style: italic;   /* italics */
  font-size: 0.80rem;   /* slightly smaller */
  line-height: 1.2;
}
@media (max-width: 880px){
  .inline-links a { font-size: 0.9rem; }
}
/* Space between link lines */
.inline-links a + a { margin-top: 8px; }
@media (min-width: 881px){
  .inline-links a + a { margin-top: 10px; }
}

.inline-links a:visited { color:#2874c7; }
.inline-links a:hover,
.inline-links a:focus { text-decoration: underline; }
.inline-links a:active { opacity: .9; }

/* ===== COMPACT SPONSORS SLIDER (full-bleed, dynamic, UNIFORM SIZE) ===== */
.sponsors-band {
  width: 100vw;
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
  background: linear-gradient(180deg, #f7f9ff 0%, #eef4ff 100%);
  border-top: 1px solid rgba(0,0,0,.06);
  border-bottom: 1px solid rgba(0,0,0,.06);
  padding: clamp(8px, 1.6vw, 12px) 0;  /* compact height */
  margin-top: clamp(24px, 4vw, 56px);  /* sits a bit lower */
}

.sponsors-inner {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 clamp(12px, 3vw, 20px);
}
.sponsors-head {
  display:flex; align-items:center; justify-content:space-between;
  gap:10px; margin-bottom: clamp(6px, 1vw, 10px);
}
.sponsors-title {
  margin:0; font-weight:800; font-size: clamp(14px, 1.8vw, 18px); color:#1f2a44;
}
.sponsors-note { margin:0; font-size:.85rem; color:#475569; }

.logo-marquee { position:relative; overflow:hidden; }
.logo-track{
  display:flex; align-items:center;
  gap: clamp(18px, 3vw, 28px); /* or 36px on events page if you had that */
  will-change: transform;
  animation: sponsors-marquee-rtl 26s linear infinite;
}

.logo-track:hover { animation-play-state: paused; }
@keyframes sponsors-marquee-rtl {
  from { transform: translateX(0); }
  to   { transform: translateX(-50%); } /* duplicated content makes seamless loop */
}

/* UNIFORM TILES for every logo */
/* UNIFORM (BIGGER) TILES for every logo */
.logo-box{
  flex: 0 0 auto;
  width: clamp(100px, 12vw, 140px);
  height: clamp(34px, 5vw, 48px);
  display:flex; align-items:center; justify-content:center;
  background: transparent;
  border-radius: 6px;
  padding: 2px;
}


/* Fit images inside the tile without cropping */
.logo{
  max-width: 100%;
  max-height: 100%;
  width: auto; height: auto;
  object-fit: contain;
  filter:saturate(.98) contrast(1.05);
  opacity:.95; transition:transform .2s ease, opacity .2s ease, filter .2s ease;
}
.logo:hover{ transform: translateY(-1px) scale(1.03); opacity:1; filter:none; }

@media (prefers-reduced-motion: reduce) { .logo-track { animation:none; } }
@media (max-width:480px){ .sponsors-note { display:none; } }
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

<!-- ===== COMPACT SPONSORS SLIDER (dynamic, uniform tiles) ===== -->
<div class="sponsors-band" aria-label="Sponsors">
  <div class="sponsors-inner">
    <div class="sponsors-head">
      <h3 class="sponsors-title">Sponsors</h3>
      <p class="sponsors-note">Thank you to our partners powering the community.</p>
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
        <div class="logo-track">
          {%- for p in logos -%}
            {% assign name = p | split:'/' | last | split:'.' | first | replace:'-',' ' | replace:'_',' ' %}
            <div class="logo-box">
              <img class="logo" src="{{ p | relative_url }}" alt="{{ name | capitalize }}">
            </div>
          {%- endfor -%}
          {%- comment -%} duplicate for seamless loop {%- endcomment -%}
          {%- for p in logos -%}
            {% assign name = p | split:'/' | last | split:'.' | first | replace:'-',' ' | replace:'_',' ' %}
            <div class="logo-box">
              <img class="logo" src="{{ p | relative_url }}" alt="{{ name | capitalize }}">
            </div>
          {%- endfor -%}
        </div>
      </div>
    {% else %}
      <p style="margin:0.25rem 0 0.2rem;"><em>Add sponsor logo files to <code>assets/img/sponsors/</code> to populate this slider.</em></p>
    {% endif %}
  </div>
</div>
