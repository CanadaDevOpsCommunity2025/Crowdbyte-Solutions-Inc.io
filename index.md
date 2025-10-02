---
title: "Home"
layout: single
classes: full-bleed
---
<!-- Inline fallback styles: guarantees hero + 4 columns now -->
<style>
/* ===== FORCE FULL-WIDTH (works regardless of theme wrappers) ===== */

/* Make hero and grid span the entire viewport width */
.hero-band,
.grid4 {
  margin-left: calc(50% - 50vw) !important;
  margin-right: calc(50% - 50vw) !important;
  width: 100vw !important;
}

/* Content padding at the edges so cards don’t touch the browser edge */
.grid4 {
  padding-left: clamp(16px, 3vw, 32px);
  padding-right: clamp(16px, 3vw, 32px);
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); /* fluid by device */
  gap: 18px;
  margin-top: 1rem;
  margin-bottom: 2rem;
}
@media (max-width: 360px){
  .grid4 { grid-template-columns: 1fr; }
}

/* Keep subhead/tagline readable but allow wider than the old 980px cap */
.subhead{
  text-align:center; margin:1.25rem auto .25rem; font-weight:800;
  font-size:clamp(1.2rem,2.5vw,1.5rem); color:#2a3e6e;
}
.tagline{
  text-align:center; font-size:1.05rem; color:#222;
  margin:.5rem auto 1.25rem;
  padding-left: clamp(16px, 3vw, 32px);
  padding-right: clamp(16px, 3vw, 32px);
  max-width: none; /* don't constrain */
}

/* Hero look */
.hero-band{ background:#2a3e6e; color:#fff; text-align:center; padding:2.5rem 1rem; }
.hero-band h1{ margin:0; font-size:clamp(1.8rem,3.5vw,2.4rem); font-weight:800; }

/* Cards */
.card{
  background:#f3f6fb; border-radius:12px; padding:14px 14px 10px;
  border:1px solid #d7dfef; min-height:320px;
}
.card h3{ margin:0 0 8px; color:#2a3e6e; font-weight:800; font-size:1.05rem; }
.card p, .card li{ font-size:.98rem; }
.card ul{ margin:0 0 0 1.1rem; }

/* Badges / section titles */
.badge{
  display:inline-block; background:#2a3e6e; color:#fff; padding:2px 8px;
  border-radius:999px; font-size:.8rem; margin-right:6px;
}
.section-title{ font-size:1.05rem; margin-top:.5rem; font-weight:700; }

/* Footer note */
.footer-note{ text-align:center; font-size:.9rem; color:#666; margin:1.5rem 0 .75rem; }

  /* Make "Crowdbyte  DevOps + AI" look like plain blue text (no pill) */
.subhead .badge {
  background: transparent !important;
  color: #3b6bbd !important;   /* match the screenshot blue */
  padding: 0 !important;
  border-radius: 0 !important;
  font-weight: 800;
  text-decoration: none;       /* no underline */
}

/* Optional: make the section headers use the same blue as the screenshot */
.page .page__inner-wrap .page__content .card h3 {
  color: #3b6bbd;
  font-weight: 800;
}
</style>



<div class="hero-band">
  <h1>Join our Github Community</h1>
</div>

<p class="subhead">
  <span class="badge">Crowdbyte</span> <span class="badge">DevOps + AI</span> Community of Practice
</p>

<p class="tagline">
  We’re an energetic, network of technologists, builders, and innovators shaping the future of DevOps and AI in Canada.
</p>

<div class="grid4">
  <div class="card">
    <h3>Best-of-Breed Hackathons</h3>
    <p>Start your open-ended or tightly themed Hackathons with community support and build the required innovation engines for quickly bringing new products and features to market.</p>
    <p>Connect with us to get a quote for organizing a local hackathon or start your own with our support.</p>
    <p class="section-title">Upcoming Hackathon</p>
    <ul>
      <li><strong>DevOps for Gen AI Hackathon — Toronto</strong><br><em>November 3, 2025</em></li>
      <li><strong>DevOps for Gen AI Hackathon — Ottawa</strong><br><em>June 2, 2025</em></li>
    </ul>
    <p><a href="https://forms.gle/" target="_blank">[ Google Form ]</a></p>
  </div>

  <div class="card">
    <h3>Summits &amp; Events</h3>
    <p>The Community of Practice hosts major events throughout the year, including a summit in Canada and virtual sessions, gathering practitioners and leaders in DevOps, SRE, cloud, and AI-native practices.</p>
    <p>Join local chapters <a href="https://www.meetup.com/" target="_blank">[ Link to meetup ]</a></p>
    <p>Connect with us to get a quote for organizing a local event or start your own with our support.</p>
    <p><a href="https://forms.gle/" target="_blank">[ Google Form ]</a></p>
  </div>

  <div class="card">
    <h3>Open-source Projects</h3>
    <p>Opportunities to co-create open-source tools such as centralized monitoring and observability solutions and taking winning projects to the next steps.</p>
    <p>Participating directly in repository yields connection with experts, peers, and industry legends.</p>
    <p>Open a new issue describing what you want to contribute. Clearly explain your proposal and the problem it addresses.</p>
    <p><a href="https://github.com/CanadaDevOpsCommunity2025" target="_blank">[ GitHub Org ]</a></p>
  </div>

  <div class="card">
    <h3>Consulting Services</h3>
    <p>Offering project management, research, and marketing support for events, product launches, and projects.</p>
    <p>Consulting and Coaching Services including workshops, training, blogs, reports, and curated resources.</p>
    <p>Organizing meetings or virtual gatherings for members to exchange ideas.</p>
    <p>Helping organizations implement CoP models for long-term cultural or operational change.</p>
    <p><a href="https://forms.gle/" target="_blank">[ Contact us | Google Form ]</a></p>
  </div>
</div>

<div class="footer-note">
  © {{ site.time | date: "%Y" }} CrowdByte Solutions Inc. — Canada DevOps Community of Practice
</div>
