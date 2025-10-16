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
  color:#2874c7;          /* keep your blue */
  font-weight:600;
  font-style: italic;     /* italics */
  font-size: 0.80rem;     /* slightly smaller */
  line-height: 1.2;
}
@media (max-width: 880px){
  .inline-links a { font-size: 0.9rem; }
}
/* Space between link lines */
.inline-links a + a { 
  margin-top: 8px;
}
@media (min-width: 881px){
  .inline-links a + a { margin-top: 10px; }
}

.inline-links a:visited { color:#2874c7; }
.inline-links a:hover,
.inline-links a:focus { text-decoration: underline; }
.inline-links a:active { opacity: .9; }
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

<!-- ===== Compact Sponsors Slider (dynamic, full-bleed) ===== -->
{% include sponsors_slider.html title="Sponsors" note="Thank you to our partners powering the community." %}
