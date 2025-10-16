---
layout: single
permalink: /become-a-contributor/
title: "Become a Contributor"
sidebar: false
classes: "full-bleed"   # used by the CSS below to remove the theme's width limits
---

<style>
/* Hide the Previous / Next pager on this page only */
.pagination,
.pagination--pager { display: none !important; }
</style>

<style>
/* ===== Remove theme width limits & gutters for THIS PAGE only ===== */
.page.full-bleed .page__inner-wrap,
.page.full-bleed .page__content {
  max-width: none !important;
  padding-left: 0 !important;
  padding-right: 0 !important;
}

/* Full-bleed helper that truly spans the viewport width */
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

/* Hero band */
.cb-hero {
  background:#2f5597;
  color:#fff;
  padding: 28px 24px;
}
.cb-hero h1 {
  margin:0;
  font-weight: 800;
  font-size: clamp(22px, 3.2vw, 34px);
  line-height: 1.2;
}

/* Main content row (also full-bleed) */
.cb-wrap { padding: 20px 24px; }

/* Section heading + intro */
.cb-title { 
  text-align:center; 
  font-weight:800; 
  margin: 8px 0 14px; 
  font-size: clamp(18px, 2.2vw, 24px); 
}
.cb-title .hl { color:#2874c7; text-decoration: underline; }
.cb-intro { text-align:center; margin-bottom: 8px; }

/* Two-column layout that can breathe across the full width */
.cb-grid {
  display:grid;
  grid-template-columns: minmax(280px, 1fr) minmax(360px, 640px);
  gap: 28px;
  align-items:start;
  max-width: 1600px;          /* keep lines readable on ultra-wide screens */
  margin: 0 auto;             /* centered inside the full-bleed row */
}
@media (max-width: 880px){ .cb-grid { grid-template-columns: 1fr; } }

.cb-list { margin-top: 8px; }
.cb-list li { margin: 8px 0; }

/* Action buttons under bullets */
.cb-actions { margin-top: 12px; display:flex; gap:10px; flex-wrap:wrap; }
.cb-actions .btn { border-radius: 999px; }

/* Video */
.video-wrap { position: relative; width: 100%; aspect-ratio: 16 / 9; }
.video-wrap iframe{ position:absolute; inset:0; width:100%; height:100%; border:0; }
.video-caption{ font-size: 12px; color:#444; margin-top:8px; text-align:left; }

/* Footer line */
.cb-footer { margin: 28px auto 8px; font-weight:600; max-width:1600px; }
  
/* Hide Previous/Next pager buttons on this page */
.page.full-bleed .pagination,
.page.full-bleed .pagination--pager,
.page.full-bleed .page__footer .pagination { display:none !important; }
</style>

<!-- HERO (full width) -->
<div class="full-bleed-row cb-hero">
  <h1>Become Part of our Amazing Community of Collaborator, Contributors and Sponsors</h1>
</div>

<!-- MAIN (full width) -->
<div class="full-bleed-row cb-wrap">
  <h2 class="cb-title">
    <span class="hl">Crowdbyte&nbsp;&nbsp;<em><strong>DevOps + AI</strong></em>&nbsp;&nbsp;Community of Practice</span>
  </h2>

  <p class="cb-intro">
    We’re an energetic, network of technologists, builders, and innovators shaping the future of DevOps and AI in<br><strong>Canada</strong>
  </p>

  <div class="cb-grid">
    <div class="cb-left">
      <ul class="cb-list">
        <li>Start your own DevOps for GenAI Hackathon Day</li>
        <li>Be a Spotlight contributor</li>
        <li>Drive next steps for open-source project</li>
        <li>Write for us</li>
      </ul>

      <p><strong>Form to submit contribution</strong></p>
      <!-- Actions: go fill the dedicated form page OR contact page -->
      <div class="cb-actions">
        <a class="btn btn--primary" href="{{ site.baseurl }}/submit-contribution/">Fill Contribution Form</a>
        <a class="btn" href="{{ site.baseurl }}/contact/">Contact Us Instead</a>
      </div>
    </div>

    <div class="cb-right">
      <div class="video-wrap">
        <iframe
          src="https://www.youtube.com/embed/9CiUU7HR_tQ"
          title="DevOps for GenAI Hackathon"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          referrerpolicy="strict-origin-when-cross-origin"
          allowfullscreen>
        </iframe>
      </div>
    </div>
  </div>

  <p class="cb-footer">Sponsor Hackathon, Event or Summit</p>
</div>
