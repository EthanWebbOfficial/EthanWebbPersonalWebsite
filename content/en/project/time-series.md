---
author: Ethan Webb
date: "2022-01-18"
description: Analysis Of COVID-19 Daily New Deaths Of Poland and Germany
tags:
- shortcodes
- privacy
thumbnail: /covid-19.jpg
title: Covid-19 Time Series Analysis
math: true
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

**Context:** As part of my Time Series module, I worked in a group of 3 to use the skills learned during the course to produce a report and deliver a presentation on a data set relating to the Covid-19 pandemic. We chose to compare the daily new deaths of Germany and Poland since they share a boarder and had contrasting governance approaches to the pandemic. <mark>We scored 90\% on this project.</mark> I was very proud of this because the project was supposed to be done in groups of 4, however I was assigned to a group of 3 - with 2 people that spoke English as their second language. I learnt some great communication skills as a result. 


### Abstract

In this report we analysed Polish and German daily new deaths, recorded from March, 2020 to January, 2021, by considering \\(\mathbf{SARIMA}\\) models using an iterative Box-Jenkins approach. We conclude that for Polish data the best fitting model is $\mathbf{SARIMA(3, 1, 4, 2, 1, 1, s = 7)}$, whilst for Germany $\mathbf{SARIMA(3, 1, 2, 1, 0, 1, s = 7)}$. Our forecasting results suggest good performance across the models, validating their effectiveness. We discussed other important factors such as governments' response and also the limitations of our work. Finally, we explored ideas on how we could improve our analysis.



