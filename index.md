---
title: ""
layout: single
classes: full-bleed
---
<!-- Inline fallback styles: guarantees hero + 4 columns now -->
<style>
/* ===== FORCE FULL-WIDTH (works regardless of theme wrappers) ===== */
.page.full-bleed .page__title{ display:none !important; }

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
/* Center the page title */
.page__title {
  text-align: center !important;
  margin-left: auto;
  margin-right: auto;
}

/* Hero look */
.hero-band{ background:#2a3e6e; color:#fff; text-align:center; padding:2.5rem 1rem; }
.hero-band h1{ margin:0; font-size:clamp(1.8rem,3.5vw,2.4rem); font-weight:800; }

/* ===== BIG, CLEAR GITHUB CTA BUTTON ===== */
.hero-band-inner{
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  flex-wrap: wrap;
}
.cta-github{
  --gh: 28px; /* logo size (auto-scales on small screens below) */
  display:inline-flex; align-items:center; gap:10px;
  padding:14px 18px;
  border-radius:12px;
  font-weight:800; font-size:18px;
  text-decoration:none;
  background:linear-gradient(180deg,#111,#000);
  color:#fff;
  border:1px solid rgba(255,255,255,.18);
  box-shadow:0 10px 24px rgba(0,0,0,.25), inset 0 1px 0 rgba(255,255,255,.05);
  transition:transform .12s ease, box-shadow .12s ease, background .12s ease;
}
.cta-github:hover{ transform:translateY(-1px); box-shadow:0 12px 28px rgba(0,0,0,.32); }
.cta-github:active{ transform:translateY(0); }
.cta-github:focus-visible{ outline:3px solid #7fb0f0; outline-offset:3px; }
.cta-github .gh{ width:var(--gh); height:var(--gh); display:inline-block; flex:0 0 auto; }
@media (max-width:520px){
  .cta-github{ font-size:16px; padding:12px 16px; --gh:24px; }
}

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
  color: #3b6bbd !important;
  padding: 0 !important;
  border-radius: 0 !important;
  font-weight: 800;
  text-decoration: none;
}

/* Optional: make the section headers use the same blue as the screenshot */
.page .page__inner-wrap .page__content .card h3 {
  color: #3b6bbd;
  font-weight: 800;
}

/* Calendar emoji before marked dates */
.cal::before,
time.cal::before{
  content: "📅 ";
  letter-spacing: 0;
  vertical-align: baseline;
}

/* Simple, smaller button (used by Chapters + GitHub Repo) */
.btn-small{
  display:inline-block;
  padding:.38rem .7rem;
  border:1px solid #2a3e6e;
  border-radius:8px;
  background:#fff;
  color:#2a3e6e !important;
  font-weight:700;
  font-size:.9rem;
  text-decoration:none;
  box-shadow:none;
}
.btn-small:hover{
  background:#f5f8ff;
  border-color:#3b6bbd;
  color:#3b6bbd !important;
}
.btn-small:focus{
  outline:2px solid #99b3e6;
  outline-offset:2px;
}
/* Even smaller variant */
.btn-small.btn-tiny{
  padding:.28rem .55rem;     /* tighter */
  font-size:.82rem;          /* smaller text */
  border-radius:6px;         /* slightly squarer */
}

/* ===== FULL-SCREEN CHAPTERS OVERLAY ===== */
#chaptersOverlay{
  position:fixed; inset:0; background:rgba(8,13,26,.65);
  display:none; z-index:9999;
}
#chaptersOverlay[aria-hidden="false"]{ display:block; }
.ch-panel{
  position:relative; margin:4vh auto; max-width:1200px;
  background:#ffffff; border-radius:18px; overflow:hidden;
  box-shadow:0 20px 60px rgba(0,0,0,.35);
}
.ch-top{
  background:linear-gradient(135deg,#2f5597 0%,#2874c7 60%,#7fb0f0 100%);
  color:#fff; padding:18px 18px;
  display:flex; gap:12px; align-items:center; justify-content:space-between; flex-wrap:wrap;
}
.ch-top h2{ margin:0; font-weight:800; font-size:clamp(1.1rem,2.2vw,1.4rem); }
.ch-actions{ display:flex; gap:10px; align-items:center; }
.ch-search{
  padding:.55rem .7rem; border-radius:10px; border:none;
  min-width:220px; font-size:.95rem;
}
.ch-close{
  background:rgba(255,255,255,.14); color:#fff; border:none; border-radius:10px;
  padding:.5rem .75rem; font-weight:800; cursor:pointer;
}
.ch-close:hover{ background:rgba(255,255,255,.25); }

/* grid of chapter cards */
.ch-grid{
  display:grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap:16px; padding:16px;
}
.ch-card{
  background:#f6f8fb; border:1px solid #e6ecf8; border-radius:14px;
  padding:12px; display:flex; flex-direction:column; gap:10px;
  box-shadow:0 8px 30px rgba(2,24,71,.06);
}
.ch-city{ margin:0; color:#1f2a44; font-weight:800; font-size:1rem; }
.ch-blurb{ margin:0; color:#334155; font-size:.92rem; line-height:1.3; }
.ch-btn{
  align-self:flex-start; display:inline-block; padding:.5rem .75rem;
  border-radius:999px; background:#2f5597; color:#fff !important; text-decoration:none;
  font-weight:800; font-size:.9rem; box-shadow:0 6px 18px rgba(47,85,151,.22)
}
.ch-btn:hover{ background:#2874c7; text-decoration:none; }

/* ===== SPONSORS (uniform, professional) ===== */
.sponsors-band-home{
  width: 100vw;
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
  background: linear-gradient(180deg, #f7f9ff 0%, #eef4ff 100%);
  border-top: 1px solid rgba(0,0,0,.06);
  border-bottom: 1px solid rgba(0,0,0,.06);
  padding: clamp(14px, 2vw, 22px) 0;
  margin-top: clamp(28px, 4vw, 60px);
}
.sponsors-inner{
  max-width: 1200px; margin: 0 auto;
  padding: 0 clamp(12px, 3vw, 24px);
}
.sponsors-head{
  display:flex; align-items:flex-end; justify-content:space-between; gap:10px;
  margin-bottom: clamp(10px, 1.6vw, 14px);
}
.sponsors-title{ margin:0; font-weight:900; font-size: clamp(16px, 2vw, 20px); color:#172b4d; }
.sponsors-note{ margin:0; font-size:.92rem; color:#51657d; }

/* Row of uniform tiles */
.sponsors-tiles{
  display:flex; flex-wrap:wrap; gap: clamp(12px, 1.8vw, 18px);
  justify-content:center;
}

/* Uniform tile: same size for all; logo sits inside */
.logo-box{
  flex: 0 1 auto;
  width: clamp(160px, 18vw, 220px);
  height: clamp(56px, 6vw, 72px);
  display:flex; align-items:center; justify-content:center;
  background:#fff;
  border:1px solid rgba(23,43,77,.10);
  border-radius: 12px;
  box-shadow: 0 8px 22px rgba(23,43,77,.08);
  padding: clamp(8px, 1.2vw, 12px);
  transition: transform .15s ease, box-shadow .15s ease, border-color .15s ease;
}
.logo-box:hover{
  transform: translateY(-2px);
  box-shadow: 0 12px 28px rgba(23,43,77,.12);
  border-color: rgba(23,43,77,.18);
}

/* Logo image never stretches; always contained and centered */
.logo{
  max-width: 100%;
  max-height: 100%;
  width: auto; height: auto;
  object-fit: contain;
  display:block;
  filter: saturate(1.05) contrast(1.05);
}

/* Small screens */
@media (max-width:520px){
  .sponsors-note{ text-align:center; flex:0 0 100%; }
}

/* Optional dark scheme polish */
@media (prefers-color-scheme: dark){
  .sponsors-band-home{
    background: linear-gradient(180deg, #0f1726 0%, #0c1422 100%);
    border-top-color: rgba(255,255,255,.06);
    border-bottom-color: rgba(255,255,255,.06);
  }
  .sponsors-title{ color:#eaf1ff; }
  .sponsors-note{ color:#a6b6cc; }
  .logo-box{
    background:#0f1828;
    border-color: rgba(255,255,255,.10);
    box-shadow: 0 10px 24px rgba(0,0,0,.35);
  }
}
</style>



<div class="hero-band">
  <div class="hero-band-inner">
    <h1 style="margin:0">Join our Github Community</h1>

    <!-- BIG, CLEAR CTA BUTTON -->
    <a class="cta-github"
       href="https://github.com/CanadaDevOpsCommunity2025"
       target="_blank" rel="noopener noreferrer"
       aria-label="Open our GitHub organization in a new tab">
      <!-- GitHub mark (SVG) -->
      <svg class="gh" viewBox="0 0 16 16" aria-hidden="true" focusable="false">
        <path fill="currentColor" d="M8 0C3.58 0 0 3.58 0 8c0 3.54
        2.29 6.53 5.47 7.59.4.07.55-.17.55-.38
        0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52
        0-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95
        0-.87.31-1.59.82-2.15-.08-.2-.36-1.01.08-2.11 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09
        2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.91.08 2.11.51.56.82 1.27.82 2.15
        0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.19
        0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/>
      </svg>
      <span>GitHub Repo</span>
    </a>
  </div>
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
      <li><strong>DevOps for Gen AI Hackathon — Toronto</strong><br><span class="cal">November 3, 2025</span></li>
      <p><a href="https://www.eventbrite.ca/e/devops-for-genai-hackathon-tickets-1407877793379" target="_blank" rel="noopener noreferrer">Link to Register</a></p>
      <li><strong>DevOps for Gen AI Hackathon — Ottawa</strong><br><span class="cal">June 2, 2025</span></li>
    </ul>
  </div>

  <div class="card">
    <h3>Summits &amp; Events</h3>
    <p>The Community of Practice hosts major events throughout the year, including a summit in Canada and virtual sessions, gathering practitioners and leaders in DevOps, SRE, cloud, and AI-native practices.</p>

    <!-- Smaller CTA (unchanged size) -->
    <p><a href="#chapters" class="btn-small btn-tiny" id="openChapters">Explore Local Chapters</a></p>

    <p>Connect with us to get a quote for organizing a local event or start your own with our support.</p>
    <p><a href="{{ '/contact/' | relative_url }}">Contact Us</a></p>
  </div>

  <div class="card">
    <h3>Open-source Projects</h3>
    <p>Opportunities to co-create open-source tools such as centralized monitoring and observability solutions and taking winning projects to the next steps.</p>
    <p>Participating directly in repository yields connection with experts, peers, and industry legends.</p>
    <p>Open a new issue describing what you want to contribute. Clearly explain your proposal and the problem it addresses.</p>
    <!-- smaller GitHub Repo button -->
    <p><a class="btn-small btn-tiny" href="https://github.com/CanadaDevOpsCommunity2025" target="_blank" rel="noopener">GitHub Repo</a></p>
  </div>

  <div class="card">
    <h3>Consulting Services</h3>
    <p>Offering project management, research, and marketing support for events, product launches, and projects.</p>
    <p>Consulting and Coaching Services including workshops, training, blogs, reports, and curated resources.</p>
    <p>Organizing meetings or virtual gatherings for members to exchange ideas.</p>
    <p>Helping organizations implement CoP models for long-term cultural or operational change.</p>
    <p><a href="{{ '/contact/' | relative_url }}">Contact Us</a></p>
  </div>
</div>

<!-- ===== SPONSORS (uniform tiles, no marquee) ===== -->
<div class="sponsors-band-home" aria-label="Sponsors">
  <div class="sponsors-inner">
    <div class="sponsors-head">
      <h3 class="sponsors-title">Sponsors</h3>
      <p class="sponsors-note">Thank you to our partners powering the community</p>
    </div>

    {% comment %}
      Gather all sponsor images from /assets/img/sponsors/
    {% endcomment %}
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
      <div class="sponsors-tiles">
        {%- for p in logos -%}
          {% assign name = p | split:'/' | last | split:'.' | first | replace:'-',' ' | replace:'_',' ' %}
          <div class="logo-box" title="{{ name | capitalize }}">
            <img class="logo"
                 src="{{ p | relative_url }}"
                 alt="{{ name | capitalize }}"
                 loading="lazy" decoding="async">
          </div>
        {%- endfor -%}
      </div>
    {% else %}
      <p><em>Add sponsor logos to <code>assets/img/sponsors/</code> to populate this section.</em></p>
    {% endif %}
  </div>
</div>

<!-- ===== FULL-SCREEN OVERLAY: Chapters ===== -->
<div id="chaptersOverlay" aria-hidden="true" role="dialog" aria-label="Local chapters">
  <div class="ch-panel">
    <div class="ch-top">
      <h2>Join a Local Chapter</h2>
      <div class="ch-actions">
        <input id="chSearch" class="ch-search" type="search" placeholder="Filter by city or province…" aria-label="Filter chapters"/>
        <button class="ch-close" id="closeChapters" aria-label="Close chapters panel">Close ✕</button>
      </div>
    </div>

    <div class="ch-grid" id="chGrid">
      <!-- Ottawa -->
      <article class="ch-card" data-city="Ottawa ON Ontario">
        <h3 class="ch-city">Ottawa, ON</h3>
        <p class="ch-blurb">Ottawa DevOps &amp; DataOps Collaboration Community</p>
        <a class="ch-btn" href="https://www.meetup.com/ottawa-devops-dataops-collaboration-community" target="_blank" rel="noopener">Open Meetup</a>
      </article>

      <!-- Toronto -->
      <article class="ch-card" data-city="Toronto ON Ontario">
        <h3 class="ch-city">Toronto, ON</h3>
        <p class="ch-blurb">Canada DevOps Community of Practice — Toronto Chapter</p>
        <a class="ch-btn" href="https://www.meetup.com/canada-devops-community-of-practice-toronto-chapter" target="_blank" rel="noopener">Open Meetup</a>
      </article>

      <!-- Edmonton -->
      <article class="ch-card" data-city="Edmonton AB Alberta">
        <h3 class="ch-city">Edmonton, AB</h3>
        <p class="ch-blurb">Canada DevOps Community of Practice — Edmonton Chapter</p>
        <a class="ch-btn" href="https://www.meetup.com/canada-devops-community-of-practice-edmonton-chapter/" target="_blank" rel="noopener">Open Meetup</a>
      </article>

      <!-- Atlantic -->
      <article class="ch-card" data-city="Atlantic Provinces NS NB PE NL">
        <h3 class="ch-city">Atlantic Provinces</h3>
        <p class="ch-blurb">Community of Practice — DevOps &amp; DataOps (Atlantic)</p>
        <a class="ch-btn" href="https://www.meetup.com/community-of-practice-devops-dataops-atlantic-provinces/" target="_blank" rel="noopener">Open Meetup</a>
      </article>

      <!-- Montréal -->
      <article class="ch-card" data-city="Montreal Montréal QC Quebec Québec">
        <h3 class="ch-city">Montréal, QC</h3>
        <p class="ch-blurb">Community of Practice — DevOps &amp; DataOps (Montréal)</p>
        <a class="ch-btn" href="https://www.meetup.com/community-of-practice-devops-dataops-montreal-chapter/" target="_blank" rel="noopener">Open Meetup</a>
      </article>
    </div>
  </div>
</div>

<script>
(function(){
  const overlay = document.getElementById('chaptersOverlay');
  const openBtn = document.getElementById('openChapters');
  const closeBtn = document.getElementById('closeChapters');
  const search = document.getElementById('chSearch');
  const cards = Array.from(document.querySelectorAll('#chGrid .ch-card'));

  function openOverlay(e){
    if(e) e.preventDefault();
    overlay.setAttribute('aria-hidden','false');
    if (search) search.focus();
    document.documentElement.style.overflow='hidden';
  }
  function closeOverlay(){
    overlay.setAttribute('aria-hidden','true');
    document.documentElement.style.overflow='';
    if (openBtn) openBtn.focus();
  }
  function filter(){
    const q = (search && search.value || '').toLowerCase();
    cards.forEach(card=>{
      const hay = (card.dataset.city + ' ' + card.textContent).toLowerCase();
      card.style.display = hay.includes(q) ? '' : 'none';
    });
  }
  if (openBtn) openBtn.addEventListener('click', openOverlay);
  if (closeBtn) closeBtn.addEventListener('click', closeOverlay);
  if (overlay) overlay.addEventListener('click', (e)=>{ if(e.target===overlay) closeOverlay(); });
  document.addEventListener('keydown', (e)=>{ if(e.key==='Escape' && overlay.getAttribute('aria-hidden')==='false') closeOverlay(); });
  if (search) addEventListener('input', filter);
})();
</script>
