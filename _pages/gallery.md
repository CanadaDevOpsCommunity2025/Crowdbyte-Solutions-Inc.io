---
layout: single
permalink: /gallery/
title: ""
classes: "full-bleed"
sidebar: false

# --- SETTINGS ---
album_name: "DevOps for Gen AI Ottawa"
album_path: "/assets/img/gallery/DevOps for Gen AI Ottawa/"   # exact path, case-sensitive
videos_album_name: "Videos"
youtube_ids:
  - nGn7-rb_dU8
  - qjpCqLSxo4A
  - 6aC_nes9LIk
  - RMwWvp7wRkY
---

<style>
/* ===== Utilities & Accessibility ===== */
:root{
  --bg1:#0b1c33;
  --bg2:#1a3a67;
  --bg3:#7fb0f0;
  --card:#ffffff;
  --ink:#0c1a2b;
  --ink-soft:#45607e;
  --brand:#2f66c7;
  --ring:#7fb0f0;
}
@media (prefers-color-scheme: dark) {
  :root{
    --card:#0f1726;
    --ink:#eaf1ff;
    --ink-soft:#a2b7d1;
    --brand:#7fb0f0;
  }
}
:focus-visible{ outline:3px solid var(--ring); outline-offset:3px; }
.sr-only{ position:absolute;width:1px;height:1px;padding:0;margin:-1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;border:0; }
[hidden]{ display:none !important; }

/* Motion-respectful */
@media (prefers-reduced-motion: reduce) {
  *{ animation-duration:0.01ms !important; animation-iteration-count:1 !important; transition-duration:0.01ms !important; scroll-behavior:auto !important; }
}

/* ===== Full-bleed reset ===== */
.page.full-bleed .page__inner-wrap,
.page.full-bleed .page__content { max-width:none !important; padding:0 !important; }
.page__title { display:none !important; }

