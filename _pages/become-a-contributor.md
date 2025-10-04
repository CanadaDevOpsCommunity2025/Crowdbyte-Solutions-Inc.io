---
title: ""
permalink: /become-a-contributor/
layout: single
classes: full-bleed
---

<!-- ======================= STYLES (scoped to this page) ======================= -->
<style>
/* ---------- columns: left bigger, right narrower ---------- */
.bc-row{
  display:grid;
  grid-template-columns: 1.7fr 0.85fr;  /* shrink the video column */
  gap: clamp(16px, 2.2vw, 28px);
  align-items:start;
  margin-top: 10px;
}
@media (max-width: 980px){
  .bc-row{ grid-template-columns: 1fr; }
}

/* ---------- video card: medium width, neat aspect ---------- */
.bc-video{
  background:#f3f6fb;
  border:1px solid #d7dfef;
  border-radius:12px;
  padding:10px;
  width: min(520px, 100%);   /* cap the width so it isn’t huge */
  justify-self: end;         /* hug the right edge in its column */
}

/* keep a proper 16:9, never “tall” */
.bc-video .thumb,
.bc-video .play{
  width:100%;
  aspect-ratio: 16 / 9;
  height:auto;
  border:0;
  border-radius:8px;
  display:block;
}

/* on very large screens, keep it classy—not oversized */
@media (min-width: 1400px){
  .bc-video{ width: 540px; }
}

/* on mid screens, slightly smaller */
@media (max-width: 1200px){
  .bc-video{ width: min(480px, 100%); }
}

/* on phones, full width of the single column */
@media (max-width: 980px){
  .bc-video{ width: 100%; justify-self: stretch; }
}

</style>

<!-- ======================= PAGE CONTENT ======================= -->

<!-- Full-width hero -->
<div class="bc-hero">
  <h1>Become Part of our Amazing Community of Collaborator, Contributors and Sponsors</h1>
</div>

<!-- Full-width band for the rest -->
<div class="bc-band">
  <p class="bc-subhead">
    <span>Crowdbyte</span> <span>DevOps + AI</span> Community of Practice
  </p>

  <p class="bc-tagline">
    We’re an energetic, network of technologists, builders, and innovators shaping the future of DevOps and AI in Canada.
  </p>

  <div class="bc-row">
    <!-- LEFT: bullets (larger column) -->
    <div>
      <ul class="bc-list">
        <li>Start your own DevOps for GenAI Hackathon Day</li>
        <li>Be a Spotlight contributor</li>
        <li>Drive next steps for open-source project</li>
        <li>Write for us</li>
        <li><a href="{{ '/contact/' | relative_url }}">Form to submit contribution</a></li>
      </ul>

      <p class="bc-footer">Sponsor Hackathon, Event or Summit</p>
    </div>

    <!-- RIGHT: medium video with visible thumbnail -->
    <div class="bc-video">
      <!-- Thumbnail image (shows first). Click to load player. -->
      <img
        class="thumb"
        src="https://img.youtube.com/vi/9CiU7HR_tQ/maxresdefault.jpg"
        alt="DevOps for GenAI Hackathon thumbnail"
        loading="lazy"
        onclick="(function(img){ img.style.display='none'; var f=img.nextElementSibling; f.style.display='block'; f.src += '&autoplay=1'; })(this)"
      >
      <!-- YouTube player (revealed on click) -->
      <iframe
        class="play"
        src="https://www.youtube.com/embed/9CiU7HR_tQ?rel=0"
        title="DevOps for GenAI Hackathon"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        allowfullscreen
      ></iframe>
      <small>https://youtu.be/9CiU7HR_tQ</small>
    </div>
  </div>
</div>
