---
title: ""
permalink: /become-a-contributor/
layout: single
classes: full-bleed
---

<!-- ============ Styles (scoped to this page) ============ -->
<style>
/* --- full-bleed hero (unchanged) --- */
.bc-hero{
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
  width: 100vw;
  background: #305890;
  color: #fff;
  padding: 22px clamp(16px, 3vw, 36px);
}
.bc-hero h1{
  margin: 0;
  font-weight: 800;
  font-size: clamp(20px, 2.6vw, 26px);
}

/* === NEW: full-bleed band for the rest of the content === */
.bc-band{
  /* pull out of the theme’s centered wrapper */
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
  width: 100vw;
  padding-left: clamp(16px, 3vw, 36px);
  padding-right: clamp(16px, 3vw, 36px);
}

/* Subhead (blue line like home) */
.bc-subhead{
  text-align: center;
  margin: 18px auto 8px;
  font-weight: 800;
  font-size: clamp(18px, 2.2vw, 22px);
  color: #305890;
}
.bc-subhead *{
  color: inherit !important;
  background: transparent !important;
  padding: 0 !important;
  border-radius: 0 !important;
}

/* Tagline: allow full width and one line on large screens */
.bc-tagline{
  text-align: center;
  color: #111;
  font-size: clamp(15px, 1.4vw, 18px);
  margin: 6px 0 12px;
  white-space: nowrap;             /* single line on desktop */
}
@media (max-width: 1024px){
  .bc-tagline{ white-space: normal; }  /* wrap on smaller screens */
}

/* Wide two-column row */
.bc-row{
  display: grid;
  grid-template-columns: 1.25fr 1fr;   /* text left wider, video right */
  gap: clamp(16px, 2.2vw, 28px);
  align-items: start;
  margin-top: 10px;
}
@media (max-width: 920px){
  .bc-row{ grid-template-columns: 1fr; }
}

/* Left column list */
.bc-list{ margin: 10px 0 0; padding-left: 22px; }
.bc-list li{ margin: 8px 0; font-size: 16px; }

/* Right column: big video card */
.bc-video{
  background: #f3f6fb;
  border: 1px solid #d7dfef;
  border-radius: 12px;
  padding: 10px;
}
.bc-video iframe{
  width: 100%;
  aspect-ratio: 16 / 9;   /* responsive height */
  height: auto;
  border: 0;
  border-radius: 8px;
}
.bc-video small{
  display: block;
  margin-top: 6px;
  color: #555;
}

/* Footer line at bottom */
.bc-footer{
  margin: 18px 0 0;
  font-weight: 600;
}
</style>


<!-- ============ Page content ============ -->

<div class="bc-hero">
  <div class="bc-wrap">
    <h1>Become Part of our Amazing Community of<br>
      Collaborator, Contributors and Sponsors</h1>
  </div>
</div>

<div class="bc-wrap">
  <p class="bc-subhead">
    <span>Crowdbyte</span> <span>DevOps + AI</span> Community of Practice
  </p>

  <p class="bc-tagline">
    We’re an energetic, network of technologists, builders, and innovators shaping the future of DevOps and AI in Canada.
  </p>

  <div class="bc-row">
    <!-- Left: bullets -->
    <div>
      <ul class="bc-list">
        <li>Start your own DevOps for GenAI Hackathon Day</li>
        <li>Be a Spotlight contributor</li>
        <li>Drive next steps for open-source project</li>
        <li>Write for us</li>
        <li>
          <a href="{{ '/contact/' | relative_url }}" rel="noopener">Form to submit contribution</a>
        </li>
      </ul>
    </div>

    <!-- Right: video -->
    <div class="bc-video">
      <!-- Replace the video ID if you want another clip -->
      <iframe
        src="https://www.youtube.com/embed/9CiU7HR_tQ"
        title="DevOps for GenAI Hackathon"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        allowfullscreen
      ></iframe>
      <small>https://youtu.be/9CiU7HR_tQ</small>
    </div>
  </div>

  <p class="bc-footer">Sponsor Hackathon, Event or Summit</p>
</div>
