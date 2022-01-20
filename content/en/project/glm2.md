---
author: Ethan Webb
date: "2022-01-18"
description: Modelling The Number Of Feeds For Bird Chicks
tags:
- shortcodes
- privacy
thumbnail: /bird-feed.png
title: Bird Chick Feeding - Generalised Linear Models
---

<!-- START Keep For Maths -->
{{< math.inline >}}
{{ if or .Page.Params.math .Site.Params.math }}

<!-- KaTeX -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.11.1/dist/katex.min.css" integrity="sha384-zB1R0rpPzHqg7Kpt0Aljp8JPLqbXI3bhnPWROx27a9N0Ll6ZP/+DiW/UqRcLbRjq" crossorigin="anonymous">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.11.1/dist/katex.min.js" integrity="sha384-y23I5Q6l+B6vatafAwxRu/0oK/79VlbSz7Q9aiSZUvyWYIYsd+qj+o24G5ZU2zJz" crossorigin="anonymous"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.11.1/dist/contrib/auto-render.min.js" integrity="sha384-kWPLUVMOks5AQFrykwIup5lo0m3iMkkHrD0uJ4H5cjeGihAutqP0yW0J6dpFiVkI" crossorigin="anonymous" onload="renderMathInElement(document.body);"></script>
{{ end }}
{{</ math.inline >}}
<!-- END Keep For Maths -->

**Context:** As part of my Statistical Fundamentals module I wrote a report on some Bird Chick Feeding Data (fictional), analysing which factors affect the amount of food chicks from this species receive. I was disappointment in my work this project because I felt I could have done better given more time. <mark>I was awarded a letter grade of A for this project which translated to 75\% (presumably to mitigate against grade inflation).</mark> My work in this project was a contributing factor in the lecturers decision to approach me about a PhD opportunity.
