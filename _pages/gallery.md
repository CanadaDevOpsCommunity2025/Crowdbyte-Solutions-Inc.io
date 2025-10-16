---
layout: single
permalink: /gallery/
title: "Gallery"
sidebar: false
classes: "full-bleed"
---

<style>
/* Hide built-in page title / pager; keep only the blue hero */
.page__title, .pagination, .pagination--pager { display:none !important; }

/* Full-bleed helpers */
.page.full-bleed .page__inner-wrap,
.page.full-bleed .page__content {
  max-width: none !important;
  padding-left: 0 !important;
  padding-right: 0 !important;
}
.full-bleed-row { width:100vw; margin-left:calc(50% - 50vw); margin-right:calc(50% - 50vw); }

/* Blue hero */
.g-hero { background:#2f5597; color:#fff; padding: clamp(28px,5vw,56px) 24px; text-align:center; }
.g-hero h1 { margin:0; font-weight:800; font-size: clamp(28px,4.6vw,56px); }

/* Body */
.g-wrap { padding: 18px clamp(14px,3vw,40px); }

/* ===== Folder cards (square buttons) ===== */
.folder-grid{
  display:grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: clamp(12px, 2vw, 20px);
}
.folder-card{
  display:flex; align-items:center; justify-content:center; text-align:center;
  aspect-ratio: 1/1; border-radius: 16px; background:#f7f9fc;
  border:1px solid #e6ecf8; box-shadow:0 8px 24px rgba(2,24,71,.06);
  padding: 18px; text-decoration:none; position:relative; overflow:hidden;
  transition: transform .08s ease, box-shadow .2s ease, border-color .2s ease;
}
.folder-card:hover{ transform: translateY(-2px); border-color:#d7e3ff; box-shadow:0 12px 30px rgba(2,24,71,.09); }
.folder-name{
  color:#1f2a44; font-weight:800; font-size:clamp(1rem, 1.8vw, 1.1rem); line-height:1.25;
}
.folder-card .badge{
  position:absolute; top:10px; right:10px; background:#2f5597; color:#fff;
  font-weight:700; font-size:.78rem; border-radius:999px; padding:.25rem .5rem;
}

/* Subtle folder glyph */
.folder-glyph{
  position:absolute; left:-16px; bottom:-18px; width:120px; height:90px; opacity:.08;
  background: linear-gradient(180deg,#ffd36c,#ffb942);
  border-radius:10px 10px 8px 8px;
}
.folder-glyph:before{
  content:""; position:absolute; left:10px; top:-18px; width:48px; height:16px;
  background: linear-gradient(180deg,#ffe199,#ffd36c); border-radius:6px 6px 0 0;
}

/* ===== Single-album view ===== */
.album-actions{
  display:flex; justify-content:space-between; align-items:center; gap:12px; margin-bottom:12px;
}
.back-link{
  display:inline-block; padding:.45rem .7rem; border:1px solid #d7e3ff; border-radius:8px;
  color:#2f5597; font-weight:700; text-decoration:none; background:#fff;
}
.back-link:hover{ background:#f5f8ff; border-color:#2f5597; }

/* Images grid (no captions) */
.g-grid{
  display:grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: clamp(8px, 1.6vw, 16px); align-items:start;
}
.g-item{ margin:0; padding:0; border-radius:12px; overflow:hidden; background:#f7f9fc; box-shadow:0 6px 24px rgba(2,24,71,.06); }
.g-item img{ width:100%; height:auto; display:block; aspect-ratio:16/10; object-fit:cover; transition: transform .25s ease; }
.g-item:hover img{ transform: scale(1.02); }

/* Hide sections toggled by JS */
#foldersView[hidden], .album-section[hidden]{ display:none !important; }
</style>

<!-- HERO -->
<div class="full-bleed-row g-hero">
  <h1>Gallery</h1>
</div>

<!-- BODY -->
<div class="full-bleed-row g-wrap">

  {%- comment -%}
    Gather all static files under /assets/img/gallery/, group by immediate subfolder.
    Path parts: ["", "assets", "img", "gallery", "<FOLDER>", "file.ext"] -> folder index 4
  {%- endcomment -%}
  {% assign all = site.static_files | where_exp: "f", "f.path contains '/assets/img/gallery/'" %}
  {% assign img_exts = ".jpg,.jpeg,.png,.webp,.gif,.JPG,.JPEG,.PNG,.WEBP,.GIF" %}

  {% assign names = "" %}
  {% for f in all %}
    {% assign ext = f.extname %}
    {% if img_exts contains ext %}
      {% assign parts = f.path | split:'/' %}
      {% if parts.size > 5 %}
        {% assign folder = parts[4] %}
        {% unless names contains folder %}
          {% assign names = names | append: folder | append: "||" %}
        {% endunless %}
      {% endif %}
    {% endif %}
  {% endfor %}
  {% assign folders = names | split:"||" | uniq | sort %}
  {% assign folders = folders | reject: "" %}

  <!-- ======= FOLDERS VIEW (square buttons) ======= -->
  <section id="foldersView">
    {% if folders.size == 0 %}
      <p><em>No albums yet. Create subfolders inside <code>assets/img/gallery/</code> and add images.</em></p>
    {% else %}
      <div class="folder-grid">
        {% for name in folders %}
          {% capture fprefix %}/assets/img/gallery/{{ name }}/{% endcapture %}
          {% assign count = 0 %}
          {% for fl in all %}
            {% assign ext = fl.extname %}
            {% if img_exts contains ext and fl.path contains fprefix %}
              {% assign count = count | plus: 1 %}
            {% endif %}
          {% endfor %}
          {% assign slug = name | slugify %}
          <a class="folder-card" href="/gallery/?album={{ name | uri_escape }}" data-folder="{{ slug }}">
            <span class="folder-name">{{ name }}</span>
            <span class="badge">{{ count }}</span>
            <span class="folder-glyph" aria-hidden="true"></span>
          </a>
        {% endfor %}
      </div>
    {% endif %}
  </section>

  <!-- ======= ONE-ALBUM VIEW (all sections pre-rendered; JS shows one) ======= -->
  {% for name in folders %}
    {% capture fprefix %}/assets/img/gallery/{{ name }}/{% endcapture %}
    {% assign slug = name | slugify %}
    <section class="album-section" id="album-{{ slug }}" data-folder="{{ slug }}" hidden>
      <div class="album-actions">
        <a class="back-link" href="/gallery/">← Back to all albums</a>
        <strong>{{ name }}</strong>
      </div>
      <div class="g-grid">
        {% for file in all %}
          {% assign ext = file.extname %}
          {% if img_exts contains ext and file.path contains fprefix %}
            <figure class="g-item">
              <img src="{{ file.path | relative_url }}" alt="Gallery image">
            </figure>
          {% endif %}
        {% endfor %}
      </div>
    </section>
  {% endfor %}

</div>

<script>
(function(){
  // Read ?album=<Folder Name> from URL
  const params = new URLSearchParams(location.search);
  const albumName = params.get('album'); // pretty name
  if(!albumName){ return; }

  // Find slug that matches this name (case-insensitive)
  const cards = Array.from(document.querySelectorAll('.folder-card[data-folder]'));
  const byName = new Map(cards.map(c => [c.querySelector('.folder-name').textContent.trim().toLowerCase(), c.dataset.folder]));
  const slug = byName.get(albumName.trim().toLowerCase());
  if(!slug){ return; }

  // Hide folders view, show the chosen album section
  const foldersView = document.getElementById('foldersView');
  const section = document.querySelector('.album-section[data-folder="'+slug+'"]');
  if(foldersView && section){
    foldersView.hidden = true;
    section.hidden = false;
    // make URL pretty (keeps album param for sharing)
    const url = new URL(location.href);
    url.searchParams.set('album', albumName.trim());
    history.replaceState(null,'',url.toString());
  }
})();
</script>
