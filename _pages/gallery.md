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
/* Full-bleed container reset */
.page.full-bleed .page__inner-wrap,
.page.full-bleed .page__content { max-width:none !important; padding:0 !important; }

/* Hide theme title to avoid duplicate H1 */
.page__title { display:none !important; }

/* ===== Blue header ===== */
.g-hero{
  width:100vw; margin-left:calc(50% - 50vw); margin-right:calc(50% - 50vw);
  background:linear-gradient(135deg,#2f5597 0%,#2874c7 50%,#7fb0f0 100%);
  color:#fff; text-align:center; padding:34px 16px 24px;
}
.g-hero h1{ margin:0; font-weight:900; font-size:clamp(24px,3.6vw,40px); }

/* ===== Albums grid ===== */
.albums-stage{ display:flex; justify-content:center; padding:24px clamp(12px,3vw,36px) 40px; }
.albums-grid{
  width:100%; max-width:1280px; margin:0 auto;
  display:grid; gap:20px; grid-template-columns:repeat(1, minmax(320px, 1fr));
}
@media (min-width:800px){ .albums-grid{ grid-template-columns:repeat(2, minmax(380px,1fr)); } }
@media (min-width:1200px){ .albums-grid{ grid-template-columns:repeat(3, minmax(420px,1fr)); } }

/* Helpful notice */
.notice{
  max-width:980px; margin:12px auto 0; padding:10px 14px; border-radius:12px;
  background:#fff3cd; color:#7a5a00; border:1px solid #ffe69c; font-size:.95rem;
}

/* Album cards */
.album-card{
  position:relative; overflow:hidden; border-radius:16px;
  background:#fff; border:1px solid rgba(0,0,0,.06);
  box-shadow:0 12px 36px rgba(2,24,71,.07); cursor:pointer; text-decoration:none;
}
.album-cover{ width:100%; aspect-ratio:16/10; object-fit:cover; display:block; transition:transform .25s; }
.album-card:hover .album-cover{ transform:scale(1.03); }
.album-meta{
  position:absolute; left:10px; right:10px; bottom:10px;
  display:flex; align-items:center; justify-content:space-between; gap:8px;
  background:linear-gradient(180deg,rgba(0,0,0,0) 0%, rgba(6,18,38,.50) 50%, rgba(6,18,38,.80) 100%);
  color:#eaf1ff; border-radius:12px; padding:12px 14px; backdrop-filter:blur(2px);
}
.album-name{ font-weight:900; font-size:clamp(16px,2.2vw,24px); text-shadow:0 2px 10px rgba(0,0,0,.4); }
.album-count{ font-weight:800; font-size:clamp(12px,1.4vw,14px); opacity:.9; }

/* ===== Viewer (overlay) — CSS :target controls visibility but JS can force it too ===== */
#viewer{
  position:fixed; inset:0; z-index:9999;
  background:rgba(6,12,24,.6); backdrop-filter:blur(6px);
  display:none; /* hidden by default */
}
#viewer:target,
#viewer.open { display:block; }  /* JS 'open' class as a backup */

