---
title: ""
permalink: /become-a-contributor/
layout: single
classes: full-bleed
---

<!-- ======================= STYLES (scoped to this page) ======================= -->
<style>
/* Pull selected sections out of the theme’s centered wrapper (full-bleed) */
.bc-hero,
.bc-band{
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
  width: 100vw;
}

/* ---------- HERO (left-aligned text, full width) ---------- */
.bc-hero{
  background:#305890;
  color:#fff;
  padding: 22px clamp(18px, 3vw, 40px);
}
.bc-hero h1{
  margin: 0;
  font-weight: 800;
  font-size: clamp(20px, 2.6vw, 26px);
  line-height: 1.25;
  text-align: left;            /* left like your mock */
}

/* ---------- CONTENT BAND (full width with comfy side padding) ---------- */
.bc-band{
  padding-left: clamp(18px, 3vw, 40px);
  padding-right: clamp(18px, 3vw, 40px);
  padding-top: 10px;
}

/* Subhead (blue) */
.bc-subhead{
  text-align: center;
  font-weight: 800;
  font-size: clamp(18px, 2.2vw, 22px);
  color:#305890;
  margin: 16px auto 6px;
}
.bc-subhead *{ color:inherit !important; background:transparent !important; padding:0 !important; border-radius:0 !important; }

/* Tagline centered across the width; single line on big screens */
.bc-tagline{
  text-align:center;
  color:#111;
  font-size: clamp(15px, 1.4vw, 18px);
  margin: 6px 0 10px;
  white-space: nowrap;
}
@media (max-width: 1100px){ .bc-tagline{ white-space: normal; }}

/* ---------- TWO-COLUMN LAYOUT: text (left) + BIG video (right) ---------- */
.bc-row{
  display:grid;
  grid-template-columns: 1fr 1.45fr; /* make video column wider */
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

/* Right column video card – big and with a thumbnail view */
.bc-video{
  background:#f3f6fb;
  border:1px solid #d7dfef;
  border-radius:12px;
  padding:10px;
}
.bc-video .thumb{
  width:100%;
  aspect-ratio: 16/9;            /* keeps the image and iframe same size */
  border-radius: 8px;
  display:block;
  object-fit: cover;
  margin:0;
  border:0;
}
.bc-video .play{
  width:100%;
  aspect-ratio: 16/9;
  border:0;
  border-radius:8px;
  display:none;                  /* hidden until user clicks the image */
}
.bc-video small{ display:block; margin-top:6px; color:#555; }

/* Footer line */
.bc-footer{ font-weight:600; margin: 18px 0 0; }
</style>

<!-- ======================= PAGE CONTENT ======================= -->

<!-- Full-width hero -->
<div class="bc-hero">
  <h1>Become Part of our Amazing Community of<br>
    Collaborator, Contributors and Sponsors</h1>
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
    <!-- LEFT: bullets -->
    <div>
      <ul class="bc-list">
        <li>Start your own DevOps for GenAI Hackathon Day</li>
        <li>Be a Spotlight contributor</li>
        <li>Drive next steps for open-source project</li>
        <li>Write for us</li>
        <li><a href="{{ '/contact/' | relative_url }}">Form to submit contribution</a></li>
      </ul>

      <p style="margin-top:18px;font-weight:600;">Sponsor Hackathon, Event or Summit</p>
    </div>

    <!-- RIGHT: BIG video with visible image -->
    <div class="bc-video">
      <!-- Thumbnail image users see first (replace with your own still if you like) -->
      <img
        class="thumb"
        src="https://img.youtube.com/vi/9CiU7HR_tQ/maxresdefault.jpg"
        alt="DevOps for GenAI Hackathon thumbnail"
        loading="lazy"
        onclick="(function(img){ img.style.display='none'; img.nextElementSibling.style.display='block'; })(this)"
      >

      <!-- The actual YouTube player; shown when the image is clicked -->
      <iframe
        class="play"
        src="https://www.youtube.com/embed/9CiU7HR_tQ?rel=0&autoplay=1"
        title="DevOps for GenAI Hackathon"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        allowfullscreen
      ></iframe>

      <small>https://youtu.be/9CiU7HR_tQ</small>
    </div>
  </div>
</div>
