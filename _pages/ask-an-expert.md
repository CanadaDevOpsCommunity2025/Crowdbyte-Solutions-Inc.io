---
layout: single
permalink: /ask-an-expert/
title: "Ask an Expert"
sidebar: false
classes: "full-bleed"
---

<style>
/* Hide pager */
.pagination, .pagination--pager { display:none !important; }

/* Center the Crowdbyte DevOps + AI subtitle */
.subtitle {
  text-align: center !important;
  margin-left: auto;
  margin-right: auto;
}

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
/* Center the page title */
.page__title {
  text-align: center !important;
  margin-left: auto;
  margin-right: auto;
}
.subtitle {
  font-weight:800;
  color:#2874c7;
  font-size: clamp(18px,2.2vw,22px);
  margin: 6px 0 12px;
  text-align: center;   /* was: left */
}

/* ===== Hero band ===== */
.hero { 
  background:#2f5597;
  color:#fff;
  padding: clamp(28px,5vw,56px) clamp(12px,3vw,32px);
  text-align: center;   /* was: left */
}
.hero h1{
  margin:0;
  font-weight:800;
  font-size: clamp(26px,4.2vw,44px);
  line-height:1.2;
}

/* ===== Body (FULL WIDTH) ===== */
.wrap {
  padding: 16px clamp(12px,3vw,32px); /* small gutters only */
}

.subtitle {
  font-weight:800;
  color:#2874c7;
  font-size: clamp(18px,2.2vw,22px);
  margin: 6px 0 12px;
  text-align:left;              /* align left to emphasize width */
}

.intro {
  margin: 0 0 20px;
  line-height: 1.5;
  text-align:left;
  max-width: none;              /* remove width cap */
}

/* FULL-WIDTH GRID */
.grid {
  display:grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: clamp(12px,2vw,28px);
  margin: 0;                    /* no centering */
  max-width: none;              /* remove width cap */
}

.block { line-height:1.45; }
.block + .block { margin-top: 18px; }

.block h3 {
  margin: 0 0 6px;
  font-size: 1rem;
  font-weight: 700;
}

.block p { margin: 0 0 10px; }

/* Links like other pages */
.block a {
  color:#2874c7;
  font-style: italic;
  font-weight:600;
  text-decoration:none;
  font-size:0.95rem;
}
.block a:hover { text-decoration: underline; }
</style>

<!-- HERO -->
<div class="full-bleed-row hero">
  <h1>Blogs, newsletters, reports, share knowledge and&nbsp;best practices</h1>
</div>

<!-- MAIN -->

<div class="full-bleed-row wrap">
  <div class="subtitle">Crowdbyte&nbsp;&nbsp;<em><strong>DevOps + AI</strong></em>&nbsp;&nbsp;Community of Practice</div>

  <p class="intro">
    We’re an energetic network of technologists, builders, and innovators shaping the future of DevOps and AI in Canada.
  </p>

  <div class="grid">
    <!-- LEFT SECTION -->
    <div class="block">
      <h3>Schedule a Quick Overview</h3>
      <p>Ask <strong>us</strong> about Crowdbyte Solutions or any questions around participating from creating a pull request to starting a bigger enhancement effort.
        <a href="{{ site.baseurl }}/contact/">[link]</a>
      </p>
    </div>

    <div class="block">
      <h3>Schedule a Coffee Chat</h3>
      <p>Reach out to <strong>Garima Bajpai</strong> to learn more about Crowdbyte and how you can get involved. She can help.</p>
    </div>

    <!-- RIGHT SECTION -->
    <div class="block">
      <h3>Schedule a Coffee Chat</h3>
      <p>Reach out to <strong>Jay Shah</strong> to learn more about our open source projects, Hackathon and how you can get involved.</p>
    </div>
  </div>
</div>
