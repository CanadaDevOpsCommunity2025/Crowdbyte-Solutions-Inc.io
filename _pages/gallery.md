---
layout: single
permalink: /gallery/
title: "Gallery"
sidebar: false
classes: "full-bleed"
---

<style>
/* Hide pager on this page */
.pagination, .pagination--pager { display:none !important; }

/* Full-bleed helpers */
.page.full-bleed .page__inner-wrap,
.page.full-bleed .page__content {
  max-width: none !important;
  padding-left: 0 !important;
  padding-right: 0 !important;
}
.full-bleed-row {
  width: 100vw;
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
}

/* Hero */
.g-hero {
  background:#2f5597;
  color:#fff;
  padding: clamp(28px,5vw,56px) 24px;
  text-align:center;
}
.g-hero h1 { margin:0; font-weight:800; font-size: clamp(28px,4.6vw,56px); }

/* Body */
.g-wrap { padding: 18px clamp(14px,3vw,40px); }

/* Grid */
.g-grid {
  display:grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: clamp(8px, 1.6vw, 16px);
  align-items:start;
}

/* Items */
.g-item {
  margin:0; padding:0;
  border-radius: 12px;
  overflow: hidden;
  background:#f7f9fc;
  box-shadow: 0 6px 24px rgba(2,24,71,.06);
}
.g-item img {
  width:100%; height:auto; display:block;
  aspect-ratio: 16/10;
  object-fit: cover;
  transition: transform .3s ease;
}
.g-item:hover img { transform: scale(1.02); }

/* Optional caption from filename */
.g-cap {
  margin:0; padding:8px 10px 10px;
  font-size: .9rem; color:#334155;
}
</style>

<!-- HERO -->
<div class="full-bleed-row g-hero">
  <h1>Gallery</h1>
</div>

<!-- BODY -->
<div class="full-bleed-row g-wrap">

  <!-- Auto-gallery: pull every file from assets/img/gallery -->
  {% assign gallery = site.static_files 
      | where_exp: "f", "f.path contains '/assets/img/gallery/'" 
      | sort: "name" %}

  {% if gallery and gallery.size > 0 %}
    <div class="g-grid">
      {% for file in gallery %}
        {% assign ext = file.extname | downcase %}
        {% if ext == '.jpg' or ext == '.jpeg' or ext == '.png' or ext == '.webp' or ext == '.gif' %}
          {% comment %}
            Build a simple caption from the filename (no extension):
            - replace dashes/underscores with spaces
            - collapse multiple spaces
            - capitalize first letter
          {% endcomment %}
          {% assign base = file.name | split: '.' | first %}
          {% assign cap = base | replace: '_',' ' | replace: '-',' ' | replace: '  ',' ' | strip %}
          {% assign cap = cap | slice: 0,1 | upcase | append: cap | slice: 1, cap.size %}

          <figure class="g-item">
            <img src="{{ file.path | relative_url }}" alt="{{ cap | escape }}">
            <figcaption class="g-cap">{{ cap }}</figcaption>
          </figure>
        {% endif %}
      {% endfor %}
    </div>
  {% else %}
    <p><em>No images found. Add files to <code>assets/img/gallery/</code>.</em></p>
  {% endif %}

</div>
