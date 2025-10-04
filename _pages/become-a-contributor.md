---
title: ""
permalink: /become-a-contributor/
layout: single
classes: full-bleed
---

<!-- ======================= STYLES (scoped to this page) ======================= -->
<style>
/* Make hero + content full-bleed */
.bc-hero, .bc-band{
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
  width: 100vw;
}

/* ---------- HERO (centered, single line on desktop) ---------- */
.bc-hero{
  background:#305890;
  color:#fff;
  padding: 22px clamp(18px, 3vw, 40px);
}
.bc-hero h1{
  margin: 0;
  font-weight: 800;
  font-size: clamp(18px, 1.9vw, 24px); /* tuned to keep one line */
  line-height: 1.2;
  text-align: center;
  white-space: nowrap;   /* single line on wide screens */
  overflow: hidden;
  text-overflow: ellipsis;
}
/* Allow wrapping on tablets/phones */
@media (max-width: 1024px){
  .bc-hero h1{ white-space: normal; }
}

/* ---------- CONTENT BAND (full width with comfortable padding) ---------- */
.bc-band{
  padding-left: clamp(18px, 3vw, 40px);
  padding-right: clamp(18px, 3vw, 40px);
  padding-top: 10px;
}

/* Subhead (same blue as brand) */
.bc-subhead{
  text-align: center;
  font-weight: 800;
  font-size: clamp(18px, 2.2vw, 22px);
  color:#305890;
  margin: 16px auto 6px;
}
.bc-subhead *{
  color:inherit !important;
  background:transparent !important;
  padding:0 !important;
  border-radius:0 !important;
}

/* Tagline centered; single line on large screens */
.bc-tagline{
  text-align:center;
  color:#111;
  font-size: clamp(15px, 1.4vw, 18px);
  margin: 6px 0 10px;
  white-space: nowrap;
}
@media (max-width: 1100px){ .bc-tagline{ white-space: normal; }}

/* ---------- TWO-COLUMN: LEFT bigger (text), RIGHT medium (video) ---------- */
.bc-row{
  display:grid;
  grid-template-columns: 1.5fr 1fr;  /* left wider */
  gap: clamp(16px, 2.2vw, 28px);
  align-items:start;
  margin-top: 10px;
}
@media (max-width: 980px){
  .bc-row{ grid-template-columns: 1fr; }
}

/* Left column list */
.bc-list{ margin: 8px 0 0; padding-left: 22px; }
.bc-list li{ margin: 8px 0; font-size: 16px; }

/* Right column video card (medium size) */
.bc-video{
  background:#f3f6fb;
  border:1px solid #d7dfef;
  border-radius:12px;
  padding:10px;
  max-width: 720px; /* keeps it medium even on huge screens */
}
.bc-video .thumb,
.bc-video .play{
  width:100%;
  aspect-ratio: 16/9;
  height:auto;
  border:0;
  border-radius:8px;
  display:block;
}
.bc-video .play{ display:none; } /* hidden until click */
.bc-video small{ display:block; margin-top:6px; color:#555; }

/* Footer line */
.bc-footer{ font-weight:600; margin: 18px 0 0; }
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
