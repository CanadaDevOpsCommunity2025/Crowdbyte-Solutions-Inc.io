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

/* Folder list */
.folder-list {
  display:grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: clamp(10px, 2vw, 18px); margin-bottom: 10px;
}
.folder-card {
  display:flex; align-items:center; gap:12px;
  background:#f7f9fc; border:1px solid #e6ecf8; border-radius:14px;
  padding:12px 14px; cursor:pointer;
  box-shadow:0 8px 24px rgba(2,24,71,.06);
  transition: transform .06s ease, box-shadow .2s ease, border-color .2s ease;
}
.folder-card:hover { transform: translateY(-1px); border-color:#d7e3ff; box-shadow:0 10px 30px rgba(2,24,71,.08); }
.folder-card[aria-expanded="true"] { border-color:#2f5597; box-shadow:0 10px 36px rgba(47,85,151,.18); }
.folder-icon{
  width:42px; height:34px; flex:0 0 auto;
  background: linear-gradient(180deg,#ffd36c,#ffb942);
  border-radius:6px 6px 4px 4px; position:relative;
  box-shadow: inset 0 -2px 0 rgba(0,0,0,.06);
}
.folder-icon:before{
  content:""; position:absolute; left:4px; top:-8px; width:22px; height:10px;
  background: linear-gradient(180deg,#ffe199,#ffd36c);
  border-radius:4px 4px 0 0; box-shadow: inset 0 -1px 0 rgba(0,0,0,.07);
}
.folder-name { margin:0; font-weight:800; color:#1f2a44; }
.folder-count { margin-left:auto; color:#2f5597; font-weight:700; font-size:.92rem; }

/* Images grid (no captions) */
.g-grid {
  display:grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: clamp(8px, 1.6vw, 16px); align-items:start;
  padding:12px 2px 2px 2px;
}
.g-item { margin:0; padding:0; border-radius:12px; overflow:hidden; background:#f7f9fc; box-shadow:0 6px 24px rgba(2,24,71,.06); }
.g-item img { width:100%; height:auto; display:block; aspect-ratio:16/10; object-fit:cover; transition: transform .25s ease; }
.g-item:hover img { transform: scale(1.02); }

/* Hide/show image sections */
.folder-images[hidden] { display:none !important; }

/* Tiny helper */
.m0 { margin:0; }
</style>

<!-- HERO -->
<div class="full-bleed-row g-hero">
  <h1>Gallery</h1>
</div>

<!-- BODY -->
<div class="full-bleed-row g-wrap">

  {%- comment -%}
    Build a list of unique subfolders directly under /assets/img/gallery/
    Example: /assets/img/gallery/<FOLDER>/<image>.jpg
  {%- endcomment -%}
  {%- assign all = site.static_files | where_exp: "f", "f.path contains '/assets/img/gallery/'" -%}
  {%- assign img_exts = ".jpg,.jpeg,.png,.webp,.gif,.JPG,.JPEG,.PNG,.WEBP,.GIF" -%}

  {%- assign names = "" -%}
  {%- for f in all -%}
    {%- assign ext = f.extname -%}
    {%- if img_exts contains ext -%}
      {%- assign parts = f.path | split:'/' -%}
      {%- if parts.size > 5 -%}
        {%- assign folder = parts[4] -%}  {# index: "",assets,img,gallery,FOLDER,file #}
        {%- unless names contains folder -%}
          {%- assign names = names | append: folder | append: "||" -%}
        {%- endunless -%}
      {%- endif -%}
    {%- endif -%}
  {%- endfor -%}

  {%- assign folders = names | split:"||" | uniq | sort -%}
  {%- assign folders = folders | reject: "" -%}

  {%- if folders.size == 0 -%}
    <p class="m0"><em>No images yet. Create subfolders inside <code>assets/img/gallery/</code> (one per event) and add images.</em></p>
  {%- else -%}
    <!-- Folder cards -->
    <div class="folder-list" id="folderList">
      {%- for name in folders -%}
        {%- assign slug = name | slugify: 'pretty' -%}
        {%- assign files = all | where_exp: "f", "f.path contains '/assets/img/gallery/' | append: name | append: '/'" -%}
        {%- assign count = 0 -%}
        {%- for fl in files -%}
          {%- assign ext = fl.extname -%}
          {%- if img_exts contains ext -%}{%- assign count = count | plus: 1 -%}{%- endif -%}
        {%- endfor -%}

        <button class="folder-card" type="button" data-folder="{{ slug }}" aria-expanded="false" aria-controls="images-{{ slug }}">
          <span class="folder-icon" aria-hidden="true"></span>
          <span class="folder-name">{{ name }}</span>
          <span class="folder-count">{{ count }}</span>
        </button>
      {%- endfor -%}
    </div>

    <!-- Images per folder -->
    {%- for name in folders -%}
      {%- assign slug = name | slugify: 'pretty' -%}
      {%- assign imgs = all | where_exp: "f", "f.path contains '/assets/img/gallery/' | append: name | append: '/'" -%}
      <section class="folder-images" id="images-{{ slug }}" data-folder="{{ slug }}" hidden>
        <div class="g-grid">
          {%- for file in imgs -%}
            {%- assign ext = file.extname -%}
            {%- if img_exts contains ext -%}
              <figure class="g-item">
                <img src="{{ file.path | relative_url }}" alt="Gallery image">
              </figure>
            {%- endif -%}
          {%- endfor -%}
        </div>
      </section>
    {%- endfor -%}
  {%- endif -%}
</div>

<script>
(function(){
  const params = new URLSearchParams(location.search);
  const desiredName = params.get('album'); // exact folder name support
  const cards = Array.from(document.querySelectorAll('.folder-card[data-folder]'));
  const sections = Array.from(document.querySelectorAll('.folder-images[data-folder]'));

  function show(folderSlug){
    // collapse all
    cards.forEach(c => c.setAttribute('aria-expanded','false'));
    sections.forEach(s => s.hidden = true);
    // expand target
    const targetCard = cards.find(c => c.dataset.folder === folderSlug);
    const target = sections.find(s => s.dataset.folder === folderSlug);
    if(targetCard && target){
      targetCard.setAttribute('aria-expanded','true');
      target.hidden = false;
      // scroll into view (nice for deep linking)
      setTimeout(()=> targetCard.scrollIntoView({behavior:'smooth', block:'start'}), 50);
      // update URL with readable album name
      const name = targetCard.querySelector('.folder-name')?.textContent?.trim() || '';
      const url = new URL(location.href);
      if(name){ url.searchParams.set('album', name); }
      else { url.searchParams.delete('album'); }
      history.replaceState(null,'',url.toString());
    }
  }

  // map pretty name -> slug using the folder-name text
  const byName = new Map(cards.map(c => [c.querySelector('.folder-name').textContent.trim().toLowerCase(), c.dataset.folder]));

  // initial: open from ?album=, else first folder
  let start = cards[0]?.dataset.folder;
  if(desiredName){
    const wanted = byName.get(desiredName.trim().toLowerCase());
    if(wanted) start = wanted;
  }
  if(start) show(start);

  // clicks
  cards.forEach(c => c.addEventListener('click', () => {
    const expanded = c.getAttribute('aria-expanded') === 'true';
    if(expanded){
      // collapse if already open
      c.setAttribute('aria-expanded','false');
      const sec = sections.find(s => s.dataset.folder === c.dataset.folder);
      if(sec) sec.hidden = true;
      // clear URL param
      const url = new URL(location.href); url.searchParams.delete('album'); history.replaceState(null,'',url.toString());
    }else{
      show(c.dataset.folder);
    }
  }));
})();
</script>
