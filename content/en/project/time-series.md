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


## Abstract

In this report we analysed Polish and German daily new deaths, recorded from March, 2020 to January, 2021, by considering \\(\mathbf{SARIMA}\\) models using an iterative Box-Jenkins approach. We conclude that for Polish data the best fitting model is \\(\mathbf{SARIMA(3, 1, 4, 2, 1, 1, s = 7)}\\), whilst for Germany \\(\mathbf{SARIMA(3, 1, 2, 1, 0, 1, s = 7)}\\). Our forecasting results suggest good performance across the models, validating their effectiveness. We discussed other important factors such as governments' response and also the limitations of our work. Finally, we explored ideas on how we could improve our analysis.

## Introduction

Coronavirus Disease 2019 (COVID-19) emerged in Wuhan, China in late 2019. By January 30th 2020, WHO declared a Public Health Emergency of International Concern [1] and by March 2020 a Global Pandemic had been established [2]. As the pandemic evolved, the epicentre shifted from the Hubei Province to Central Europe and, as of January 31st 2020, Europe’s 5 largest countries are all in the World’s top 10 for most COVID-19 cases - meanwhile China sits 83rd [3]. With that in mind, the European data is important to understanding the nature of the pandemic and how it might progress. 

Throughout the course of history, humans have experienced the deadliest plagues, infectious diseases and epidemics, which have wiped out millions of people. Every outbreak has long-lasting effects on society and causes great suffering on humankind. However, through mathematical modelling we can learn from the past to advance our understanding of epidemiology, push medical innovation and reduce casualties.

Since the beginning of the outbreak, many mathematical and computational models have been published to analyse and predict the coronavirus case and death figures. These models are fundamental to government decision makers attempting to minimise the number of deaths and strain on health services, whilst ensuring the economy can function as best as possible. At the start of the pandemic, Zeynep Ceylan [4] modelled COVID-19 case figures in Spain, Italy and the UK using ARIMA models with second order differencing to help epidemiologists assess the worst affected areas. Meanwhile other models focused on forecasting the spread and death rate of coronavirus [5].

We analyse the Polish and German data of new daily deaths from March, 2020 to January 2021. Germany and Poland share a border and have similar levels of total deaths. This makes their comparison of interest because it could reveal how other factors such as governance approach, population density and country footfall affect the pandemic. Whilst we acknowledge countries have different methods of recording death figures, we choose to study new daily deaths as they are more reliable than case figures - you can't misdiagnose a death.

In our study, we build models to predict the number of new deaths, and compare the differences in these two series. Additionally, we look at how the restrictions and lockdowns impact these series as well as discussing the strength of our forecasts and the trends that lie within. The data has been obtained from Our World In Data (OWID) [6].

## Methods

To begin the process of our analysis, we first layout our intentions. We wish to compare the new daily deaths of Germany and Poland. As a result, we first examine the raw data, to explore trends and stationarity, before fitting models in order to forecast how the new daily deaths might progress – all so we can assess the similarities and differences between the two countries.  

### Preliminary Analysis

To build our models we rely on useful results such as Wold's Decomposition, which allows us to write one time series as the sum of two time series - one deterministic and one stochastic. In order to use this result, we require our data to be independent and have constant stochastic properties, in other words we need stationarity. Upon our initial plots (Fig. 1), it is evident that the raw data does not meet this condition since the mean is not constant, whilst the variance and covariance differ across time. This observation is reaffirmed by an Augmented Dickey-Fuller Test (ADF) on the raw data, which yields  p-values of 0.9286 and 0.99, for Poland and Germany respectively. 

<figure>
<img src="/Polish&German.png" style="width:100%">
<figcaption align = "center"><b>Figure 1 : Poland's (Red) and Germany's (Blue) new daily deaths.</b></figcaption>
</figure>

### Model Fitting

## Results

### Polish Model

### German Model

### Forecasting Models For Both Countries

## Discussion

### Impact of Lockdowns and Restrictions

### Improvements

## Conclusion

## References 

1. M. T. Meehan, D. P. Rojas, A. I. Adekunle, O. A. Adegboye, J. M. Caldwell, E. Turek, B. Williams, J. M. Trauer, and E. S. McBryde, “Modelling insights into the covid-19 pandemic,” Paediatric respiratory reviews, 2020. 1

2. “Coronavirus disease travel information (covid-19).” [Online]. Available: https://www.fitfortravel.nhs.uk/advice/disease-prevention-advice/coronavirus-disease-covid-19 1

3. “Coronavirus cases woldometer data.” [Online]. Available: https://www.worldometers.info/coronavirus/?utmcampaign=homeAdvegas1%3F#countries 1

4. Z. Ceylan, “Estimation of covid-19 prevalence in italy, spain, and france,” Science of The Total Environment, vol. 729, p. 138817, 2020. 1

5.  M. R. Mahmoudi, M. Maleki, and A. Pak, “Testing the difference between two indepen- dent time series models,” Iranian Journal of Science and Technology, Transactions A: Science, vol. 41, no. 3, pp. 665–669, 2017. 1

6. M. Roser, H. Ritchie, E. Ortiz-Ospina, and J. Hasell, “Coronavirus pandemic (covid-19) - statistics and research,” Mar 2020. [Online]. Available: https://ourworldindata.org/coronavirus 1

7. A. A.-S. N.-F. A.Ramadan, A. Kamel, “A multivariate data analysis approach for investigating daily statistics of countries affected with covid-19 pandemic,” 2020, source accessed on 05-02-2021”https://www.sciencedirect.com/science/article/pii/S240584402032418X”. 5

8. A. Singh, “A multivariate time series guide to forecasting and modeling,” 2020, source accessed on 05-02-2021 ”https://www.analyticsvidhya.com/blog/2018/09/multivariate-time-series-guide-forecasting-modeling-python-codes/#:∼:text=A%20Multivariate%20time%20series%20has,used%20for%20forecasting%20future%20values.&text=In%20this%20case%2C%20there%20are,considered%20to%20optimally%20predict%20temperature”. 5
