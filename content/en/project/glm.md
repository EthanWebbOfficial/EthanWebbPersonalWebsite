---
author: Ethan Webb
date: "2022-01-15"
description: An Analysis Of Smoking Cessation
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

{{< math.inline >}}
<p>
Inline math: \(\varphi = \dfrac{1+\sqrt5}{2}= 1.6180339887…\)
</p>
{{</ math.inline >}}

**Context:** As part of my Generalised Linear Models module, I worked in a group of 5 to produce a project, analysing the factors that contributed to smoking - using a fictional dataset. <mark>We achieved a grade of 95% on this report.</mark> All analysis in this project was conducted using R.

# An Analysis Of Smoking Cessation

## Abstract

The anti-smoking movement has created a cultural shift in recent decades, resulting in a rise of health concerns and relevant statistical analysis. We aim to answer the question of which path to smoking cessation based on lifestyle choices is the most successful. Throughout this report we have analysed data consisting of 4 categorical variables, and discovered that ``years smoked'' and ``methods'' are the most impactful in relation to smoking cessation. Furthermore, the best method out of the five options is individual therapy; the only one with a significant confidence interval at the 5\% significance level. Amongst the numerous conclusions that are drawn from this report, the most significant was that an individual is more likely to quit smoking, the shorter the amount of time they've been smoking for, with individuals being 6.45 times more likely to restart smoking if they've been smoking for 10 years compared to someone whose only been smoking for 4 years. We conclude by outlining which group of people are most at risk of restarting.


## Introduction 

Smoking has become a major problem for healthcare services in recent years as the amount of money spent on treating smoking related ailments has reached £3.6 billion per annum [1] and has put a huge strain on the NHS. 

In 1950, British researchers demonstrated a clear relationship between smoking and cancer, based on a preliminary report that would later become known as the British Doctors study. The study itself was carried out on a population of doctors, and followed up for 50 years. It can be considered the first strong statistical proof of the correlation between smoking habits and many serious diseases, including lung cancer [2]. The best way to combat this proven link is to reduce the number of individuals who smoke. This can be done by discouraging non-smokers from starting and encouraging smokers to quit.

The anti-smoking movement has had a cultural impact, as smoking has become more taboo, and those who smoke no longer have the same status as they did a few decades ago. The social and health-conscious deterrents, such as pictorial health warnings (which have become compulsory in the UK since October 2008) [3], have encouraged the smoking population to give up their cigarettes, either on their own, or with aids recommended by the NHS.

This cultural shift has intrigued statisticians and epidemiologists, resulting in longitudinal data analyses based on smoking cessation and the variables which may explain success or failure in giving up cigarettes for good.

We look at a sample of smoking cessation data which details both categorical and indicative variables, allowing us to visualise and predict the risk of an individual's likelihood to restart smoking. These explanatory variables include: the number of years smoked ($\mathrm{YS}$), the number of cigarettes smoked per day ($\mathrm{PD}$), whether the individual lives with other smokers ($\mathrm{O}$) and the method used to quit smoking ($\mathrm{M}$).
During this trial, smokers were given options and support on which methods to use to quit; including nicotine patches or gum, attending group therapy or individual talking therapy, and practicing mindfulness meditation. 

The binary response variable is whether or not the individual restarted smoking, ($\mathrm{R}$). In our analysis, we assume the data to be independent. However, given the dataset is from an NHS trust smoking cessation clinic it is possible that there is some dependence between observations (ie. smokers in the same household may both go to this clinic affecting each other).

In this report we model the data and perform various tests in order to determine the most successful cessation method out of the 5 techniques provided in the study.

## Methods

### Preliminary Analysis 

### Model Fitting 

### Model Testing / Diagnostics

## Results

### Preliminary Analysis 

### Model Fitting 

### Model Testing / Diagnostics

## Discussion

### Inference

### Conclusion

## References 

1. "Smoking and the public purse," accessed: 24/03/21. [Online]. Available: https://iea.org.uk/wpcontent/uploads/2017/08/Smoking-and-the-Public-Purse.pdf

2. R. Doll, R. Peto, J. Boreham, and I. Sutherland, "Mortality from cancer in relation to smoking: 50 years observations on british doctors," British journal of cancer, vol. 92 , no. 3 , Pp. 426429,2005 .

3. "Smoking warning labels", accessed: 25/03/21. [Online]. Available: https://ash.org.uk/category/informationand-resources/packaging-labelling-information-andresources/warning-labels/

4. "Smoking cessation in women," accessed: 07 / 04 / 21. [Online]. Available: https://link.springer.com/article/10.2165/00023210200115050-00005

5. M. Alexander H. Glassman, M. John E. Helzer, P. Lirio S. Covey, and et al, "Smoking, smoking cessation and major depression," 1990. [Online]. Available: https://jamanetwork.com/journals/jama/articleabstract/383334

6. "Depression in women," accessed: 07/04/21. [Online]. Available:https://www.sciencedirect.com/science/article/abs/pii/S0026049505000363?casatoken=iNxL2glSXkEAAAAA:eESsw2bFzd3lyWTV9VNEpq251ya3SPa0TvjkRWvNTzlQVacThzs0cdpTRV6GXi1yjrlpRAqt
