---
title: ""
permalink: /become-a-contributor/
layout: single
classes: full-bleed
---

<!-- ======================= STYLES (scoped to this page) ======================= -->
<style>
/* Use full-bleed sections (edge-to-edge with safe side padding) */
.bc-hero, .bc-band{
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
  width: 100vw;
}

/* ---------- HERO (LEFT-ALIGNED, WRAPS LIKE THE MOCK) ---------- */
.bc-hero{
  background:#305890;
  color:#fff;
  padding: 22px clamp(18px, 3vw, 40px);
}
.bc-hero h1{
  margin: 0;
  font-weight: 800;
  font-size: clamp(20px, 2.4vw, 26px); /* size from the mock */
  line-height: 1.25;
  text-align: left; /* left, not centered */
}

/* ---------- CONTENT BAND ---------- */
.bc-band{
  padding-left: clamp(18px, 3vw, 40px);
  padding-right: clamp(18px, 3vw, 40px);
  padding-top: 10px;
}

/* Subhead (blue, centered) */
.bc-subhead{
  text-align: center;
  font-weight: 800;
  font-size: clamp(18px, 2.2vw, 22px);
  color:#305890;
  margin: 16px auto 6px;
}
.bc-subhead *{ color:inherit !important; background:transparent !important; padding:0 !important; border-radius:0 !important; }

/* Tagline centered, with the same break as the screenshot */
.bc-tagline{
  text-align:center;
  color:#111;
  font-size: 16px;
  margin: 6px 0 10px;
}

/* ---------- TWO COLUMNS: LEFT BIGGER, RIGHT (VIDEO) MEDIUM ---------- */
.bc-row{
  display:grid;
  grid-template-columns: 1.6fr 0.9fr;  /* left bigger, right medium */
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

/* Right column video card (medium size with visible thumbnail) */
/* Video box = exact video size, no extra padding/border */
.bc-video{
  width: min(520px, 100%);   /* medium width; change to 500/560 if you prefer */
  justify-self: end;         /* align to the right column edge */
  padding: 0;                /* no padding around the player */
  background: transparent;   /* no background box */
  border: 0;                 /* no border so box = video */
}

/* Responsive 16:9 player that fills the box */
.bc-video iframe{
  display: block;
  width: 100%;
  aspect-ratio: 16 / 9;      /* keeps correct height automatically */
  height: auto;
  border: 0;
}

/* On phones, let it go full width */
@media (max-width: 980px){
  .bc-video{ width: 100%; justify-self: stretch; }
}


/* Footer line */
.bc-footer{ font-weight:600; margin: 18px 0 0; }
</style>

<!-- ======================= PAGE CONTENT ======================= -->

<!-- Full-width hero (left-aligned, wraps like the screenshot) -->
<div class="bc-hero">
  <h1>Become Part of our Amazing Community of<br>
    Collaborator, Contributors and Sponsors</h1>
</div>

<!-- Full-width band for the rest -->
<div class="bc-band">
  <p class="bc-subhead">
    <span>Crowdbyte</span> <span>DevOps + AI</span> Community of Practice
  </p>

  <!-- Force the same line break as the image (Canada on a new line) -->
  <p class="bc-tagline">
    We’re an energetic, network of technologists, builders, and innovators shaping the future of DevOps and AI in<br>
    Canada.
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
        src="https://www.youtube.com/watch?v=9CiUU7HR_tQ"
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
