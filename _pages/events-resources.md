---
layout: single
permalink: /events-resources/
title: "Events and Resources"
sidebar: false
classes: "full-bleed"
---

<style>
/* Hide the Previous / Next pager on this page only */
.pagination, .pagination--pager { display:none !important; }

/* ===== Full-bleed layout (edge-to-edge) ===== */
.page.full-bleed .page__inner-wrap,
.page.full-bleed .page__content {
  max-width: none !important;
  padding-left: 0 !important;
  padding-right: 0 !important;
}
.full-bleed-row { width:100vw; margin-left:calc(50% - 50vw); margin-right:calc(50% - 50vw); }

/* Center the page title */
.page__title { text-align:center !important; margin-left:auto; margin-right:auto; }

/* ===== Hero band ===== */
.cb-hero{
  background:#2f5597; color:#fff; padding:28px 24px; text-align:center;
}
.cb-hero h1{ margin:0; font-weight:800; font-size:clamp(24px,3.6vw,40px); line-height:1.2; }

/* ===== Body ===== */
.cb-wrap { padding: 20px clamp(16px,3vw,24px); }

/* Title + intro */
.cb-title{
  text-align:center; font-weight:800; margin:10px 0; font-size: clamp(18px, 2.2vw, 24px);
}
.cb-title .hl{ color:#2874c7; text-decoration: underline; }
.cb-intro{ text-align:center; margin:6px 0 18px; }
.cb-intro strong{ display:block; }

/* ===== Three-column layout ===== */
.er-grid3{
  display:grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 18px;
  max-width: 1200px;
  margin: 0 auto;
}
@media (max-width: 980px){ .er-grid3{ grid-template-columns: 1fr 1fr; } }
@media (max-width: 680px){ .er-grid3{ grid-template-columns: 1fr; } }

/* Column header (title + pill button) */
.col-head{
  display:flex; align-items:center; justify-content:flex-start; gap:10px;
  margin-bottom: 8px;
}
.col-title{
  display:inline-block;
  background:#2f74d0; color:#fff; font-weight:800;
  padding:6px 10px; border-radius:8px; font-size:14px; letter-spacing:.2px;
}
.pill-btn{
  margin-left: 6px;
  display:inline-block; font-weight:800; font-size:14px;
  color:#fff !important; text-decoration:none;
  background:#7fb0f0; border:1px solid rgba(0,0,0,.1);
  padding:6px 10px; border-radius:8px;
}
.pill-btn:hover{ filter:brightness(1.05); }

/* Cards */
.tile-card{
  background:#e9eff7; border:1px solid #d2dbe8; border-radius:4px;
  padding: 10px 12px;
}
.tile-card + .tile-card{ margin-top: 12px; }
.tile-card h4{ margin:0 0 6px; color:#1f3c6d; font-weight:800; font-size: 15px; }
.tile-card p{ margin:.25rem 0; }
.tile-card .muted{ color:#2b4f8b; font-weight:700; }

/* Inline links list */
.inline-links a{
  display:block; color:#2874c7; text-decoration:none; font-weight:600; font-style:italic;
  font-size:.92rem; line-height:1.25;
}
.inline-links a + a{ margin-top:.25rem; }
.inline-links a:hover, .inline-links a:focus{ text-decoration:underline; }

/* ===== Pretty “Agenda” button ===== */
.btn-row{ margin-top:6px; }
.btn-agenda{
  display:inline-flex; align-items:center; gap:8px;
  padding:8px 12px;
  border-radius:999px;
  font-weight:800; font-size:14px;
  text-decoration:none;
  color:#fff !important;
  background: linear-gradient(180deg, #3b82f6 0%, #1d4ed8 100%);
  border:1px solid rgba(255,255,255,.2);
  box-shadow: 0 6px 16px rgba(29,78,216,.25), inset 0 1px 0 rgba(255,255,255,.06);
  transition: transform .1s ease, box-shadow .1s ease, filter .1s ease;
}
.btn-agenda:hover{ transform: translateY(-1px); filter:brightness(1.03); box-shadow:0 8px 18px rgba(29,78,216,.35); }
.btn-agenda:active{ transform: translateY(0); }
.btn-agenda:focus-visible{ outline:3px solid #93c5fd; outline-offset:2px; }
.btn-agenda .ico{ width:16px; height:16px; display:block; }

/* ===== SPONSORS (uniform tiles + seamless loop) ===== */
.sponsors-band{
  width:100vw; margin-left:calc(50% - 50vw); margin-right:calc(50% - 50vw);
  background: linear-gradient(180deg, #f7f9ff 0%, #eef4ff 100%);
  border-top: 1px solid rgba(0,0,0,.06);
  border-bottom: 1px solid rgba(0,0,0,.06);
  padding: clamp(12px, 1.8vw, 18px) 0;
  margin-top: clamp(24px, 3.2vw, 48px);
}
.sponsors-inner{ max-width:1200px; margin:0 auto; padding:0 clamp(10px, 2.6vw, 20px); }
.sponsors-head{ display:flex; flex-direction:column; align-items:center; gap:6px; margin-bottom:10px; text-align:center; }
.sponsors-title{ margin:0; font-weight:900; font-size: clamp(15px, 1.8vw, 18px); color:#172b4d; }
.sponsors-note{ margin:0; font-size: clamp(.86rem, 1.3vw, .95rem); color:#51657d; }
.logo-marquee{ position:relative; overflow:hidden; }
.logo-track{
  --loop-distance: 50%; --loop-duration: 26s;
  display:flex; align-items:center; gap:12px; will-change:transform;
  animation: sponsors-marquee var(--loop-duration) linear infinite;
}
.logo-track:hover{ animation-play-state: paused; }
@keyframes sponsors-marquee{ from{transform:translateX(0)} to{transform:translateX(calc(-1 * var(--loop-distance)))} }

:root{ --tile-w: 170px; --tile-h: 60px; }
.logo-box{
  flex:0 0 auto; width:var(--tile-w); height:var(--tile-h);
  display:flex; align-items:center; justify-content:center;
  background:#fff; border:1px solid rgba(23,43,77,.10); border-radius:10px;
  box-shadow:0 6px 18px rgba(23,43,77,.08); padding:6px; overflow:hidden;
}
.logo{ display:block; max-width:100%; max-height:100%; width:auto; height:auto; object-fit:contain; }

/* Reduced motion */
@media (prefers-reduced-motion: reduce){ .logo-track{ animation:none; } }
</style>

<!-- HERO -->
<div class="full-bleed-row cb-hero">
  <h1>We’re more than a community—we’re a movement!</h1>
</div>

<!-- MAIN -->
<div class="full-bleed-row cb-wrap">
  <h2 class="cb-title">
    <span class="hl">Crowdbyte&nbsp;&nbsp;<em><strong>DevOps + AI</strong></em>&nbsp;&nbsp;Community of Practice</span>
  </h2>
  <p class="cb-intro">
    We’re an energetic, network of technologists, builders, and innovators shaping the future of DevOps and AI in <strong>Canada.</strong>
  </p>

  <!-- ===== 3 COLUMN LAYOUT ===== -->
  <div class="er-grid3">

    <!-- ==== Column: Events ==== -->
    <section>
      <div class="col-head">
        <span class="col-title">Events</span>
        <!-- UPDATED: direct Eventbrite link -->
        <a class="pill-btn"
           href="https://www.eventbrite.ca/e/devops-for-genai-hackathon-tickets-1407877793379"
           target="_blank" rel="noopener"
           aria-label="Register now on Eventbrite">
          Register now
        </a>
      </div>

      <div class="tile-card">
        <h4>DevOps for GenAI,<br/>Hackathon Series Global</h4>
        <div class="inline-links">
          <a href="{{ site.baseurl }}/contact/">Become a Sponsor</a>
          <a href="{{ site.baseurl }}/contact/">Propose a Location</a>
        </div>
      </div>

      <div class="tile-card">
        <h4>AI Summit, Canada<br/>DevOps Summit, Canada</h4>
        <div class="inline-links">
          <a href="{{ site.baseurl }}/contact/">Become a Sponsor</a>
          <a href="#">Submit Speaker Proposal</a>
        </div>
      </div>
    </section>

    <!-- ==== Column: Workshops ==== -->
    <section>
      <div class="col-head">
        <span class="col-title">Workshops</span>
        <!-- UPDATED: Coming Soon text, link to Contact Us page -->
        <a class="pill-btn"
           href="{{ site.baseurl }}/contact/"
           aria-label="Coming soon — provide your email to share interest via Contact Us">
          Coming Soon — Share Interest
        </a>
      </div>

      <div class="tile-card">
        <h4>Operationalizing AI — One Day Workshop for Leaders</h4>
        <div class="btn-row">
          <a class="btn-agenda" href="#" aria-label="Open agenda for Operationalizing AI workshop">
            <svg class="ico" viewBox="0 0 16 16" aria-hidden="true"><path fill="currentColor" d="M11 1h1v2h2v1H2V3h2V1h1v2h6V1zM2 6h12v8a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V6zm2 2v2h3V8H4zm4 0v2h4V8H8zm0 3v2h4v-2H8zM4 11v2h3v-2H4z"/></svg>
            Agenda
          </a>
        </div>
      </div>

      <div class="tile-card">
        <h4>AI Bootcamp — Two Day Workshop for Leaders and Executives</h4>
        <div class="btn-row">
          <a class="btn-agenda" href="#" aria-label="Open agenda for AI Bootcamp">
            <svg class="ico" viewBox="0 0 16 16" aria-hidden="true"><path fill="currentColor" d="M11 1h1v2h2v1H2V3h2V1h1v2h6V1zM2 6h12v8a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V6zm2 2v2h3V8H4zm4 0v2h4V8H8zm0 3v2h4v-2H8zM4 11v2h3v-2H4z"/></svg>
            Agenda
          </a>
        </div>
      </div>

      <div class="tile-card">
        <h4>AI Transformation Day — One day fulfilled learning event</h4>
        <div class="btn-row">
          <a class="btn-agenda" href="#" aria-label="Open agenda for AI Transformation Day">
            <svg class="ico" viewBox="0 0 16 16" aria-hidden="true"><path fill="currentColor" d="M11 1h1v2h2v1H2V3h2V1h1v2h6V1zM2 6h12v8a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V6zm2 2v2h3V8H4zm4 0v2h4V8H8zm0 3v2h4v-2H8zM4 11v2h3v-2H4z"/></svg>
            Agenda
          </a>
        </div>
      </div>

      <div class="tile-card">
        <h4>AI Security Bootcamp — Half day Security workshop for Leaders</h4>
        <div class="btn-row">
          <a class="btn-agenda" href="#" aria-label="Open agenda for AI Security Bootcamp">
            <svg class="ico" viewBox="0 0 16 16" aria-hidden="true"><path fill="currentColor" d="M11 1h1v2h2v1H2V3h2V1h1v2h6V1zM2 6h12v8a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V6zm2 2v2h3V8H4zm4 0v2h4V8H8zm0 3v2h4v-2H8zM4 11v2h3v-2H4z"/></svg>
            Agenda
          </a>
        </div>
      </div>
    </section>

    <!-- ==== Column: Services ==== -->
    <section>
      <div class="col-head">
        <span class="col-title">Services</span>
        <a class="pill-btn" href="{{ site.baseurl }}/submit-contribution/">Request now</a>
      </div>

      <div class="tile-card">
        <h4>Custom Hackathons</h4>
      </div>

      <div class="tile-card">
        <h4>Networking Services</h4>
        <p>Developer Days &amp; Meetups<br/>Roundtables and Webinars<br/>Custom Events</p>
      </div>

      <div class="tile-card">
        <h4>Support Services</h4>
        <p>Blog Package, reports &amp; surveys<br/>Project Management Services</p>
      </div>
    </section>

  </div><!-- /er-grid3 -->
</div><!-- /cb-wrap -->

<!-- ===== SPONSORS (uniform tiles + seamless loop) ===== -->
<div class="sponsors-band" aria-label="Sponsors">
  <div class="sponsors-inner">
    <div class="sponsors-head">
      <h3 class="sponsors-title">Sponsors</h3>
      <p class="sponsors-note">Thank you to our partners powering the community</p>
    </div>

    {% assign all = site.static_files | where_exp: "f", "f.path contains '/assets/img/sponsors/'" %}
    {% assign img_exts = ".png,.svg,.jpg,.jpeg,.webp,.gif,.PNG,.SVG,.JPG,.JPEG,.WEBP,.GIF" %}
    {% assign paths = "" %}
    {% for f in all %}
      {% if img_exts contains f.extname %}
        {% assign paths = paths | append: f.path | append: "||" %}
      {% endif %}
    {% endfor %}
    {% assign logos = paths | split:"||" | uniq | sort | reject: "" %}

    {% if logos.size > 0 %}
      <div class="logo-marquee">
        <div class="logo-track" id="logoTrack-events">
          {%- for p in logos -%}
            {% assign name = p | split:'/' | last | split:'.' | first | replace:'-',' ' | replace:'_',' ' %}
            <div class="logo-box" title="{{ name | capitalize }}">
              <img class="logo" src="{{ p | relative_url }}" alt="{{ name | capitalize }}" loading="lazy" decoding="async">
            </div>
          {%- endfor -%}
          {%- for p in logos -%}
            {% assign name = p | split:'/' | last | split:'.' | first | replace:'-',' ' | replace:'_',' ' %}
            <div class="logo-box" title="{{ name | capitalize }}">
              <img class="logo" src="{{ p | relative_url }}" alt="{{ name | capitalize }}" loading="lazy" decoding="async">
            </div>
          {%- endfor -%}
        </div>
      </div>
    {% else %}
      <p style="text-align:center;"><em>Add sponsor logo files to <code>assets/img/sponsors/</code> to populate this section.</em></p>
    {% endif %}
  </div>
</div>

<script>
(function(){
  /* Sponsors: dynamic seamless marquee (brisk) */
  const track = document.getElementById('logoTrack-events');
  if (track) {
    const children = Array.from(track.children);
    const half = Math.floor(children.length / 2);
    if (half > 0) {
      let distance = 0;
      for (let i = 0; i < half; i++) {
        const el = children[i];
        const style = window.getComputedStyle(el);
        const ml = parseFloat(style.marginLeft) || 0;
        const mr = parseFloat(style.marginRight) || 0;
        distance += el.getBoundingClientRect().width + ml + mr;
      }
      track.style.setProperty('--loop-distance', distance + 'px');
      const pxPerSec = 140;
      const duration = Math.max(10, Math.round(distance / pxPerSec));
      track.style.setProperty('--loop-duration', duration + 's');
    }
  }
})();
</script>
