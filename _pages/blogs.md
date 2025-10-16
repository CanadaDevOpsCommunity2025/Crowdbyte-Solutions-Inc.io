---
layout: single
permalink: /blogs/
title: "Blogs"
sidebar: false
classes: "full-bleed"
---

<style>
/* Hide built-in page title; we use the hero heading */
.page__title { display:none !important; }

/* Hide Previous / Next pager on this page only */
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

/* ===== HERO (full width, centered) ===== */
.blog-hero {
  background:#2f5597;
  color:#fff;
  padding: clamp(28px,5vw,56px) 24px;
  text-align:center;
}
.blog-hero h1 {
  margin:0;
  font-weight:800;
  font-size: clamp(28px,4.6vw,56px);
  line-height:1.2;
  letter-spacing:.2px;
}

/* ===== BODY (full width) ===== */
.blog-body.full-bleed-row { background:#fff; }
.blog-inner {
  /* full width look with comfortable gutters */
  max-width: none;
  padding: 0 clamp(12px, 3vw, 48px);
  margin: 18px 0 64px;
}

/* Subtitle */
.blog-subtitle {
  text-align:center;
  font-weight: 800;
  color:#2874c7;
  font-size: clamp(18px, 2.2vw, 24px);
  margin: 8px 0 22px;
}

/* Intro */
.blog-intro {
  margin: 0 auto 24px;
  line-height: 1.5;
  max-width: 90ch;
  text-align: center;
}

/* ===== Card grid (edge-to-edge, responsive) ===== */
.card-grid {
  display:grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: clamp(12px, 2vw, 28px);
}

/* Blog card */
.card {
  position: relative;
  border-radius: 18px;
  overflow: hidden;
  box-shadow: 0 8px 30px rgba(0,0,0,.06);
  background: #f6f8fb;
  min-height: 220px;
  display:flex;
  flex-direction:column;
  isolation:isolate;
}

/* Poster-style “image” */
.card .thumb {
  min-height: 140px;
  background: linear-gradient(135deg, #2f5597 0%, #2874c7 45%, #7fb0f0 100%);
  display:flex;
  align-items: flex-end;
  padding: 16px;
}
.card .thumb h3{
  margin:0;
  color:#fff;
  font-weight:800;
  font-size: clamp(16px, 1.6vw, 22px);
  line-height:1.25;
  text-shadow: 0 2px 12px rgba(0,0,0,.25);
}

/* Body of card */
.card .meta {
  padding: 14px 16px 16px;
  display:flex;
  gap:12px;
  align-items:center;
  justify-content: space-between;
  flex-wrap: wrap;
}
.card .source {
  font-size:.9rem;
  font-weight:700;
  color:#2f5597;
  letter-spacing:.2px;
}

/* Button */
.card .btn {
  display:inline-block;
  line-height: 1;
  padding: 10px 14px;
  border-radius: 999px;
  background:#2f5597;
  color:#fff !important;
  text-decoration:none;
  font-weight:700;
  font-size:.92rem;
  transition: transform .05s ease, box-shadow .2s ease, background .2s ease;
  box-shadow: 0 4px 14px rgba(47,85,151,.22);
}
.card .btn:hover { background:#2874c7; text-decoration:none; }
.card .btn:active { transform: translateY(1px); }

/* Make long titles wrap nicely */
.card .thumb h3 { word-break: break-word; }
</style>

<!-- HERO -->
<div class="full-bleed-row blog-hero">
  <h1>Blogs, newsletters, reports, share knowledge and best practices</h1>
</div>

<!-- BODY -->
<div class="blog-body full-bleed-row">
  <div class="blog-inner">
    <div class="blog-subtitle">Crowdbyte&nbsp;&nbsp;<em><strong>DevOps + AI</strong></em>&nbsp;&nbsp;Community of Practice</div>

    <p class="blog-intro">
      We’re an energetic network of technologists, builders, and innovators shaping the future of DevOps and AI in Canada.
    </p>

    <!-- CARDS -->
    <div class="card-grid">
      <!-- Card 1 -->
      <article class="card">
        <div class="thumb">
          <h3>DevOps + GenAI Hackathon series energizes Ottawa tech community</h3>
        </div>
        <div class="meta">
          <span class="source">LinkedIn Pulse</span>
          <a class="btn" href="https://www.linkedin.com/pulse/devops-genai-hackathon-series-energizes-ottawa-tech-community-willis-suzxe/" target="_blank" rel="noopener">Read</a>
        </div>
      </article>

      <!-- Card 2 -->
      <article class="card">
        <div class="thumb">
          <h3>Accelerating GenAI innovation with DevOps hackathons—insights, gaps & future directions</h3>
        </div>
        <div class="meta">
          <span class="source">DevOps.com</span>
          <a class="btn" href="https://devops.com/accelerating-genai-innovation-with-devops-hackathons-hackathon-insights-strategic-gaps-and-future-directions/" target="_blank" rel="noopener">Read</a>
        </div>
      </article>

      <!-- Card 3 -->
      <article class="card">
        <div class="thumb">
          <h3>SRE in the Age of AI</h3>
        </div>
        <div class="meta">
          <span class="source">DevOps.com</span>
          <a class="btn" href="https://devops.com/sre-in-the-age-of-ai/" target="_blank" rel="noopener">Read</a>
        </div>
      </article>

      <!-- Card 4 -->
      <article class="card">
        <div class="thumb">
          <h3>Cloud-first, cloud-smart to cloud-minimalism: a strategic shift</h3>
        </div>
        <div class="meta">
          <span class="source">DevOps.com</span>
          <a class="btn" href="https://devops.com/cloud-first-cloud-smart-to-cloud-minimalism-a-strategic-shift/" target="_blank" rel="noopener">Read</a>
        </div>
      </article>
    </div>
  </div>
</div>
