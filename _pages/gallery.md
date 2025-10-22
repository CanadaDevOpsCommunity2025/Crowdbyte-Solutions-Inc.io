---
layout: single
permalink: /gallery/
title: ""
classes: "full-bleed"
sidebar: false

# ——— Settings you can tweak ———
albums_root: "/assets/img/gallery/"
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
.page.full-bleed .page__content { max-width: none !important; padding: 0 !important; }

/* Hide theme title to avoid duplicate H1 */
.page__title { display:none !important; }

/* ===== Blue header (hero) ===== */
.g-hero {
  width: 100vw; margin-left: calc(50% - 50vw); margin-right: calc(50% - 50vw);
  background: linear-gradient(135deg,#2f5597 0%,#2874c7 50%,#7fb0f0 100%);
  color:#fff; text-align:center; padding: 34px 16px 24px;
}
.g-hero h1 { margin:0; font-weight:900; font-size: clamp(24px,3.6vw,40px); }

/* ===== Centered content wrapper ===== */
.albums-stage{
  display:flex; align-items:flex-start; justify-content:center;
  padding: 24px clamp(12px,3vw,36px) 40px;
}
.albums-grid{
  width: 100%;
  max-width: 1280px;
  margin: 0 auto;
  display:grid; gap:20px;
  grid-template-columns: repeat(1, minmax(320px, 1fr));
}
@media (min-width: 800px){
  .albums-grid{ grid-template-columns: repeat(2, minmax(380px, 1fr)); }
}
@media (min-width: 1200px){
  .albums-grid{ grid-template-columns: repeat(3, minmax(420px, 1fr)); }
}

/* Album card */
.album-card{
  position:relative; overflow:hidden; border-radius:16px;
  background:#fff; border:1px solid rgba(0,0,0,.06);
  box-shadow: 0 12px 36px rgba(2,24,71,.07);
  cursor:pointer;
}
.album-cover{
  width:100%; aspect-ratio: 16/10; object-fit:cover; display:block;
  transition: transform .25s ease;
}
.album-card:hover .album-cover{ transform: scale(1.03); }

.album-meta{
  position:absolute; left:10px; bottom:10px; right:10px;
  display:flex; align-items:center; justify-content:space-between; gap:8px;
  background: linear-gradient(180deg, rgba(0,0,0,0) 0%,
                                      rgba(6,18,38,.50) 50%,
                                      rgba(6,18,38,.80) 100%);
  color:#eaf1ff; border-radius:12px; padding:12px 14px;
  backdrop-filter: blur(2px);
}
.album-name{
  font-weight:900; letter-spacing:.2px;
  font-size: clamp(16px, 2.2vw, 24px);
  line-height: 1.15;
  white-space: normal;
  text-shadow: 0 2px 10px rgba(0,0,0,.4);
}
.album-count{
  font-weight:800; opacity:.9;
  font-size: clamp(12px, 1.4vw, 14px);
}

/* ===== Viewer (overlay) — visibility controlled by JS + hashchange fallback ===== */
#viewer{
  position:fixed; inset:0; z-index:9999;
  background: rgba(6,12,24,.6); backdrop-filter: blur(6px);
  display: none; /* hidden by default */
}
.viewer-inner{
  position:absolute; inset:0; display:flex; flex-direction:column; gap:10px;
  padding: clamp(10px,3vw,22px);
}
.viewer-bar{
  position: relative; z-index: 5;
  display:flex; align-items:center; justify-content:space-between; gap:10px;
  color:#eaf1ff;
}
.viewer-title{ font-weight:900; font-size:clamp(16px,1.8vw,20px); }

/* ✕ Close button (anchor; works even if JS listener fails) */
.viewer-close{
  position: fixed; top: 16px; right: 16px;
  z-index: 2147483647;
  background: rgba(0,0,0,.65); color:#fff; border:1px solid rgba(255,255,255,.45);
  border-radius:999px; width:46px; height:46px; display:grid; place-items:center;
  text-decoration:none; font-weight:900; font-size:22px; line-height:1;
  cursor:pointer; pointer-events:auto;
}
.viewer-close:hover{ background: rgba(0,0,0,.8); }

