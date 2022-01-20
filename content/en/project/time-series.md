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


With the stationary data, we then examine the Autocorrelation Function (ACF) and Partial Autocorrelation Function (PACF) for each time series. From this initial analysis, we gain insight into the potential Autoregressive and Moving Average components of each series as well as if there is any seasonality. Firstly, we notice that both data sets have significant peaks at lags of multiples of 7, suggesting a seasonality with period 7. 

Using $\mathrm{ARIMA}(p,d,q)$ models, we see no clear cut-offs in the ACFs and PACFs. However, for Polish data (Fig. 2), we observe significant peaks on the ACF and PACF that suggest the p values of $2,3 \text{ or } 4$ and q values of $1,2 \text{ or } 3$. Whereas for Germany (Fig. 3), p values of the range $2 \text{ to } 5$ and q is $1 \text{ or } 2$.

<figure>
<img src="/acf_pacf.jpeg" style="width:100%">
<figcaption align = "center"><b>Figure 2 : ACF and PACF of differenced log Polish data.</b></figcaption>
</figure>

<figure>
<img src="/ACFPACFGermLogDiff.png" style="width:100%">
<figcaption align = "center"><b>Figure 3 : ACF and PACF of differenced log German data.</b></figcaption>
</figure>

### Model Fitting

Once we have stationary data, we try to find the best fit SARIMA models by using a manual, iterative Box-Jenkins approach. 

Before we begin building our models, we need to segment our data into training and test sets so we can assess the ability of our models to forecast the time series. Taking 10\% of the data leaves a forecast horizon of 31 days for the Polish data and 35 days for the German data.

The modelling procedure is composed of five iterative steps: estimation of $\mathrm{ARIMA}$ parameters, diagnostic checking, estimation of $\mathrm{SARIMA}$ parameters, further diagnostic checking and finally prediction.

Since there is no clear cut off in either data's ACF and PACF, we start the process with an $\mathrm{ARIMA}(1,1,1)$ and iterate, changing the p and q values until the best model has been found. To check the models, we look at the p-value of the Ljung-Box statistic, which should be above the threshold of 0.05. This tests the randomness of our residuals. Then, by plotting the ACF and PACF of the residuals, we look for the resemblance of white noise. Lastly, we select the model based on information criterion, such as Akaike’s Information Criterion (AIC), which measures the degrees of freedom/numbers of free parameters. As a result, we aim to choose a suitable model with the least AIC score in order to avoid over-fitting.


The seasonality to our data means that we can improve our $\mathrm{ARIMA}$ models by adding MA and AR components for seasonality - forming a $\mathrm{SARIMA}$ model. Hence we repeat the process above, but for the seasonal component, until settling on the best models for each data set.

Following this, we forecast our data (over the forecast horizon) using a fixed origin approach. We are then able to compare these forecasts to the real data to assess their ability. We finally use Error Matrix tests to measure the strength of, and error in, our predictions.   

## Results

