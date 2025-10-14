---
layout: single
title: "Submit a Contribution"
permalink: /submit-contribution/
sidebar: false
---

<style>
.form-card {
  border: 1px solid #e5e7eb; background:#fafafa; border-radius:12px; padding:18px;
}
.form-card h2 { margin:0 0 10px; font-size:22px; font-weight:800; }
.form-grid { display:grid; grid-template-columns: 1fr 1fr; gap: 14px; }
@media (max-width: 720px){ .form-grid { grid-template-columns: 1fr; } }
.form-card label { display:block; font-weight:600; margin: 8px 0 6px; }
.form-card input[type="text"],
.form-card input[type="email"],
.form-card select,
.form-card textarea {
  width:100%; border:1px solid #d1d5db; border-radius:10px; padding:10px 12px; font:inherit; background:#fff;
}
.form-card textarea { min-height: 140px; resize: vertical; }
.form-card .required::after { content:" *"; color:#dc2626; }
.form-card .hint { font-size:12px; color:#6b7280; margin-top:4px; }
.actions { margin-top:16px; display:flex; gap:10px; align-items:center; }
.actions .btn { border-radius:999px; }
</style>

<div class="form-card">
  <h2>Submit a Contribution</h2>
  <p>Choose your contribution type and share a brief summary. We’ll get back to you shortly.</p>

  <!-- Replace action with your real Formspree endpoint -->
  <form method="POST" action="https://formspree.io/f/XXXXXXXX">
    <label class="required" for="topic">What is this about</label>
    <select id="topic" name="topic" required>
      <option value="" disabled selected>Select one…</option>
      <option>Start your own DevOps for GenAI Hackathon Day</option>
      <option>Be a Spotlight contributor</option>
      <option>Drive next steps for open-source project</option>
      <option>Write for us</option>
      <option>Sponsor Hackathon / Event / Summit</option>
    </select>

    <div class="form-grid">
      <div>
        <label class="required" for="name">Your Name</label>
        <input id="name" name="name" type="text" autocomplete="name" required />
      </div>
      <div>
        <label class="required" for="email">Email</label>
        <input id="email" name="email" type="email" autocomplete="email" required />
      </div>
    </div>

    <div class="form-grid">
      <div>
        <label for="organization">Organization (optional)</label>
        <input id="organization" name="organization" type="text" />
      </div>
      <div>
        <label for="role">Role / Title (optional)</label>
        <input id="role" name="role" type="text" />
      </div>
    </div>

    <label class="required" for="summary">Short summary</label>
    <textarea id="summary" name="summary" placeholder="Tell us briefly what you’d like to contribute…" required></textarea>
    <div class="hint">E.g., talk/workshop idea, open-source contribution, sponsorship interest, or an article outline.</div>

    <label for="details">Details (links welcome)</label>
    <textarea id="details" name="details" placeholder="Add details, links to repos/slides, topics, audience, timelines, etc."></textarea>

    <label><input type="checkbox" name="consent" value="yes" required> I agree to be contacted about this submission.</label>

    <!-- Optional helpers for Formspree -->
    <input type="hidden" name="_subject" value="New Contribution via Submit page" />
    <input type="hidden" name="_template" value="table" />
    <input type="hidden" name="_redirect" value="{{ site.url }}{{ site.baseurl }}/submit-contribution/" />

    <div class="actions">
      <button class="btn btn--primary" type="submit">Submit Contribution</button>
      <a class="btn" href="{{ site.baseurl }}/contact/">Prefer to Contact Us</a>
    </div>
  </form>
</div>

<!-- Hide pager on this page too -->
<style>
.pagination, .pagination--pager { display:none !important; }
</style>
