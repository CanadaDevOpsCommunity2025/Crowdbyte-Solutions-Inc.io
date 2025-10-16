---
layout: single
permalink: /gallery/
title: "Gallery"
sidebar: false
classes: "full-bleed"
---

<style>
/* Hide built-in title/pager; keep only the hero */
.page__title, .pagination, .pagination--pager { display:none !important; }

/* Full-bleed hero only */
.full-bleed-row { width:100vw; margin-left:calc(50% - 50vw); margin-right:calc(50% - 50vw); }
.g-hero { background:#2f5597; color:#fff; padding:clamp(28px,5vw,56px) 24px; text-align:center; }
.g-hero h1 { margin:0; font-weight:800; font-size:clamp(28px,4.6vw,56px); }

/* Body: CONSTRAINED WIDTH so cards don’t cover entire page */
.g-wrap {
  max-width: 1100px;  /* adjust to taste (e.g., 960px or 1200px) */
  margin: 18px auto 40px;
  padding: 0 clamp(12px, 3vw, 24px);
}

/* ===== Small square folder cards with thumbnail ===== */
.folder-grid{
  display:grid;
  grid-template-columns: repeat(auto-fit, minmax(140px, 180px)); /* small squares */
  gap: clamp(10px, 1.6vw, 18px);
  justify-content:center; /* center the grid */
}
.folder-card{
  display:block; position:relative; text-decoration:none;
  aspect-ratio: 1 / 1;     /* perfect square */
  border-radius:12px; overflow:hidden;
  border:1px solid #e6ecf8; background:#f7f9fc;
  box-shadow:0 8px 20px rgba(2,24,71,.06);
  transition:transform .07s ease, box-shadow .2s ease, border-color .2s ease;
}
.folder-card:hover{ transform:translateY(-2px); border-color:#d7e3ff; box-shadow:0 12px 28px rgba(2,24,71,.1); }

/* Thumbnail */
.folder-thumb{
  position:absolute; inset:0;
  background-size:cover; background-position:center;
  filter:saturate(1.05);
}

/* Subtle gradient + label */
.folder-fade{
  position:absolute; inset:0;
  background:linear-gradient(180deg, rgba(0,0,0,0) 55%, rgba(0,0,0,.45) 100%);
}
.folder-label{
  position:absolute; left:8px; right:8px; bottom:8px;
  display:flex; align-items:center; gap:8px;
}
.folder-icon{
  width:22px; height:16px; flex:0 0 auto; position:relative;
  background:linear-gradient(180deg,#ffd36c,#ffb942);
  border-radius:4px 4px 3px 3px; box-shadow:inset 0 -1px 0 rgba(0,0,0,.08);
}
.folder-icon:before{
  content:""; position:absolute; left:3px; top:-6px; width:12px; height:6px;
  background:linear-gradient(180deg,#ffe199,#ffd36c);
  border-radius:4px 4px 0 0; box-shadow:inset 0 -1px 0 rgba(0,0,0,.08);
}
.folder-name{
  color:#fff; font-weight:800; font-size:.85rem; line-height:1.2; text-shadow:0 1px 2px rgba(0,0,0,.35);
  max-height:2.4em; overflow:hidden;
}
.folder-count{
  margin-left:auto; color:#fff; font-weight:700; font-size:.75rem; background:rgba(0,0,0,.35);
  padding:.15rem .45rem; border-radius:999px;
}

/* ===== One-album view (constrained width too) ===== */
.album-actions{
  display:flex; justify-content:space-between; align-items:center; gap:10px; margin-bottom:10px;
}
.back-link{
  display:inline-block; padding:.4rem .65rem; border:1px solid #d7e3ff; border-radius:8px;
  color:#2f5597; text-decoration:none; font-weight:700; background:#fff;
}
.back-link:hover{ background:#f5f8ff; border-color:#2f5597; }

.g-grid{
  display:grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: clamp(8px, 1.4vw, 14px);
}
.g-item{ margin:0; padding:0; border-radius:12px; overflow:hidden; background:#f7f9fc; box-shadow:0 6px 20px rgba(2,24,71,.06); }
.g-item img{ width:100%; height:auto; display:block; aspect-ratio:16/10; object-fit:cover; transition:transform .22s ease; }
.g-item:hover img{ transform:scale(1.02); }

/* Toggle sections */
#foldersView[hidden], .album-section[hidden]{ display:none !important; }
</style>

<!-- HERO -->
<div class="full-bleed-row g-hero">
  <h1>Gallery</h1>
</div>

<!-- BODY (constrained width) -->
<div class="g-wrap">

  {% comment %}
    Collect subfolders under /assets/img/gallery/ and build small square cards.
    First image in each folder is used as the thumbnail.
  {% endcomment %}
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

  <!-- ===== FOLDERS VIEW (small square buttons) ===== -->
  <section id="foldersView">
    {% if folders.size == 0 %}
      <p><em>No albums yet. Create subfolders in <code>assets/img/gallery/</code> and add images.</em></p>
    {% else %}
      <div class="folder-grid">
        {% for name in folders %}
          {% capture fprefix %}/assets/img/gallery/{{ name }}/{% endcapture %}
          {% assign count = 0 %}
          {% assign thumb = "" %}
          {% for fl in all %}
            {% assign ext = fl.extname %}
            {% if img_exts contains ext and fl.path contains fprefix %}
              {% assign count = count | plus: 1 %}
              {% if thumb == "" %}
                {% assign thumb = fl.path %}
              {% endif %}
            {% endif %}
          {% endfor %}
          {% assign slug = name | slugify %}
          <a class="folder-card" href="/gallery/?album={{ name | uri_escape }}" data-folder="{{ slug }}">
            <span class="folder-thumb" style="background-image:url('{{ thumb | relative_url }}');" aria-hidden="true"></span>
            <span class="folder-fade" aria-hidden="true"></span>
            <span class="folder-label">
              <span class="folder-icon" aria-hidden="true"></span>
              <span class="folder-name">{{ name }}</span>
              <span class="folder-count">{{ count }}</span>
            </span>
          </a>
        {% endfor %}
      </div>
    {% endif %}
  </section>

  <!-- ===== ONE-ALBUM VIEW ===== -->
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
  // Switch to album view if ?album=<Folder Name> present
  const params = new URLSearchParams(location.search);
  const albumName = params.get('album');
  if(!albumName) return;

  const cards = Array.from(document.querySelectorAll('.folder-card[data-folder]'));
  const nameToSlug = new Map(cards.map(c => [c.querySelector('.folder-name').textContent.trim().toLowerCase(), c.dataset.folder]));
  const slug = nameToSlug.get(albumName.trim().toLowerCase());
  if(!slug) return;

  const foldersView = document.getElementById('foldersView');
  const albumSection = document.querySelector('.album-section[data-folder="'+slug+'"]');
  if(foldersView && albumSection){
    foldersView.hidden = true;
    albumSection.hidden = false;
    // Keep shareable URL
    const url = new URL(location.href);
    url.searchParams.set('album', albumName.trim());
    history.replaceState(null,'',url.toString());
  }
})();
</script>