$$\begin{table*}[t]\scriptsize
        \vspace{-0.3cm}
        \centering
        \begin{tabular}{c|c| c | c | c | c | c | c |c} 
        \hline
        \textbf{Data} & \textbf{Model} & \textbf{AIC} & \textbf{Log-Likelihood }& \textbf{Ljung-Box} & \textbf{MAE Av.}& \textbf{RMSE Av.}&  \textbf{MAE Roll. O. (k=1)} & \textbf{RMSE Roll. O. (k=1)} \\ [0.4ex] 
        \hline
         Polish & ARIMA(2, 1, 2) & 690.527 & -339.26 & 0.8102 & - & - & - & -\\
         Polish & ARIMA(3, 1, 4) & 696.4566 & -339.23 & 0.9779 & - & - & - & -\\
         Polish & ARIMA(1, 1, 3) & 714.0732 & -351.04 & 0.7366 & - & - & - & -\\
         Polish & SARIMA(2, 1, 2, 0, 1, 2, s = 7) & 642.42 & -314.39 & 0.9978 & 1.177 & 1.346 & 0.381 & 0.504\\         
         \vspace{0.15cm}
         Polish & SARIMA(3, 1, 4, 2, 1, 1, s = 7) & 638.695& -308.35 & 0.943 & 1.283 & 1.419 & 0.371 & 0.498 \\
         German & ARIMA(3, 0, 2) & 995.14 & -490.57 & 0.7555 & - & - & - & -\\
         German & ARIMA(4, 0, 2) & 992.63 & -488.32 & 0.6898 & - & - & - & -\\
         German & ARIMA(5, 0, 2) & 979.52 & -480.76 & 0.8863 & - & - & - & -\\
         German & SARIMA(3, 1, 2, 1, 0, 1, s = 7) & 957.27 & -469.64 & 0.9999 & 1.045 & 1.092 & 0.272 & 0.342\\ 
         German & SARIMA(5, 1, 2, 1, 0, 1, s = 7) & 961.46 & -469.73 & 0.9718 & 0.883 & 0.037 & 0.261 & 0.33\\
        \hline
        \end{tabular}
        \vspace{0.3cm}
        \caption{\footnotesize{Score comparisons for the Polish and German models.}}
        \label{scores}
        \vspace{-0.3cm}
    \end{table*}$$

### Polish Model

#### ARIMA Selection

Using R, we choose different permutations of parameters, starting from $\mathrm{ARIMA}(1,1,1)$, and select the best fitting models as described in the previous section. The scores for each test of the most appropriate models are displayed in the Table \ref{scores}. Based on that, we consider $\mathrm{ARIMA}(2,1,2)$ and $\mathrm{ARIMA}(3,1,4)$ for the SARIMA process.

#### SARIMA Selection

Building on $\mathrm{ARIMA}$, we repeat the process for the seasonal component and obtain two best performing models $\mathrm{SARIMA}(2,1,2, 0,1,2, s=7)$ and $\mathrm{SARIMA}(3, 1, 4, 2, 1, 1, s = 7)$. The ACF and PACF plots of their residuals (Fig. 4) are suitable for white noise, with a slightly better performance of the latter model.

<figure>
<img src="/res1.jpeg" style="width:100%">
<figcaption align = "center"><b>Figure 4 : ACF and PACF of residuals for both Polish models.</b></figcaption>
</figure>

#### Model Selection

For the final selection, we consider the complexity of the models – the first one is simpler than the second. For the Ljung-Box statistic - both pass the p-value threshold of 0.05 and residuals look like white noise. Finally, by comparing the AIC score, we choose $\mathrm{SARIMA}(3, 1, 4, 2, 1, 1, s = 7)$.

### German Model

#### ARIMA Selection

Similarly, we use R to repeat this process for the German data. The best performing 3 models across the selection criteria were $\mathrm{ARIMA}(3,1,2)$, $\mathrm{ARIMA}(4,1,2)$ and $\mathrm{ARIMA}(5,1,2)$ (see Table \ref{scores}), which we iterate on for the seasonal component to find the best $\mathrm{SARIMA}$ model.

#### SARIMA Selection

Further iteration on the seasonal MA and AR parameters provides $\mathrm{SARIMA}(3,1,2,1,0,1, s = 7)$ and $\mathrm{SARIMA}(5,1,2,1,0,1, s = 7)$ as the most appropriate models. 

#### Model Selection

In order to select the leading $\mathrm{SARIMA}$ model we require residuals that resemble white noise, so we plot the two model's respective residual's ACF and PACF. Both of these are suitable. Since both models have p-values close to one across many lags for the Ljung-Box statistic, we choose the simpler model $\mathrm{SARIMA}(3,1,2,1,0,1, s = 7)$ which has a lower AIC score.


<figure>
<img src="/res2.jpeg" style="width:100%">
<figcaption align = "center"><b>Figure 5 : ACF and PACF of residuals for both German models.</b></figcaption>
</figure>

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
