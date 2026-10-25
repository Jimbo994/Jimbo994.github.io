---
layout: page
permalink: /publications/
title: Publications
description: Research papers, preprints, and doctoral and master's theses.
years: [2026, 2025, 2024, 2023, 2022, 2021]
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->
<nav class="publication-sections" aria-label="Publication sections">
  <a href="#papers">Papers &amp; preprints</a>
  <a href="#theses">Theses</a>
</nav>

<div class="publications">

<section id="papers" aria-labelledby="papers-heading">
  <h2 id="papers-heading" class="section-heading">Papers &amp; preprints</h2>
{%- for y in page.years %}
  <h3 class="year">{{y}}</h3>
  {% bibliography -f papers -q @article[year={{y}}],@inproceedings[year={{y}}] %}
{% endfor %}
</section>

<section id="theses" aria-labelledby="theses-heading">
  <h2 id="theses-heading" class="section-heading">Theses</h2>
  {% bibliography -f papers -q @phdthesis,@mastersthesis %}
</section>

</div>
