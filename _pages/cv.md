---
layout: page
permalink: /cv/
title: CV 
nav: true
nav_order: 2
cv_pdf: CV_website.pdf
cv_updated: 2026-10-27
---

{% assign cv_url = page.cv_pdf | prepend: 'assets/pdf/' | relative_url %}
{% assign cv_version = site.time | date: '%s' %}

<p><a href="{{ cv_url }}?v={{ cv_version }}" target="_blank" rel="noopener noreferrer"><i class="fas fa-file-pdf" aria-hidden="true"></i> Download CV (PDF)</a></p>

<p>Last updated: {{ page.cv_updated | date: '%-d %B %Y' }}</p>

<object data="{{ cv_url }}?v={{ cv_version }}" width="100%" height="1100" type="application/pdf">
  <p><a href="{{ cv_url }}?v={{ cv_version }}">Download the CV as a PDF.</a></p>
</object>
