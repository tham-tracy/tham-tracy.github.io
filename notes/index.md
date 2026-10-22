---
layout: summary
title: "Domain notes"
permalink: /notes/
description: "Short notes on how digital-asset infrastructure shapes product decisions - custody, on/off-ramps, stablecoins, yield and trading APIs."
---

<section class="portfolio-hero">
  <p class="eyebrow">Domain notes</p>
  <h1>Digital-asset infrastructure,<br><span>from a product angle.</span></h1>
  <p class="lede">Notes I keep on how the plumbing of digital assets - custody, fiat rails, stablecoins, yield and trading APIs - shapes what customers experience and the product decisions behind it.</p>
</section>

<section class="portfolio-section">
  <div class="note-grid">
    {%- assign notes = site.notes | sort: "order" -%}
    {%- for note in notes %}
    <a class="note-card" href="{{ note.url | relative_url }}">
      <p class="note-card-meta"><span class="tag">{{ note.tag }}</span>{{ note.read_time }} read</p>
      <h2>{{ note.title }}</h2>
      <p>{{ note.summary }}</p>
      <span class="note-card-cta">Read note <span aria-hidden="true">→</span></span>
    </a>
    {%- endfor %}
  </div>
</section>