/* Horizontal strip (normal visuals) */
.viewer-strip{
  position:relative; flex:1 1 auto; overflow-x:auto; overflow-y:hidden;
  scroll-snap-type: x mandatory; display:flex; gap:10px; padding: 6px 0;
}
.viewer-item{
  flex: 0 0 auto; scroll-snap-align: center;
  display:grid; place-items:center;
  background:#000; border-radius:14px; overflow:hidden;
  border:1px solid rgba(255,255,255,.15);
  width: min(72vw, 780px);
  height: min(62vh, 520px);
  box-shadow: 0 18px 50px rgba(0,0,0,.45);
}
@media (max-width: 640px){
  .viewer-item{ width: 92vw; height: 56vh; }
}
.viewer-item img, .viewer-item iframe{
  max-width: 100%; max-height: 100%;
  width: auto; height: auto;
  object-fit: contain; display:block; border:0; background:#000;
}

/* RIGHT-SIDE nav column (fixed; does NOT move with pictures) */
.viewer-nav-fixed{
  position: fixed;
  right: 16px; top: 50%; transform: translateY(-50%);
  display: flex; flex-direction: column; gap: 10px;
  z-index: 2147483000; /* under close button */
  pointer-events: none;
}
.nav-btn{
  pointer-events: auto;
  width:48px; height:48px; border-radius:999px;
  background: rgba(0,0,0,.55); color:#fff;
  border:1px solid rgba(255,255,255,.35); display:grid; place-items:center;
  cursor:pointer; font-size: 22px; line-height: 1;
  backdrop-filter: blur(2px);
}
.nav-btn:hover{ background: rgba(0,0,0,.7); }

/* Hide MM pager here */
.pagination, .pagination--pager { display:none !important; }
</style>

<!-- ===== BLUE HEADER ===== -->
<section class="g-hero" aria-labelledby="gallery-heading">
  <h1 id="gallery-heading">Gallery</h1>
</section>

<!-- ===== CENTERED ALBUMS ===== -->
<section id="gallery-home" class="albums-stage" aria-label="Gallery albums" tabindex="-1">
  <div id="albumsGrid" class="albums-grid"></div>
</section>

<!-- Hidden pool of media items generated by Liquid (images + videos) -->
<div id="mediaPool" style="display:none">
  {% assign root = page.albums_root | default: "/assets/img/gallery/" %}
  {% assign all = site.static_files | where_exp: "f", "f.path contains root" %}
  {% assign img_exts = ".png,.svg,.jpg,.jpeg,.webp,.gif,.PNG,.SVG,.JPG,.JPEG,.WEBP,.GIF" %}
  {% for f in all %}
    {% if img_exts contains f.extname %}
      {% assign rel = f.path | remove: root %}
      {% assign album = rel | split:'/' | first %}
      {% if album == rel %}{% assign album = "Photos" %}{% endif %}
      <a class="media" data-type="image" data-album="{{ album }}" href="{{ f.path | relative_url | uri_escape }}"></a>
    {% endif %}
  {% endfor %}

  {% if page.youtube_ids and page.youtube_ids.size > 0 %}
    {% assign vname = page.videos_album_name | default: "Videos" %}
    {% for vid in page.youtube_ids %}
      <a class="media" data-type="video" data-album="{{ vname }}" href="https://www.youtube-nocookie.com/embed/{{ vid }}"></a>
    {% endfor %}
  {% endif %}
</div>

<!-- Viewer Modal -->
<div id="viewer" aria-label="Album viewer">
  <div class="viewer-inner">
    <div class="viewer-bar">
      <div class="viewer-title" id="viewerTitle">Album</div>
      <!-- IMPORTANT: real anchor (works without JS); JS also listens for hashchange -->
      <a id="viewerClose" class="viewer-close" href="#gallery-home" aria-label="Close viewer and return to Gallery">✕</a>
    </div>

    <div class="viewer-strip" id="viewerStrip" tabindex="0" aria-label="Scroll left or right to browse">
      <!-- items injected by JS -->
    </div>
  </div>
  <!
