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

/* ===== Hero band (edge to edge) ===== */
.blog-hero {
  background:#2f5597;
  color:#fff;
  padding: 36px 24px;
}
.blog-hero h1 {
  margin:0;
  font-weight:800;
  font-size: clamp(26px, 4.2vw, 44px);
  line-height:1.2;
}

/* ===== Body (edge to edge container + wide inner) ===== */
.blog-body.full-bleed-row { background:#fff; }
.blog-inner {
  /* CONTROL THE WIDE CONTENT WIDTH HERE */
  max-width: 1400px;          /* <- make wider than before */
  margin: 18px auto 56px;
  padding: 0 28px;
}

/* Centered blue sub-heading */
.blog-subtitle {
  text-align:center;
  font-weight: 800;
  color:#2874c7;
  font-size: clamp(18px, 2.2vw, 22px);
  margin: 12px 0 18px;
}

/* Intro paragraph */
.blog-intro {
  margin: 0 auto 18px;
  line-height: 1.5;
  max-width: 80ch;            /* readable width for the blurb */
  text-align: left;
}

/* ===== Links laid out in responsive columns ===== */
.blog-links {
  display: grid;
  grid-template-columns: 1fr 1fr; /* two columns on wide screens */
  gap: 16px 32px;                 /* row x column gaps */
  align-items: start;
}

/* one column on smaller screens */
@media (max-width: 900px){
  .blog-links { grid-template-columns: 1fr; }
}

/* Individual link styling */
.blog-links a {
  display:block;
  text-decoration: none;
  color:#2874c7;
  font-style: italic;
  font-weight:600;
  font-size: 0.95rem;
  line-height: 1.3;
  word-break: break-word;        /* prevent overflow on long URLs */
}
.blog-links a:hover,
.blog-links a:focus { text-decoration: underline; }
.blog-links a:visited { color:#2874c7; }
</style>

<!-- HERO (full width) -->
<div class="full-bleed-row blog-hero">
  <h1>Blogs, newsletters, reports, share<br/>knowledge and&nbsp;best practices</h1>
</div>

<!-- BODY (full width container with wide inner) -->
<div class="blog-body full-bleed-row">
  <div class="blog-inner">
    <div class="blog-subtitle">Crowdbyte&nbsp;&nbsp;<em><strong>DevOps + AI</strong></em>&nbsp;&nbsp;Community of Practice</div>

    <p class="blog-intro">
      We’re an energetic, network of technologists, builders, and innovators shaping the future of DevOps and AI in Canada.
    </p>

    <div class="blog-links">
      <a href="https://www.linkedin.com/pulse/devops-genai-hackathon-series-energizes-ottawa-tech-community-willis-suzxe/" target="_blank" rel="noopener">
        https://www.linkedin.com/pulse/devops-genai-hackathon-series-energizes-ottawa-tech-community-willis-suzxe/
      </a>

      <a href="https://devops.com/accelerating-genai-innovation-with-devops-hackathons-hackathon-insights-strategic-gaps-and-future-directions/" target="_blank" rel="noopener">
        https://devops.com/accelerating-genai-innovation-with-devops-hackathons-hackathon-insights-strategic-gaps-and-future-directions/
      </a>

      <a href="https://devops.com/sre-in-the-age-of-ai/" target="_blank" rel="noopener">
        https://devops.com/sre-in-the-age-of-ai/
      </a>

      <a href="https://devops.com/cloud-first-cloud-smart-to-cloud-minimalism-a-strategic-shift/" target="_blank" rel="noopener">
        https://devops.com/cloud-first-cloud-smart-to-cloud-minimalism-a-strategic-shift/
      </a>
    </div>
  </div>
</div>
