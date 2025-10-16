---
layout: single
permalink: /ask-an-expert/
title: "Ask an Expert"
sidebar: false
classes: "full-bleed"
---

<style>
/* Hide Previous / Next on this page */
.pagination, .pagination--pager { display:none !important; }

/* ===== Full-bleed helpers ===== */
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

/* ===== Hero band ===== */
.hero {
  background:#2f5597; /* deep blue */
  color:#fff;
  padding: 32px 24px;
}
.hero h1{
  margin:0;
  font-weight:800;
  font-size: clamp(26px, 4.2vw, 44px);
  line-height:1.2;
}

/* ===== Body ===== */
.wrap { padding: 22px 24px; }

.subtitle {
  text-align:center;
  font-weight:800;
  color:#2874c7; /* lighter blue */
  font-size: clamp(18px, 2.2vw, 22px);
  margin: 10px 0 12px;
}

.intro {
  text-align:center;
  margin: 6px auto 20px;
  line-height: 1.45;
  max-width: 900px;
}
.intro strong { display:inline-block; }

/* Two-column grid */
.grid {
  display:grid;
  grid-template-columns: 1fr 1fr;
  gap: 28px;
  max-width: 1100px;
  margin: 0 auto;
}
@media (max-width: 880px){ .grid { grid-template-columns: 1fr; } }

.block { line-height:1.35; }
.block + .block { margin-top: 22px; }

.block h3 {
  margin: 0 0 6px;
  font-size: 1rem;
  font-weight: 700;
}

.block p { margin: 0 0 10px; }

/* Links styled like your other pages */
.block a {
  color:#2874c7;
  font-style: italic;
  font-weight:600;
  text-decoration: none;
  font-size: 0.95rem;
}
.block a:hover { text-decoration: underline; }
</style>

<!-- HERO -->
<div class="full-bleed-row hero">
  <h1>Blogs, newsletters, reports, share<br/>knowledge and&nbsp;best practices</h1>
</div>

<!-- MAIN -->
<div class="full-bleed-row wrap">
  <div class="subtitle">Crowdbyte&nbsp;&nbsp;<em><strong>DevOps + AI</strong></em>&nbsp;&nbsp;Community of Practice</div>

  <p class="intro">
    We’re an energetic, network of technologists, builders, and innovators shaping the future of DevOps and AI in
    <strong>Canada.</strong>
  </p>

  <div class="grid">
    <!-- LEFT COLUMN -->
    <div>
      <div class="block">
        <h3>Schedule a Quick Overview</h3>
        <p>Ask <strong>Steve Taylor</strong> about Ortelius or any questions around participating — from creating a pull request to starting a bigger enhancement effort.
          <a href="{{ site.baseurl }}/contact/">[link]</a>
        </p>
      </div>

      <div class="block">
        <h3>Schedule a Coffee Chat</h3>
        <p>Reach out to <strong>Garima Bajpai</strong> to learn more about the Crowdbyte and how you can get involved. She can help.</p>
      </div>
    </div>

    <!-- RIGHT COLUMN -->
    <div>
      <div class="block">
        <h3>Schedule a Coffee Chat</h3>
        <p>Reach out to <strong>Jay Shah</strong> to learn more about our open source projects, Hackathon and how you can get involved.</p>
      </div>
    </div>
  </div>
</div>
