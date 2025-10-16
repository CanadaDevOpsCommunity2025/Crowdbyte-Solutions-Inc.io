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
  min-height: 240px;
  display:flex;
  flex-direction:column;
  isolation:isolate;
}

/* Photo header (real images) */
.card .thumb {
  min-height: 200px;                 /* slightly taller for a more visual feel */
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  aspect-ratio: 16/9;                 /* consistent crop across cards */
}

/* Title + actions below the photo */
.card .meta {
  padding: 12px 14px 14px;
  display:grid;
  grid-template-columns: 1fr auto;
  gap: 10px;
  align-items:center;
  border-top: 1px solid rgba(0,0,0,.06);
}

/* SIMPLE TITLE: smaller + not bold */
.card .title-text {
  margin: 0;
  font-weight: 400;                  /* normal weight (not bold) */
  font-size: 0.95rem;                /* smaller text */
  line-height: 1.3;
  color: #1f2937;                    /* neutral dark */
}

@media (max-width: 520px){
  .card .title-text { font-size: 0.92rem; }
}
@media (min-width: 1100px){
  .card .title-text { font-size: 0.98rem; }
}

/* Button */
.card .btn {
  display:inline-block;
  line-height: 1;
  padding: 9px 13px;
  border-radius: 999px;
  background:#2f5597;
  color:#fff !important;
  text-decoration:none;
  font-weight:700;
  font-size:.88rem;
  transition: transform .05s ease, box-shadow .2s ease, background .2s ease;
  box-shadow: 0 4px 14px rgba(47,85,151,.22);
  white-space: nowrap;
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
        <div class="thumb"
             style="background-image:url('https://images.unsplash.com/photo-1551836022-4c4c79ecde51?q=80&w=1600&auto=format&fit=crop');">
        </div>
        <div class="meta">
          <h3 class="title-text">DevOps + GenAI Hackathon series energizes Ottawa tech community</h3>
          <a class="btn" href="https://www.linkedin.com/pulse/devops-genai-hackathon-series-energizes-ottawa-tech-community-willis-suzxe/" target="_blank" rel="noopener">Read</a>
        </div>
      </article>

      <!-- Card 2 -->
      <article class="card">
        <div class="thumb"
             style="background-image:url('https://images.unsplash.com/photo-1519389950473-47ba0277781c?q=80&w=1600&auto=format&fit=crop');">
        </div>
        <div class="meta">
          <h3 class="title-text">Accelerating GenAI innovation with DevOps hackathons</h3>
          <a class="btn" href="https://devops.com/accelerating-genai-innovation-with-devops-hackathons-hackathon-insights-strategic-gaps-and-future-directions/" target="_blank" rel="noopener">Read</a>
        </div>
      </article>

      <!-- Card 3 -->
      <article class="card">
        <div class="thumb"
             style="background-image:url('https://images.unsplash.com/photo-1587202372775-98927b1b5a52?q=80&w=1600&auto=format&fit=crop');">
        </div>
        <div class="meta">
          <h3 class="title-text">SRE in the Age of AI</h3>
          <a class="btn" href="https://devops.com/sre-in-the-age-of-ai/" target="_blank" rel="noopener">Read</a>
        </div>
      </article>

      <!-- Card 4 -->
      <article class="card">
        <div class="thumb"
             style="background-image:url('https://images.unsplash.com/photo-1504384308090-c894fdcc538d?q=80&w=1600&auto=format&fit=crop');">
        </div>
        <div class="meta">
          <h3 class="title-text">Cloud-first, cloud-smart to cloud-minimalism</h3>
          <a class="btn" href="https://devops.com/cloud-first-cloud-smart-to-cloud-minimalism-a-strategic-shift/" target="_blank" rel="noopener">Read</a>
        </div>
      </article>
    </div>
  </div>
</div>
