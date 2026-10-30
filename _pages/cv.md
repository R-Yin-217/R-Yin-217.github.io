---
layout: null
permalink: /cv/
title: CV
nav: true
nav_order: 5
cv_pdf: /assets/pdf/CV.pdf
sitemap: false
---

<!doctype html>
<html lang="{{ site.lang | default: 'en' }}">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="refresh" content="0; url={{ page.cv_pdf | relative_url }}">
    <title>CV</title>
  </head>
  <body>
    <p><a href="{{ page.cv_pdf | relative_url }}">Open CV (PDF)</a></p>
  </body>
</html>
