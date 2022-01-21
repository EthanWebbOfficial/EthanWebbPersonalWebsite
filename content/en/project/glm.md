---
author: Ethan Webb
date: "2022-01-15"
description: An Analysis Of Smoking Cessation
tags:
- shortcodes
- privacy
thumbnail: /smoking.png
title: Smoking - Generalised Linear Models
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

**Context:** As part of my Generalised Linear Models module, I worked in a group of 5 to produce a project, analysing the factors that contributed to smoking - using a fictional dataset. <mark>We achieved a grade of 95% on this report.</mark>

## Abstract

In this report we analysed Polish and German daily new deaths, recorded from March, 2020 to January, 2021, by considering \\(\mathbf{SARIMA}\\) models using an iterative Box-Jenkins approach. We conclude that for Polish data the best fitting model is \\(\mathbf{SARIMA(3, 1, 4, 2, 1, 1, s = 7)}\\), whilst for Germany \\(\mathbf{SARIMA(3, 1, 2, 1, 0, 1, s = 7)}\\). Our forecasting results suggest good performance across the models, validating their effectiveness. We discussed other important factors such as governments' response and also the limitations of our work. Finally, we explored ideas on how we could improve our analysis.

Block math:

$$
 \varphi = 1+\frac{1} {1+\frac{1} {1+\frac{1} {1+\cdots} } }
$$

Test 2 :

$$
\left[\begin{array}{l}
x_{1}(t) \\
x_{2}(t)
\end{array}\right]=\left[\begin{array}{l}
a_{1} \\
a_{2}
\end{array}\right]+\left[\begin{array}{ll}
\phi_{11} & \phi_{12} \\
\phi_{21} & \phi_{22}
\end{array}\right]\left[\begin{array}{l}
x_{1}(t-1) \\
x_{2}(t-2)
\end{array}\right]+\left[\begin{array}{l}
e_{1}(t) \\
e_{2}(t)
\end{array}\right]
$$