/* ===== Hero ===== */
.g-hero{
  width:100vw; margin-left:calc(50% - 50vw); margin-right:calc(50% - 50vw);
  background:radial-gradient(1200px 600px at 20% -10%, rgba(127,176,240,.35), transparent 60%),
             linear-gradient(135deg, var(--bg1) 0%, var(--bg2) 55%, #244a81 100%);
  color:#fff; text-align:center; padding:48px 16px 28px; position:relative; overflow:hidden;
}
.g-hero h1{ margin:0; font-weight:900; letter-spacing:.2px; font-size:clamp(26px,3.8vw,44px); }
.g-hero p{ margin:10px auto 0; max-width:900px; opacity:.95; font-size:clamp(14px,1.6vw,18px); }

/* ===== Albums grid ===== */
.albums-stage{ display:flex; justify-content:center; padding:28px clamp(14px,3vw,42px) 48px; background:linear-gradient(180deg,rgba(255,255,255,.0),rgba(255,255,255,.0));}
.albums-grid{
  width:100%; max-width:1200px; margin:0 auto;
  display:grid; gap:22px; grid-template-columns:repeat(1, minmax(300px, 1fr));
}
@media (min-width:860px){ .albums-grid{ grid-template-columns:repeat(2, minmax(360px,1fr)); } }
@media (min-width:1200px){ .albums-grid{ grid-template-columns:repeat(3, minmax(360px,1fr)); } }

/* Album card (button) */
.album-card{
  -webkit-appearance:none; appearance:none; border:0; background:none; padding:0; margin:0;
  position:relative; overflow:hidden; border-radius:18px; width:100%; text-align:left;
  background:var(--card); border:1px solid rgba(0,0,0,.06);
  box-shadow:0 14px 40px rgba(12,26,43,.10);
  cursor:pointer; display:block; transform:translateZ(0);
}
.album-cover{
  width:100%; aspect-ratio:16/10; object-fit:cover; display:block;
  transition:transform .35s ease;
}
.album-card:hover .album-cover{ transform:scale(1.03); }
.album-meta{
  position:absolute; left:12px; right:12px; bottom:12px;
  display:flex; align-items:center; justify-content:space-between; gap:10px;
  background:linear-gradient(180deg,rgba(0,0,0,0) 0%, rgba(6,18,38,.55) 60%, rgba(6,18,38,.85) 100%);
  color:#eaf1ff; border-radius:12px; padding:12px 14px; backdrop-filter:blur(2px);
}
.album-name{ font-weight:900; font-size:clamp(16px,2.2vw,22px); text-shadow:0 2px 10px rgba(0,0,0,.4); }
.album-count{ font-weight:800; font-size:clamp(12px,1.6vw,14px); opacity:.92; }

/* Card footer with CTA */
.card-footer{
  display:flex; align-items:center; justify-content:space-between; gap:10px;
  padding:12px 14px 14px; color:var(--ink-soft);
  font-size:14px;
}
.badge{
  display:inline-flex; align-items:center; gap:8px; font-weight:700;
  background:rgba(47,102,199,.08); color:#2f66c7; border:1px solid rgba(47,102,199,.25);
  padding:6px 10px; border-radius:999px; line-height:1;
}
.btn{
  -webkit-appearance:none; appearance:none; border:0; cursor:pointer;
  display:inline-flex; align-items:center; gap:8px; border-radius:10px;
  padding:10px 14px; font-weight:800; text-decoration:none;
  background:linear-gradient(180deg,#eaf1ff, #d5e5ff); color:#123;
  border:1px solid rgba(47,102,199,.25); box-shadow:0 6px 16px rgba(18,38,66,.15);
}
.btn:hover{ filter:brightness(.98); }
.btn:active{ transform:translateY(1px); }

/* ===== Helper notice ===== */
.notice{
  max-width:980px; margin:12px auto 0; padding:10px 14px; border-radius:12px;
  background:#fff3cd; color:#7a5a00; border:1px solid #ffe69c; font-size:.95rem;
}

/* ===== Viewer (dialog) — JS `.open` ONLY ===== */
#viewer{
  position:fixed; inset:0; z-index:9999;
  background:rgba(6,12,24,.6); backdrop-filter:blur(6px);
  display:none !important;
}
#viewer.open { display:block !important; }
html.viewer-lock{ overflow:hidden !important; }

.viewer-inner{ position:absolute; inset:0; display:flex; flex-direction:column; gap:12px; padding:clamp(12px,3vw,22px); }
.viewer-bar{ display:flex; align-items:center; justify-content:space-between; color:#eaf1ff; }
.viewer-title{ font-weight:900; font-size:clamp(16px,1.8vw,20px); margin:0; }

.viewer-hint{ font-size:12px; opacity:.85; margin-top:4px; }

/* Close button with label */
.viewer-close{
  position:fixed; top:16px; right:16px;
  z-index:2147483647; min-width:60px; height:46px; border-radius:999px;
  background:rgba(0,0,0,.78); color:#fff; border:1px solid rgba(255,255,255,.35);
  display:inline-flex; align-items:center; gap:10px; padding:0 14px; font-weight:800; cursor:pointer;
}
.viewer-close:hover{ background:rgba(0,0,0,.9); }
.viewer-close .x{ font-size:22px; line-height:1; }

/* Filmstrip */
.viewer-strip{
  position:relative; flex:1 1 auto; overflow-x:auto; overflow-y:hidden;
  scroll-snap-type:x mandatory; display:flex; gap:12px; padding:6px 0;
}
.viewer-item{
  flex:0 0 auto; scroll-snap-align:center; display:grid; place-items:center;
  background:#000; border-radius:14px; overflow:hidden; border:1px solid rgba(255,255,255,.15);
  width:min(76vw,920px); height:min(66vh,620px); box-shadow:0 18px 50px rgba(0,0,0,.45);
}
@media (max-width:640px){ .viewer-item{ width:92vw; height:58vh; } }
.viewer-item img, .viewer-item iframe{ max-width:100%; max-height:100%; width:auto; height:auto; object-fit:contain; display:block; border:0; background:#000; }

/* Fixed right-side arrows */
.viewer-nav-fixed{
  position:fixed; right:16px; top:50%; transform:translateY(-50%);
  display:flex; flex-direction:column; gap:10px; z-index:2147483000; pointer-events:none;
}
.nav-btn{
  pointer-events:auto; width:48px; height:48px; border-radius:999px;
  background:rgba(0,0,0,.55); color:#fff; border:1px solid rgba(255,255,255,.35);
  display:grid; place-items:center; cursor:pointer; font-size:22px; line-height:1; backdrop-filter:blur(2px);
}
.nav-btn:hover{ background:rgba(0,0,0,.7); }

/* Skeleton shimmer for covers (progressive feeling) */
.skel{
  position:relative; overflow:hidden; background:linear-gradient(90deg,#e9eef5 0%,#f4f7fb 40%,#e9eef5 80%); 
}
.skel::after{
  content:""; position:absolute; inset:0; transform:translateX(-100%);
  background:linear-gradient(90deg, rgba(255,255,255,0) 0%, rgba(255,255,255,.6) 50%, rgba(255,255,255,0) 100%);
  animation:sh 1.35s infinite;
}
@keyframes sh{ 100%{ transform:translateX(100%); } }
</style>

<!-- ===== Hero ===== -->
<section class="g-hero" aria-labelledby="gallery-heading">
  <h1 id="gallery-heading">Gallery</h1>
  <p>Highlights from our community—photos and session videos. Click an album to browse. Press <strong>Esc</strong> to close the viewer; use <strong>← / →</strong> to navigate.</p>
</section>

{% comment %}
  Gather images from the EXACT album path (with spaces).
{% endcomment %}
{% assign img_exts = ".png,.svg,.jpg,.jpeg,.webp,.gif,.PNG,.SVG,.JPG,.JPEG,.WEBP,.GIF" %}
{% assign album_files = site.static_files | where_exp: "f", "f.path contains page.album_path" %}
{% assign images = "" %}
{% for f in album_files %}
  {% if img_exts contains f.extname %}
    {% assign images = images | append: f.path | append: "||" %}
  {% endif %}
{% endfor %}
{% assign img_list = images | split: "||" | reject: "" %}

{% if img_list.size == 0 %}
<div class="notice" role="status" aria-live="polite">
  <strong>No images detected</strong> in <code>{{ page.album_path }}</code> at build time.<br>
  Confirm the path and case exactly. Example: <code>assets/img/gallery/DevOps for Gen AI Ottawa/photo1.jpg</code><br>
  If using Git LFS, re-add images as normal Git files (Pages doesn’t fetch LFS objects).
</div>
{% endif %}

<!-- ===== Albums grid ===== -->
<section id="gallery-home" class="albums-stage" aria-label="Gallery albums" tabindex="-1">
  <div class="albums-grid">
    {% if img_list.size > 0 %}
      {% assign cover = img_list[0] %}
      <button type="button" class="album-card" id="photosCard"
         data-album="{{ page.album_name }}" data-kind="photos"
         aria-label="Open album {{ page.album_name }} ({{ img_list.size }} photos)">
        <img class="album-cover skel" src="{{ cover | uri_escape | relative_url }}" alt="" loading="lazy" onload="this.classList.remove('skel')">
        <div class="album-meta" aria-hidden="true">
          <span class="album-name">{{ page.album_name }}</span>
          <span class="album-count">{{ img_list.size }} photos</span>
        </div>
        <div class="card-footer">
          <span class="badge">📸 Photos</span>
          <span class="btn">Open Photos</span>
        </div>
      </button>
    {% endif %}

    {% if page.youtube_ids and page.youtube_ids.size > 0 %}
      <button type="button" class="album-card" id="videosCard"
         data-album="{{ page.videos_album_name }}" data-kind="videos"
         aria-label="Open album {{ page.videos_album_name }} ({{ page.youtube_ids | size }} videos)">
        <img class="album-cover skel" src="https://img.youtube.com/vi/{{ page.youtube_ids[0] }}/hqdefault.jpg" alt="" loading="lazy" onload="this.classList.remove('skel')">
        <div class="album-meta" aria-hidden="true">
          <span class="album-name">{{ page.videos_album_name }}</span>
          <span class="album-count">{{ page.youtube_ids | size }} videos</span>
        </div>
        <div class="card-footer">
          <span class="badge">🎬 Videos</span>
          <span class="btn">Open Videos</span>
        </div>
      </button>
    {% endif %}
  </div>
</section>

<!-- ===== Hidden pools (for building viewer) ===== -->
<div id="poolPhotos" style="display:none">
  {% for p in img_list %}
    <a class="media" data-type="image" data-album="{{ page.album_name }}" href="{{ p | uri_escape | relative_url }}"></a>
  {% endfor %}
</div>

<div id="poolVideos" style="display:none">
  {% if page.youtube_ids and page.youtube_ids.size > 0 %}
    {% for vid in page.youtube_ids %}
      <a class="media" data-type="video" data-album="{{ page.videos_album_name }}" href="https://www.youtube-nocookie.com/embed/{{ vid }}"></a>
    {% endfor %}
  {% endif %}
</div>

<!-- ===== Viewer / Dialog ===== -->
<div id="viewer" role="dialog" aria-modal="true" aria-labelledby="viewerHeading" aria-hidden="true">
  <div class="viewer-inner">
    <div class="viewer-bar">
      <div>
        <h2 id="viewerHeading" class="viewer-title">Album</h2>
        <div class="viewer-hint" aria-hidden="true">Tip: Use ← / → to navigate, Esc to close</div>
      </div>
      <button id="viewerClose" class="viewer-close" type="button">
        <span class="x" aria-hidden="true">×</span>
        <span>Close</span>
      </button>
    </div>
    <div class="viewer-strip" id="viewerStrip" tabindex="0" aria-label="Scroll left or right to browse"></div>
  </div>
  <div class="viewer-nav-fixed" aria-hidden="false">
    <button class="nav-btn" id="navPrev" aria-label="Previous item">‹</button>
    <button class="nav-btn" id="navNext" aria-label="Next item">›</button>
  </div>
</div>

<script>
(function(){
  var photosCard = document.getElementById('photosCard');
  var videosCard = document.getElementById('videosCard');

  var poolPhotos = document.getElementById('poolPhotos');
  var poolVideos = document.getElementById('poolVideos');

  var viewer = document.getElementById('viewer');
  var viewerHeading = document.getElementById('viewerHeading');
  var viewerStrip = document.getElementById('viewerStrip');
  var btnPrev = document.getElementById('navPrev');
  var btnNext = document.getElementById('navNext');
  var btnClose = document.getElementById('viewerClose');

  var lastTrigger = null; // restore focus on close
  var currentIndex = 0;

  function collectPool(pool){
    if (!pool) return [];
    var links = Array.prototype.slice.call(pool.querySelectorAll('.media'));
    return links.map(function(a){
      return { type:a.getAttribute('data-type'), album:a.getAttribute('data-album'), href:a.getAttribute('href') };
    });
  }

  var photos = collectPool(poolPhotos);
  var videos = collectPool(poolVideos);

  function itemEl(item){
    var wrap = document.createElement('div');
    wrap.className = 'viewer-item';
    if (item.type === 'image') {
      var img = document.createElement('img');
      img.loading = 'lazy';
      img.src = item.href; img.alt = '';
      wrap.appendChild(img);
    } else {
      var ifr = document.createElement('iframe');
      ifr.src = item.href;
      ifr.allow = "accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share";
      ifr.referrerPolicy = "strict-origin-when-cross-origin";
      ifr.allowFullscreen = true;
      wrap.appendChild(ifr);
    }
    return wrap;
  }

  function buildViewer(name, items){
    if (!items || !items.length) return;
    viewerHeading.textContent = name;
    viewerStrip.innerHTML = '';
    items.forEach(function(it){ viewerStrip.appendChild(itemEl(it)); });
    setTimeout(function(){
      var first = viewerStrip.querySelector('.viewer-item');
      if (first) first.scrollIntoView({behavior:'instant', inline:'center', block:'nearest'});
      currentIndex = 0;
    }, 0);
  }

  function openViewer(name, items, trigger){
    lastTrigger = trigger || null;
    buildViewer(name, items);
    document.documentElement.classList.add('viewer-lock');
    viewer.classList.add('open');
    viewer.setAttribute('aria-hidden','false');
    btnClose && btnClose.focus({preventScroll:true});
  }

  function closeViewer(){
    viewer.classList.remove('open');
    viewer.setAttribute('aria-hidden','true');
    document.documentElement.classList.remove('viewer-lock');
    // Stop videos
    Array.prototype.forEach.call(viewerStrip.querySelectorAll('iframe'), function(f){ f.src = f.src; });
    // Inline failsafe
    viewer.style.display = 'none';
    setTimeout(function(){ viewer.style.display = ''; }, 0);
    // Restore focus
    if (lastTrigger && typeof lastTrigger.focus === 'function') lastTrigger.focus({preventScroll:true});
    else {
      var grid = document.getElementById('gallery-home');
      if (grid) grid.focus({preventScroll:true});
    }
  }

  // Navigation
  function goTo(n){
    var items = viewerStrip.querySelectorAll('.viewer-item');
    if (!items.length) return;
    var L = items.length; currentIndex = (n + L) % L;
    items[currentIndex].scrollIntoView({behavior:'smooth', inline:'center', block:'nearest'});
  }
  function next(){ goTo(currentIndex + 1); }
  function prev(){ goTo(currentIndex - 1); }

  // Focus trap
  function getFocusable(container){
    return Array.prototype.slice.call(container.querySelectorAll(
      'a[href], button:not([disabled]), textarea, input, select, [tabindex]:not([tabindex="-1"])'
    ));
  }
  function trapFocus(e){
    if (!viewer.classList.contains('open')) return;
    if (e.key !== 'Tab') return;
    var focusables = getFocusable(viewer).filter(function(el){ return el.offsetParent !== null; });
    if (!focusables.length) return;
    var first = focusables[0], last = focusables[focusables.length - 1];
    if (e.shiftKey && document.activeElement === first){ e.preventDefault(); last.focus(); }
    else if (!e.shiftKey && document.activeElement === last){ e.preventDefault(); first.focus(); }
  }

  // Wire up albums
  if (photosCard){
    photosCard.addEventListener('click', function(e){
      openViewer('{{ page.album_name | escape }}', photos, e.currentTarget);
    });
  }
  if (videosCard){
    videosCard.addEventListener('click', function(e){
      openViewer('{{ page.videos_album_name | escape }}', videos, e.currentTarget);
    });
  }

  // Close handlers
  if (btnClose){
    ['click','touchend'].forEach(function(evt){
      btnClose.addEventListener(evt, function(e){ e.preventDefault(); e.stopPropagation(); closeViewer(); }, {passive:false});
    });
  }
  viewer.addEventListener('click', function(e){ if (e.target === viewer) closeViewer(); });
  document.addEventListener('keydown', function(e){
    if (!viewer.classList.contains('open')) return;
    if (e.key === 'Escape') { e.preventDefault(); closeViewer(); }
    if (e.key === 'ArrowRight') { e.preventDefault(); next(); }
    if (e.key === 'ArrowLeft') { e.preventDefault(); prev(); }
  });
  document.addEventListener('keydown', trapFocus);

  // Right-side arrows
  btnNext.addEventListener('click', function(e){ e.preventDefault(); e.stopPropagation(); next(); });
  btnPrev.addEventListener('click', function(e){ e.preventDefault(); e.stopPropagation(); prev(); });

  // Sync index as user scrolls
  viewerStrip.addEventListener('scroll', function(){
    var items = viewerStrip.querySelectorAll('.viewer-item');
    if (!items.length) return;
    var contLeft = viewerStrip.getBoundingClientRect().left;
    var best=0, dist=Infinity;
    Array.prototype.forEach.call(items, function(el, i){
      var d = Math.abs(el.getBoundingClientRect().left - contLeft);
      if (d < dist){ dist = d; best = i; }
    });
    currentIndex = best;
  }, {passive:true});

  // Normalize any legacy #viewer hash (old bookmarks)
  if (location.hash === '#viewer'){
    try{
      if (history.replaceState){
        history.replaceState(null, '', location.pathname + location.search + '#gallery-home');
      } else {
        location.hash = 'gallery-home';
      }
    }catch(e){}
  }
})();
</script>
