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

/* ===== Hero ===== */
.gal-hero {
  width: 100vw; margin-left: calc(50% - 50vw); margin-right: calc(50% - 50vw);
  background: linear-gradient(135deg,#2f5597 0%,#2874c7 50%,#7fb0f0 100%);
  color:#fff; text-align:center; padding: 30px 16px;
}
.gal-hero h1 { margin:0; font-weight:800; font-size: clamp(24px,3.6vw,40px); }
.gal-nav { margin-top: 10px; display:flex; gap:10px; justify-content:center; flex-wrap:wrap; }
.gal-nav a{
  display:inline-block; padding:.45rem .8rem; border-radius:999px; text-decoration:none;
  background:#ffffff; color:#1f3c7a !important; font-weight:800; font-size:.9rem;
  border:1px solid rgba(255,255,255,.2);
}
.gal-nav a:hover{ background:#eef4ff; }

/* ===== Auto-scrolling photo strip (infinite loop) ===== */
.strip-wrap{
  width: 100vw; margin-left: calc(50% - 50vw); margin-right: calc(50% - 50vw);
  background: linear-gradient(180deg, #f7f9ff 0%, #eef4ff 100%);
  border-top: 1px solid rgba(0,0,0,.06);
  border-bottom: 1px solid rgba(0,0,0,.06);
  padding: clamp(8px, 1.6vw, 12px) 0;
}
.strip-inner{ max-width: 1200px; margin: 0 auto; padding: 0 clamp(12px,3vw,20px); }
.strip{
  position:relative; overflow:hidden;
}
.strip-track{
  display:flex; align-items:center;
  gap: clamp(14px, 2.5vw, 24px);
  will-change: transform;
  animation: strip-marquee 36s linear infinite;
}
.strip:hover .strip-track{ animation-play-state: paused; }
@keyframes strip-marquee{
  from{ transform: translateX(0); }
  to  { transform: translateX(-50%); }
}
.strip-item{
  flex: 0 0 auto;
  width: clamp(160px, 22vw, 240px);
  height: clamp(110px, 15vw, 160px);
  border-radius: 12px; overflow:hidden;
  background:#fff; border:1px solid rgba(0,0,0,.06);
  box-shadow: 0 8px 28px rgba(2,24,71,.06);
}
.strip-img{
  width:100%; height:100%; object-fit:cover; display:block;
}

/* ===== Main content area ===== */
.gal-wrap { padding: 18px clamp(12px, 3vw, 36px) 36px; }

/* ===== Masonry grid (Photos) ===== */
.gal-masonry{
  column-gap: 14px;
  column-count: 1;               /* default */
}
@media (min-width: 520px){ .gal-masonry{ column-count: 2; } }
@media (min-width: 880px){ .gal-masonry{ column-count: 3; } }
@media (min-width: 1200px){ .gal-masonry{ column-count: 4; } }

.gal-card{
  display: inline-block; width: 100%; margin: 0 0 14px; break-inside: avoid;
  background:#fff; border: 1px solid rgba(0,0,0,.06);
  border-radius: 12px; overflow: hidden;
  box-shadow: 0 10px 30px rgba(2,24,71,.06);
  transition: transform .15s ease, box-shadow .15s ease;
}
.gal-card:hover{ transform: translateY(-2px); box-shadow: 0 14px 36px rgba(2,24,71,.10); }
.gal-img{
  display:block; width:100%; height:auto;
  aspect-ratio: 4 / 3;
  object-fit: cover;
}
.gal-meta{
  padding: 10px 12px; font-size:.92rem; color:#334155;
  display:flex; align-items:center; justify-content:space-between; gap:8px;
}
.gal-caption{ overflow:hidden; text-overflow:ellipsis; white-space:nowrap; }
.gal-zoom{
  flex:0 0 auto; font-weight:800; font-size:.85rem;
  color:#2874c7; text-decoration:none; border:1px solid rgba(40,116,199,.25);
  padding: .25rem .5rem; border-radius: 999px;
}
.gal-zoom:hover{ background:#eef4ff; }

/* ===== Videos grid ===== */
.v-grid{
  display:grid; gap: 16px; margin-top: 22px;
  grid-template-columns: 1fr;
}
@media (min-width: 680px){ .v-grid{ grid-template-columns: 1fr 1fr; } }
@media (min-width: 1080px){ .v-grid{ grid-template-columns: 1fr 1fr 1fr; } }

.v-card{
  background:#fff; border: 1px solid rgba(0,0,0,.06);
  border-radius: 12px; overflow: hidden;
  box-shadow: 0 10px 30px rgba(2,24,71,.06);
}
.v-embed{
  position: relative; width: 100%; padding-bottom: 56.25%; /* 16:9 */
  background:#000;
}
.v-embed iframe{
  position: absolute; inset: 0; width: 100%; height: 100%;
  border: 0; border-radius: 0;
}
.v-cap{
  padding: 10px 12px; font-size: .92rem; color:#334155; font-weight: 600;
  white-space: nowrap; overflow: hidden; text-overflow: ellipsis;
}

/* ===== Lightbox (no libraries) ===== */
#lightbox{
  position: fixed; inset:0; display:none; z-index: 9999;
  background: rgba(5,10,25,.84);
}
#lightbox[aria-hidden="false"]{ display:block; }

.lb-inner{
  position:absolute; inset: 0; display:grid; place-items:center;
  padding: clamp(10px, 3vw, 28px);
}
.lb-img{
  max-width: 96vw; max-height: 82vh; border-radius: 12px;
  box-shadow: 0 20px 60px rgba(0,0,0,.45);
}
.lb-caption{
  margin-top: 10px; color:#e6eefc; text-align:center; font-size: .98rem;
  max-width: 92vw; overflow: hidden; text-overflow: ellipsis; white-space: nowrap;
}

/* Controls */
.lb-controls{
  position: absolute; inset: 0; pointer-events:none;
}
.lb-btn{
  position:absolute; top:50%; transform: translateY(-50%);
  pointer-events:auto; cursor:pointer;
  width: 42px; height: 42px; border-radius: 999px; border: 1px solid rgba(255,255,255,.35);
  background: rgba(255,255,255,.08); color:#fff; display:grid; place-items:center;
  font-size: 18px; font-weight: 900; user-select:none;
}
.lb-btn:hover{ background: rgba(255,255,255,.16); }
.lb-prev{ left: 14px; }
.lb-next{ right: 14px; }

.lb-close{
  position:absolute; top: 14px; right: 14px;
  width: 40px; height: 40px; border-radius: 999px; border: 1px solid rgba(255,255,255,.35);
  background: rgba(255,255,255,.08); color:#fff; display:grid; place-items:center;
  font-size: 20px; font-weight: 900; cursor: pointer; pointer-events:auto;
}
.lb-close:hover{ background: rgba(255,255,255,.16); }

/* Hide default pager on this page */
.pagination, .pagination--pager { display:none !important; }

/* Help note */
.gal-help{
  text-align:center; color:#475569; font-size:.9rem; margin: 10px 0 24px;
}
</style>

<!-- HERO -->
<section class="gal-hero" aria-labelledby="gallery-heading">
  <h1 id="gallery-heading">Gallery</h1>
  <div class="gal-nav">
    <a href="#photos">Jump to Photos</a>
    <a href="#videos">Jump to Videos</a>
  </div>
</section>

<!-- ===== AUTO-SCROLL STRIP ===== -->
<section class="strip-wrap" aria-label="Recent photos">
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
             width="1200" height="900"/>
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
  <h2 id="videos-heading" style="margin:0 0 8px; font-weight:800;">Videos</h2>
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
      <div class="v-cap">Video: nGn7-rb_dU8</div>
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
      <div class="v-cap">Video: qjpCqLSxo4A</div>
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
      <div class="v-cap">Video: 6aC_nes9LIk</div>
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
      <div class="v-cap">Video: RMwWvp7wRkY</div>
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

  // Click handlers (image or "View" button)
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
