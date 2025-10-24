<!-- BEFORE -->
<a id="viewerClose" class="viewer-close" href="#gallery-home" aria-label="Close viewer and return to Gallery">✕</a>

<!-- AFTER (paste this instead) -->
<button
  id="viewerClose"
  class="viewer-close"
  type="button"
  aria-label="Close viewer and return to Gallery"
  onclick="
    (function(){
      var v = document.getElementById('viewer');
      var s = document.getElementById('viewerStrip');
      if (v) v.classList.remove('open');
      document.documentElement.classList.remove('viewer-lock');
      // stop any playing videos
      if (s) Array.prototype.forEach.call(s.querySelectorAll('iframe'), function(f){ f.src = f.src; });
      // ensure URL leaves #viewer without adding a new history entry
      if (location.hash === '#viewer' && history && history.replaceState){
        history.replaceState(null, '', '#gallery-home');
      }
      // focus back to grid
      var grid = document.getElementById('gallery-home');
      if (grid){
        grid.scrollIntoView({behavior:'smooth', block:'start'});
        setTimeout(function(){ try{ grid.focus({preventScroll:true}); }catch(e){} }, 
