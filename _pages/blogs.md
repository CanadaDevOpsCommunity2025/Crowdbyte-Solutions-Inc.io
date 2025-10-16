---
layout: single
permalink: /blogs/
title: "Blogs"
sidebar: false
classes: "full-bleed"
---

<style>
/* Hide the built-in page title so only the hero heading shows */
.page__title { display:none !important; }

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

/* ===== Hero band ===== */
.blog-hero {
  background:#2f5597;     /* deep blue */
  color:#fff;
  padding: 32px 24px;
}
.blog-hero h1 {
  margin:0;
  font-weight:800;
  font-size: clamp(26px, 4.2vw, 44px);
  line-height:1.2;
}

/* ===== Body wrapper ===== */
.blog-wrap {
  max-width: 980px;
  margin: 16px auto 48px;
  padding: 0 20px;
}

/* Centered blue sub-heading */
.blog-subtitle {
  text-align:center;
  font-weight: 800;
  color:#2874c7;           /* same blue used on Events/Resources */
  font-size: clamp(18px, 2.2vw, 22px);
  margin: 12px 0 10px;
}

/* Body intro */
.blog-intro {
  margin: 0 auto 14px;
  line-height: 1.45;
}

/* Link list styles: blue, italic, slightly smaller, spaced */
.blog-links a {
  display:block;
  text-decoration: none;
  color:#2874c7;
  font-style: italic;
  font-weight:600;
  font-size: 0.95rem;
  line-height: 1.25;
}
.blog-links a + a { margin-top: 10px; }
.blog-links a:visited { color:#2874c7; }
.blog-links a:hover, .blog-links a:focus { text-decoration: underline; }
</style>

<!-- HERO -->
<div class="full-bleed-row blog-hero">
  <h1>Blogs, newsletters, reports, share<br/>knowledge and&nbsp;best practices</h1>
</div>

<!-- MAIN -->
<div class="blog-wrap">
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
