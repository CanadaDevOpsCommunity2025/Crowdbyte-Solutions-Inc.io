---
layout: single
permalink: /gallery/
title: "Gallery"
classes: "full-bleed"
sidebar: false
---

<style>
/* ===== Global page tweaks ===== */
.page.full-bleed .page__inner-wrap,
.page.full-bleed .page__content { max-width: none !important; padding: 0 !important; }

/* ===== Variables (fallbacks baked in) ===== */
:root{
  --cb-blue-1:#2f5597;
  --cb-blue-2:#2874c7;
  --cb-blue-3:#7fb0f0;
  --cb-ink:#0f172a;
  --cb-muted:#475569;
  --cb-surface:#ffffff;
  --cb-glass: rgba(255,255,255,.08);
  --cb-border: rgba(0,0,0,.06);
}

/* ===== Hero ===== */
.gal-hero {
  width: 100vw; margin-left: calc(50% - 50vw); margin-right: calc(50% - 50vw);
  background: radial-gradient(1200px 480px at 50% -10%, rgba(127,176,240,.28), transparent 60%),
              linear-gradient(135deg,var(--cb-blue-1) 0%,var(--cb-blue-2) 52%,var(--cb-blue-3) 100%);
  color:#fff; text-align:center; padding: 38px 16px 28px;
  position: relative; overflow:hidden;
}
.gal-hero h1 {
  margin:0; font-weight:900; letter-spacing:.2px;
  font-size: clamp(26px,3.8vw,42px);
  text-shadow: 0 2px 18px rgba(0,0,0,.18);
}
.gal-nav { margin-top: 12px; display:flex; gap:10px; justify-content:center; flex-wrap:wrap; }
.gal-nav a{
  display:inline-flex; align-items:center; gap:.45rem;
  padding:.5rem .9rem; border-radius:999px; text-decoration:none;
  background: #fff; color:#163567 !important; font-weight:800; font-size:.92rem;
  border:1px solid rgba(255,255,255,.35);
  box-shadow: 0 8px 22px rgba(2,24,71,.15);
}
.gal-nav a:hover{ background:#eef4ff; transform: translateY(-1px); }

/* ===== Auto-scrolling filmstrip (elegant) ===== */
.strip-wrap{
  width: 100vw; margin-left: calc(50% - 50vw); margin-right: calc(50% - 50vw);
  background: linear-gradient(180deg, #f8fbff 0%, #eef4ff 100%);
  border-top: 1px solid var(--cb-border);
  border-bottom: 1px solid var(--cb-border);
  padding: clamp(10px, 1.8vw, 14px) 0;
}
.strip-inner{ max-width: 1280px; margin: 0 auto; padding: 0 clamp(12px,3vw,22px); }
.strip{
  position:relative; overflow:hidden; border-radius: 14px;
  box-shadow: 0 10px 30px rgba(2,24,71,.06);
  background:
    linear-gradient(90deg, rgba(255,255,255,0), rgba(255,255,255,.85) 6%, rgba(255,255,255,.85) 94%, rgba(255,255,255,0));
}
.strip-track{
  display:flex; align-items:center;
  gap: clamp(14px, 2.4vw, 26px);
  padding: 10px;
  will-change: transform;
  animation: strip-marquee 34s linear infinite;
}
.strip:hover .strip-track{ animation-play-state: paused; }
@keyframes strip-marquee{
  from{ transform: translateX(0); }
  to  { transform: translateX(-50%); }
}
.strip-item{
  flex: 0 0 auto;
  width: clamp(180px, 22vw, 260px);
  height: clamp(120px, 15vw, 170px);
  border-radius: 12px; overflow:hidden;
  background: var(--cb-surface);
  border:1px solid var(--cb-border);
}
.strip-img{ width:100%; height:100%; object-fit:cover; display:block; filter:saturate(1.04) contrast(1.03); }

/* ===== Main content area ===== */
.gal-wrap { padding: 22px clamp(14px, 3.4vw, 40px) 40px; }

/* Section headings */
.gal-heading{
  margin: 6px 0 12px; font-weight:900; letter-spacing:.2px;
  font-size: clamp(18px, 2.2vw, 26px); color: var(--cb-ink);
}

/* ===== Masonry grid (Photos) ===== */
.gal-masonry{
  column-gap: 16px; column-count: 1;
}
@media (min-width: 560px){ .gal-masonry{ column-count: 2; } }
@media (min-width: 900px){ .gal-masonry{ column-count: 3; } }
@media (min-width: 1280px){ .gal-masonry{ column-count: 4; } }

.gal-card{
  display: inline-block; width: 100%; margin: 0 0 16px; break-inside: avoid;
  border-radius: 14px; overflow: hidden; position:relative;
  border:1px solid var(--cb-border);
  background: #fff;
  box-shadow: 0 12px 38px rgba(2,24,71,.07);
  transform: translateZ(0);
}
.gal-img{
  display:block; width:100%; height:auto;
  aspect-ratio: 4 / 3; object-fit: cover; transition: transform .35s ease;
}
.gal-card:hover .gal-img{ transform: scale(1.03); }

/* Overlay caption on hover (elegant fade) */
.gal-cap-overlay{
  position:absolute; inset:auto 0 0 0; padding: 10px 12px;
  background: linear-gradient(180deg, rgba(0,0,0,0) 0%, rgba(6,18,38,.55) 60%, rgba(6,18,38,.75) 100%);
  color:#e8f0ff; font-weight:700; font-size:.95rem;
  opacity:0; transform: translateY(6px); transition: all .28s ease;
}
.gal-card:hover .gal-cap-overlay{ opacity:1; transform: translateY(0); }

/* Meta row */
.gal-meta{
  padding: 10px 12px; font-size:.92rem; color:#334155;
  display:flex; align-items:center; justify-content:space-between; gap:8px; background:#fff;
}
.gal-caption{ overflow:hidden; text-overflow:ellipsis; white-space:nowrap; font-weight:700; }
.gal-zoom{
  flex:0 0 auto; font-weight:800; font-size:.85rem;
  color:#2874c7; text-decoration:none; border:1px solid rgba(40,116,199,.25);
  padding: .28rem .55rem; border-radius: 999px;
}
.gal-zoom:hover{ background:#eef4ff; }

/* Helper note */
.gal-help{
  text-align:center; color:var(--cb-muted); font-size:.92rem; margin: 6px 0 18px;
}

/* ===== Videos grid ===== */
.v-grid{
  display:grid; gap: 18px; margin-top: 10px;
  grid-template-columns: 1fr;
}
@media (min-width: 680px){ .v-grid{ grid-template-columns: 1fr 1fr; } }
@media (min-width: 1080px){ .v-grid{ grid-template-columns: 1fr 1fr 1fr; } }

.v-card{
  position:relative;
  background:
    radial-gradient(600px 180px at 20% -20%, rgba(127,176,240,.15), transparent 60%),
    #ffffff;
  border: 1px solid var(--cb-border);
  border-radius: 14px; overflow: hidden;
  box-shadow: 0 12px 38px rgba(2,24,71,.07);
}
.v-embed{
  position: relative; width: 100%; padding-bottom: 56.25%;
  background:#0b1222;
}
.v-embed iframe{
  position: absolute; inset: 0; width: 100%; height: 100%; border: 0;
}
.v-cap{
  padding: 10px 12px; font-size: .95rem; color:#1f2a44; font-weight: 800;
  letter-spacing:.1px;
}

/* ===== Lightbox (glassmorphism) ===== */
#lightbox{
  position: fixed; inset:0; display:none; z-index: 9999;
  background: rgba(6,12,24,.55); backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
}
#lightbox[aria-hidden="false"]{ display:block; animation: lb-fade .18s ease; }
@keyframes lb-fade{ from{ opacity:0 } to{ opacity:1 } }

.lb-inner{
  position:absolute; inset: 0; display:grid; place-items:center;
  padding: clamp(12px, 3vw, 28px);
}
.lb-img{
  max-width: 96vw; max-height: 82vh; border-radius: 14px;
  box-shadow: 0 24px 70px rgba(0,0,0,.45);
  transform: scale(.985); animation: lb-pop .18s ease;
}
@keyframes lb-pop{ from{ transform: scale(.965); opacity:.8 } to{ transform: scale(.985); opacity:1 } }

.lb-caption{
  margin-top: 10px; color:#e6eefc; text-align:center; font-size: .98rem;
  max-width: 92vw; overflow: hidden; text-overflow: ellipsis; white-space: nowrap;
}

/* Controls */
.lb-controls{ position: absolute; inset: 0; pointer-events:none; }
.lb-btn{
  position:absolute; top:50%; transform: translateY(-50%);
  pointer-events:auto; cursor:pointer;
  width: 44px; height: 44px; border-radius: 999px; border: 1px solid rgba(255,255,255,.35);
  background: var(--cb-glass); color:#fff; display:grid; place-items:center;
  font-size: 18px; font-weight: 900; user-select:none;
}
.lb-btn:hover{ background: rgba(255,255,255,.16); }
.lb-prev{ left: 14px; }
.lb-next{ right: 14px; }

.lb-close{
  position:absolute; top: 14px; right: 14px;
  width: 42px; height: 42px; border-radius: 999px; border: 1px solid rgba(255,255,255,.35);
  background: var(--cb-glass); color:#fff; display:grid; place-items:center;
  font-size: 20px; font-weight: 900; cursor: pointer; pointer-events:auto;
}
.lb-close:hover{ background: rgba(255,255,255,.16); }

/* Accessibility + reduced motion */
@media (prefers-reduced-motion: reduce){
  .strip-track{ animation: none; }
  .gal-card .gal-img{ transition:none; }
  #lightbox[aria-hidden="false"]{ animation:none; }
  .lb-img{ animation:none; }
}

/* Hide default pager on this page */
.pagination, .pagination--pager { display:none !important; }
</style>

<!-- HERO -->
<section class="gal-hero" aria-labelledby="gallery-heading">
  <h1 id="gallery-heading">Gallery</h1>
  <div class="gal-nav">
    <a href="#photos" aria-label="Jump to photos">Photos</a>
    <a href="#videos" aria-label="Jump to videos">Videos</a>
  </div>
</section>

<!-- ===== AUTO-SCROLL FILMSTRIP ===== -->
<section class="strip-wrap" aria-label="Featured photos">
  <div class="strip-inner">
    <div class="strip">
      <div class="strip-track">
        {% comment %} Build photo list from /assets/img/gallery/ {% endcomment %}
        {% assign all = site.static_files | where_exp: "f", "f.path contains '/assets/img/gallery/'" %}
        {% assign img_exts = ".png,.svg,.jpg,.jpeg,.webp,.gif,.PNG,.SVG,.JPG,.JPEG,.WEBP,.GIF" %}
        {% assign paths = "" %}
        {% for f in all %}
          {% if img_exts contains f.extname %}
            {% assign paths = paths | append: f.path | append: "||" %}
          {% endif %}
        {% endfor %}
        {% assign images = paths | split:"||" | uniq | sort | reject: "" %}

        {%- assign max_strip = 24 -%}
        {%- for p in images limit:max_strip -%}
          <div class="strip-item">
            <img class="strip-img" src="{{ p | relative_url }}" alt="Gallery photo {{ forloop.index }}" loading="lazy"/>
          </div>
        {%- endfor -%}
        {%- comment -%} duplicate for seamless loop {%- endcomment -%}
        {%- for p in images limit:max_strip -%}
          <div class="strip-item">
            <img class="strip-img" src="{{ p | relative_url }}" alt="Gallery photo {{ forloop.index }}" loading="lazy"/>
          </div>
        {%- endfor -%}
      </div>
    </div>
  </div>
</section>

<section class="gal-wrap" id="photos">
  <h2 class="gal-heading">Photos</h2>
  <p class="gal-help">Click any photo to view full-size • Use ← → keys to navigate • Press Esc to close</p>

  <!-- ===== Masonry Photo Grid ===== -->
  {% if images.size > 0 %}
  <div class="gal-masonry" id="galMasonry">
    {%- for p in images -%}
      {% assign file = p | split:'/' | last %}
      {% assign base = file | split:'.' | first %}
      {% assign caption = base | replace:'-',' ' | replace:'_',' ' %}
      <figure class="gal-card" data-index="{{ forloop.index0 }}">
        <img class="gal-img"
             src="{{ p | relative_url }}"
             alt="{{ caption | capitalize }}"
             loading="lazy"
             width="1600" height="1200"/>
        <figcaption class="gal-cap-overlay">{{ caption | capitalize }}</figcaption>
        <figcaption class="gal-meta">
          <span class="gal-caption">{{ caption | capitalize }}</span>
          <a href="#" class="gal-zoom" data-index="{{ forloop.index0 }}">View</a>
        </figcaption>
      </figure>
    {%- endfor -%}
  </div>
  {% else %}
    <p style="text-align:center; margin: 32px 0;">
      <em>Add images to <code>assets/img/gallery/</code> to populate the gallery.</em>
    </p>
  {% endif %}
</section>

<!-- ===== Videos ===== -->
<section class="gal-wrap" id="videos" aria-labelledby="videos-heading">
  <h2 id="videos-heading" class="gal-heading">Videos</h2>
  <div class="v-grid">
    <!-- Video 1 -->
    <article class="v-card">
      <div class="v-embed">
        <iframe
          src="https://www.youtube-nocookie.com/embed/nGn7-rb_dU8"
          title="YouTube video"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          referrerpolicy="strict-origin-when-cross-origin"
          allowfullscreen></iframe>
      </div>
      <div class="v-cap">DevOps + AI • Highlight Reel</div>
    </article>
    <!-- Video 2 -->
    <article class="v-card">
      <div class="v-embed">
        <iframe
          src="https://www.youtube-nocookie.com/embed/qjpCqLSxo4A"
          title="YouTube video"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          referrerpolicy="strict-origin-when-cross-origin"
          allowfullscreen></iframe>
      </div>
      <div class="v-cap">Community Sessions • Best Moments</div>
    </article>
    <!-- Video 3 -->
    <article class="v-card">
      <div class="v-embed">
        <iframe
          src="https://www.youtube-nocookie.com/embed/6aC_nes9LIk"
          title="YouTube video"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          referrerpolicy="strict-origin-when-cross-origin"
          allowfullscreen></iframe>
      </div>
      <div class="v-cap">Hackathon Series • Toronto</div>
    </article>
    <!-- Video 4 -->
    <article class="v-card">
      <div class="v-embed">
        <iframe
          src="https://www.youtube-nocookie.com/embed/RMwWvp7wRkY"
          title="YouTube video"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          referrerpolicy="strict-origin-when-cross-origin"
          allowfullscreen></iframe>
      </div>
      <div class="v-cap">Meetups • Talks & Demos</div>
    </article>
  </div>
</section>

<!-- ===== Lightbox ===== -->
<div id="lightbox" aria-hidden="true" aria-label="Image viewer">
  <div class="lb-inner">
    <img id="lbImg" class="lb-img" alt="Expanded gallery image"/>
    <div id="lbCap" class="lb-caption"></div>
    <div class="lb-controls">
      <button type="button" class="lb-btn lb-prev" id="lbPrev" aria-label="Previous image">‹</button>
      <button type="button" class="lb-btn lb-next" id="lbNext" aria-label="Next image">›</button>
    </div>
    <button type="button" class="lb-close" id="lbClose" aria-label="Close viewer">✕</button>
  </div>
</div>

<script>
(function(){
  /* Smooth anchor scroll */
  document.querySelectorAll('.gal-nav a[href^="#"]').forEach(a=>{
    a.addEventListener('click', e=>{
      const id = a.getAttribute('href').slice(1);
      const el = document.getElementById(id);
      if(el){
        e.preventDefault();
        el.scrollIntoView({behavior:'smooth', block:'start'});
      }
    });
  });

  const container = document.getElementById('galMasonry');
  if(!container) return;

  const cards = Array.from(container.querySelectorAll('.gal-card'));
  const images = cards.map(card => {
    const img = card.querySelector('.gal-img');
    const cap = card.querySelector('.gal-caption');
    return { src: img.src, alt: img.alt || '', caption: cap ? cap.textContent.trim() : '' };
  });

  const lb = document.getElementById('lightbox');
  const lbImg = document.getElementById('lbImg');
  const lbCap = document.getElementById('lbCap');
  const prevBtn = document.getElementById('lbPrev');
  const nextBtn = document.getElementById('lbNext');
  const closeBtn = document.getElementById('lbClose');

  let idx = 0;

  function open(i){
    idx = (i + images.length) % images.length;
    const item = images[idx];
    lbImg.src = item.src;
    lbImg.alt = item.alt;
    lbCap.textContent = item.caption || '';
    lb.setAttribute('aria-hidden', 'false');
    document.documentElement.style.overflow = 'hidden';
  }
  function close(){
    lb.setAttribute('aria-hidden', 'true');
    document.documentElement.style.overflow = '';
    lbImg.src = '';
  }
  function next(){ open(idx + 1); }
  function prev(){ open(idx - 1); }

  // Open from image click or "View" button
  container.addEventListener('click', (e) => {
    const fig = e.target.closest('.gal-card');
    if(!fig) return;
    if(e.target.classList.contains('gal-img') || e.target.classList.contains('gal-zoom')){
      e.preventDefault();
      const i = parseInt(fig.dataset.index, 10) || 0;
      open(i);
    }
  });

  // Controls
  nextBtn.addEventListener('click', next);
  prevBtn.addEventListener('click', prev);
  closeBtn.addEventListener('click', close);
  lb.addEventListener('click', (e)=>{ if(e.target === lb) close(); });

  // Keyboard
  document.addEventListener('keydown', (e)=>{
    if(lb.getAttribute('aria-hidden') === 'true') return;
    if(e.key === 'Escape') close();
    else if(e.key === 'ArrowRight') next();
    else if(e.key === 'ArrowLeft') prev();
  });
})();
</script>
