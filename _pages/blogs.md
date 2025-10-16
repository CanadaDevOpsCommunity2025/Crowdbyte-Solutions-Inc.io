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

/* “Innovative photo” header using gradients + SVG patterns (no external images) */
.card .thumb {
  min-height: 160px;
  display:flex;
  align-items: flex-end;
  padding: 16px;
  position: relative;
  color:#fff;
}
.card .thumb h3{
  margin:0;
  color:#fff;
  font-weight:800;
  font-size: clamp(16px, 1.6vw, 22px);
  line-height:1.25;
  text-shadow: 0 2px 12px rgba(0,0,0,.28);
  word-break: break-word;
}

/* Pattern 1: diagonal tech lines */
.thumb.c1{
  background:
    /* svg pattern */
    url("data:image/svg+xml;utf8,\
      <svg xmlns='http://www.w3.org/2000/svg' width='240' height='240' viewBox='0 0 240 240'>\
        <defs>\
          <linearGradient id='g' x1='0' y1='0' x2='1' y2='1'>\
            <stop stop-color='%23ffffff' stop-opacity='0.12' offset='0'/>\
            <stop stop-color='%23ffffff' stop-opacity='0.02' offset='1'/>\
          </linearGradient>\
        </defs>\
        <g opacity='0.7'>\
          <rect x='-60' y='100' width='360' height='4' fill='url(%23g)' transform='rotate(-30 120 120)'/>\
          <rect x='-60' y='140' width='360' height='4' fill='url(%23g)' transform='rotate(-30 120 120)'/>\
          <rect x='-60' y='180' width='360' height='4' fill='url(%23g)' transform='rotate(-30 120 120)'/>\
        </g>\
      </svg>"),
    linear-gradient(135deg, #2f5597 0%, #2874c7 55%, #7fb0f0 100%);
  background-size: auto, cover;
  background-repeat: repeat, no-repeat;
}

/* Pattern 2: isometric cubes */
.thumb.c2{
  background:
    url("data:image/svg+xml;utf8,\
      <svg xmlns='http://www.w3.org/2000/svg' width='180' height='180' viewBox='0 0 180 180'>\
        <path d='M60 10 L90 25 L60 40 L30 25 Z' fill='rgba(255,255,255,0.08)'/>\
        <path d='M90 25 L120 40 L90 55 L60 40 Z' fill='rgba(255,255,255,0.06)'/>\
        <path d='M30 25 L60 40 L30 55 L0 40 Z' fill='rgba(255,255,255,0.04)'/>\
      </svg>"),
    linear-gradient(135deg, #1a5ad7 0%, #2f5597 50%, #1f8eea 100%);
  background-size: auto, cover;
  background-repeat: repeat, no-repeat;
}

/* Pattern 3: dotted grid */
.thumb.c3{
  background:
    radial-gradient(circle at 8px 8px, rgba(255,255,255,0.20) 2px, transparent 2px),
    linear-gradient(135deg, #1a3d7c 0%, #2f5597 50%, #2874c7 100%);
  background-size: 22px 22px, cover;
}

/* Pattern 4: wave */
.thumb.c4{
  background:
    url("data:image/svg+xml;utf8,\
      <svg xmlns='http://www.w3.org/2000/svg' width='360' height='160' viewBox='0 0 360 160'>\
        <path d='M0,110 C60,140 120,80 180,100 C240,120 300,70 360,95 L360,160 L0,160 Z' fill='rgba(255,255,255,0.12)'/>\
        <path d='M0,95 C60,125 120,65 180,85 C240,105 300,55 360,80 L360,160 L0,160 Z' fill='rgba(255,255,255,0.08)'/>\
      </svg>"),
    linear-gradient(135deg, #224a95 0%, #2f5597 50%, #5aa0ef 100%);
  background-size: auto, cover;
  background-repeat: repeat-x, no-repeat;
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
        <div class="thumb c1">
          <h3>DevOps + GenAI Hackathon series energizes Ottawa tech community</h3>
        </div>
        <div class="meta">
          <span class="source">LinkedIn Pulse</span>
          <a class="btn" href="https://www.linkedin.com/pulse/devops-genai-hackathon-series-energizes-ottawa-tech-community-willis-suzxe/" target="_blank" rel="noopener">Read</a>
        </div>
      </article>

      <!-- Card 2 -->
      <article class="card">
        <div class="thumb c2">
          <h3>Accelerating GenAI innovation with DevOps hackathons</h3>
        </div>
        <div class="meta">
          <span class="source">DevOps.com</span>
          <a class="btn" href="https://devops.com/accelerating-genai-innovation-with-devops-hackathons-hackathon-insights-strategic-gaps-and-future-directions/" target="_blank" rel="noopener">Read</a>
        </div>
      </article>

      <!-- Card 3 -->
      <article class="card">
        <div class="thumb c3">
          <h3>SRE in the Age of AI</h3>
        </div>
        <div class="meta">
          <span class="source">DevOps.com</span>
          <a class="btn" href="https://devops.com/sre-in-the-age-of-ai/" target="_blank" rel="noopener">Read</a>
        </div>
      </article>

      <!-- Card 4 -->
      <article class="card">
        <div class="thumb c4">
          <h3>Cloud-first, cloud-smart to cloud-minimalism</h3>
        </div>
        <div class="meta">
          <span class="source">DevOps.com</span>
          <a class="btn" href="https://devops.com/cloud-first-cloud-smart-to-cloud-minimalism-a-strategic-shift/" target="_blank" rel="noopener">Read</a>
        </div>
      </article>
    </div>
  </div>
</div>