.viewer-inner{ position:absolute; inset:0; display:flex; flex-direction:column; gap:10px; padding:clamp(10px,3vw,22px); }
.viewer-bar{ display:flex; align-items:center; justify-content:space-between; color:#eaf1ff; }
.viewer-title{ font-weight:900; font-size:clamp(16px,1.8vw,20px); }

/* ✕ close (REAL LINK) */
.viewer-close{
  position:fixed; top:16px; right:16px;
  z-index:2147483647; width:46px; height:46px; border-radius:999px;
  background:rgba(0,0,0,.65); color:#fff; border:1px solid rgba(255,255,255,.45);
  display:grid; place-items:center; text-decoration:none; font-weight:900; font-size:22px; line-height:1; cursor:pointer;
}
.viewer-close:hover{ background:rgba(0,0,0,.8); }

/* Horizontal filmstrip */
.viewer-strip{
  position:relative; flex:1 1 auto; overflow-x:auto; overflow-y:hidden;
  scroll-snap-type:x mandatory; display:flex; gap:10px; padding:6px 0;
}
.viewer-item{
  flex:0 0 auto; scroll-snap-align:center; display:grid; place-items:center;
  background:#000; border-radius:14px; overflow:hidden; border:1px solid rgba(255,255,255,.15);
  width:min(72vw,780px); height:min(62vh,520px); box-shadow:0 18px 50px rgba(0,0,0,.45);
}
@media (max-width:640px){ .viewer-item{ width:92vw; height:56vh; } }
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

/* Hide theme pager */
.pagination, .pagination--pager{ display:none !important; }
</style>

<!-- ===== Header ===== -->
<section class="g-hero" aria-labelledby="gallery-heading">
  <h1 id="gallery-heading">Gallery</h1>
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
<div class="notice">
  <strong>No images detected</strong> in <code>{{ page.album_path }}</code> at build time.<br>
  Confirm the path and case exactly. Example: <code>assets/img/gallery/DevOps for Gen AI Ottawa/photo1.jpg</code><br>
  If using Git LFS, re-add images as normal Git files (Pages doesn’t fetch LFS objects).
</div>
{% endif %}

<!-- ===== Albums grid (server-rendered) ===== -->
<section id="gallery-home" class="albums-stage" aria-label="Gallery albums" tabindex="-1">
  <div class="albums-grid">
    {% if img_list.size > 0 %}
      {% assign cover = img_list[0] %}
      <a href="#viewer" class="album-card" id="photosCard"
         data-album="{{ page.album_name }}" data-kind="photos">
        <img class="album-cover" src="{{ cover | uri_escape | relative_url }}" alt="{{ page.album_name }}">
        <div class="album-meta">
          <span class="album-name">{{ page.album_name }}</span>
          <span class="album-count">{{ img_list.size }}</span>
        </div>
      </a>
    {% endif %}

    {% if page.youtube_ids and page.youtube_ids.size > 0 %}
      <a href="#viewer" class="album-card" id="videosCard"
         data-album="{{ page.videos_album_name }}" data-kind="videos">
        <img class="album-cover" src="https://img.youtube.com/vi/{{ page.youtube_ids[0] }}/hqdefault.jpg" alt="{{ page.videos_album_name }}">
        <div class="album-meta">
          <span class="album-name">{{ page.videos_album_name }}</span>
          <span class="album-count">{{ page.youtube_ids | size }}</span>
        </div>
      </a>
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

<!-- ===== Viewer ===== -->
<div id="viewer" aria-label="Album viewer">
  <div class="viewer-inner">
    <div class="viewer-bar">
      <div class="viewer-title" id="viewerTitle">Album</div>
      <!-- REAL link to #gallery-home -->
      <a id="viewerClose" class="viewer-close" href="#gallery-home" aria-label="Close viewer and return to Gallery">✕</a>
    </div>
    <div class="viewer-strip" id="viewerStrip" tabindex="0" aria-label="Scroll left or right to browse"></div>
  </div>
  <div class="viewer-nav-fixed" aria-hidden="false">
    <button class="nav-btn" id="navPrev" aria-label="Previous">‹</button>
    <button class="nav-btn" id="navNext" aria-label="Next">›</button>
  </div>
</div>

<script>
(function(){
  var photosCard = document.getElementById('photosCard');
  var videosCard = document.getElementById('videosCard');

  var poolPhotos = document.getElementById('poolPhotos');
  var poolVideos = document.getElementById('poolVideos');

  var viewer = document.getElementById('viewer');
  var viewerTitle = document.getElementById('viewerTitle');
  var viewerStrip = document.getElementById('viewerStrip');
  var btnPrev = document.getElementById('navPrev');
  var btnNext = document.getElementById('navNext');

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
    viewerTitle.textContent = name;
    viewerStrip.innerHTML = '';
    items.forEach(function(it){ viewerStrip.appendChild(itemEl(it)); });

    // Snap to first item
    setTimeout(function(){
      var first = viewerStrip.querySelector('.viewer-item');
      if (first) first.scrollIntoView({behavior:'instant', inline:'center', block:'nearest'});
    }, 0);
  }

  // Force open: build content, add .open class, and set hash
  function forceOpenViewer(name, items){
    buildViewer(name, items);
    viewer.classList.add('open');          // show even if hash doesn’t change
    if (location.hash !== '#viewer') {
      location.hash = '#viewer';           // trigger :target path
    }
  }

  // Click handlers — robust open
  if (photosCard){
    photosCard.addEventListener('click', function(e){
      e.preventDefault();
      forceOpenViewer('{{ page.album_name | escape }}', photos);
    });
  }
  if (videosCard){
    videosCard.addEventListener('click', function(e){
      e.preventDefault();
      forceOpenViewer('{{ page.videos_album_name | escape }}', videos);
    });
  }

  // If page loads directly at #viewer (or Back to it), ensure there’s content
  function ensureViewerHasContent(){
    if (location.hash !== '#viewer') {
      viewer.classList.remove('open');
      return;
    }
    if (viewerStrip.children.length > 0) return;
    // Prefer photos if present; otherwise videos
    if (photos.length){ buildViewer('{{ page.album_name | escape }}', photos); viewer.classList.add('open'); return; }
    if (videos.length){ buildViewer('{{ page.videos_album_name | escape }}', videos); viewer.classList.add('open'); return; }
  }
  ensureViewerHasContent();
  window.addEventListener('hashchange', ensureViewerHasContent);

  // Right-side arrows
  var currentIndex = 0;
  function goTo(n){
    var items = viewerStrip.querySelectorAll('.viewer-item');
    if (!items.length) return;
    var L = items.length; currentIndex = (n + L) % L;
    items[currentIndex].scrollIntoView({behavior:'smooth', inline:'center', block:'nearest'});
  }
  function next(){ goTo(currentIndex + 1); }
  function prev(){ goTo(currentIndex - 1); }
  btnNext.addEventListener('click', function(e){ e.preventDefault(); e.stopPropagation(); next(); });
  btnPrev.addEventListener('click', function(e){ e.preventDefault(); e.stopPropagation(); prev(); });

  // Keep index in sync as user scrolls
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

  // Stop videos when leaving #viewer and also remove .open
  window.addEventListener('hashchange', function(){
    if (location.hash !== '#viewer') {
      viewer.classList.remove('open');
      Array.prototype.forEach.call(viewerStrip.querySelectorAll('iframe'), function(f){ f.src = f.src; });
    }
  });
})();
</script>
