Exploring COVID-19 Data
================
by omarxinyijohn

## Summary

Reported first in December, 2019, the COVID-19 pandemic constitutes the
largest global public health crisis in a century, with daunting health
and socioeconomic challenges. In the United States alone, more than
700,000 people have lost their lives due to the public health crisis.
The progress in vaccination rates, as well as the spread of the Delta
variant, adds more nuance to the overall situation. In this project, we
explore COVID-19 data in the United States (more specifically, the 50
states plus D.C.) using two publicly available data sets sourced from
the CDC. One of these data sets includes cases and deaths data broken
down by state and date, and the other includes vaccination data broken
down by state and date. These data sets can be found in the reference
section of this document.

We start by simply exploring the relationship between deaths and cases
since the CDC began recording this type of data on January 22nd, 2020.
We first visualized daily new cases versus time and daily new deaths
versus time. Based on these two plots, which have almost identical
shape, it appeared that daily new deaths and daily new cases are
linearly related. A simple plot of daily new deaths versus daily new
cases confirmed this. We then fit a linear model to this deaths versus
cases data to predict how many deaths we would expect on any individual
day given a certain number of cases. The linear model is given by

*y* = 0.01146*x* + 274.67437

Where x is the number of cases and y is the number of deaths. This tells
us that for each additional daily case, we expect the number of daily
deaths to increase on average by 0.01146. Additionally, we found that
*R*<sup>2</sup> = 0.673, which indicates that about 67.3% of the
variation in the daily new deaths is dependent on daily new cases. Why
is the *R*<sup>2</sup> not any higher? Well, there could be a multitude
of reasons. The most obvious reason is that we have not factored in any
other variables such as vaccination rates or seasonality, but a less
obvious reason is that our data is not perfectly reliable. One might
notice from the daily new deaths versus daily new cases plot that there
is a higher ratio of deaths to cases closer to the origin. This reflects
how at the beginning of the pandemic, this ratio was higher, likely due
to a combination of high susceptibility of the population dealing with
the novelty of the disease and the fact that a robust testing regimen
had not been developed yet. In other words, there could have been cases
not counted in the data due to a lack of testing infrastructure. This
problem likely persists throughout the dataset, as it is unlikely that
everyone who has had COVID-19 has also been tested for it at the same
time.

To further explore the relationship between deaths and cases, we also
took into account the correlation and cross correlation of the two
variables. Typically, when we are comparing two variables *X* and *Y*,
we calculate the correlation coefficient
$$\\rho = \\frac{\\sigma\_{XY}}{\\sigma\_X\\sigma\_Y}$$
The correlation coefficient describes how one variable moves in relation
to another. When dealing with time series data and both *X* and *Y* are
functions of time, the time series *Y*<sub>*t*</sub> might be related to
past lags of the time series *X*<sub>*t*</sub>. In other words, if our
time series is discrete (it must be), we want to determine the
relationship between *X*<sub>*t* + *h*</sub> and *Y*<sub>*t*</sub> for
*h* = 0,  ± 1,  ± 2, ... . The **cross correlation coefficient** is thus
given by
$$\\rho = \\frac{\\sigma\_{X\_{t + h}Y\_t}}{\\sigma\_{X\_{t + h}}\\sigma\_{Y\_t}}$$

Two things to note :

-   When one or more *X*<sub>*t* + *h*</sub>, with *h* *negative*, are
    predictors of *Y*<sub>*t*</sub>, it is sometimes said that **x leads
    y**

-   When one or more *X*<sub>*t* + *h*</sub>, with *h* *positive*, are
    predictors of *Y*<sub>*t*</sub>, it is sometimes said that **x lags
    y**

In this case, we say cases are a predictor of deaths and cases leads
deaths, so it makes sense to consider negative values of *h*. If we take
a look at our plot of the cross correlation along with the underlying
data, it appears that the highest correlation between deaths and cases
is at a value of *h* =  + 7 where correlation  ≈ 0.85. However, this
implies that cases in the future (plus seven days) are more related to
deaths in the present than cases in the present (i.e. when *h* = 0),
which does not make much sense in this context. One interesting thing to
note is that the correlation seems to spike every seven days. In other
words, there is a local maximum of correlation every seven days. If we
let *h* =  − 7 days (i.e. let the cases variable lead deaths by 7 days),
then we have a local minimum of correlation equal to approximately 0.72.
It is difficult to explain why the greatest correlation occurs when *h*
is positive, but it might again be explained by the early pandemic when
testing was not widely available, but determining cause of death was
easy. In theory, as testing capacity increased, so did case count, which
would show that cases lagged deaths for a period of time.

Another fundamental factor for analysing COVID-19 data is vaccination
rates. Due to the limitation of the two data sets in capturing the
multitude of nuances involved in the pandemic (mask mandates,
stay-at-home orders, differing general behaviors in different states,
etc.) it is impossible to conduct a complete rigorous examination of the
effectiveness of vaccination through our cursory exploration, but it is
still possible to gain a modicum of insight by conducting a basic
analysis of the data. We started this analysis by examining overall
vaccination rates as a function of time. While this examination showed
that the overall vaccination rate in the United States was only just
over 55% as of early October, 2021, this hid the fact that the
vaccination rate does indeed vary widely by age group. By faceting the
data by age group, we saw that the 65+ age group is approaching a 90%
vaccination rate, suggesting that one of the most vulnerable demographic
groups in this pandemic has largely been inoculated in comparison with
younger demographics. We also examined the cross correlation between
daily new deaths and the percent of the population fully vaccinated. In
this context, we choose vaccinations as the predictor variable. If we
examine the plot and corresponding output, it would appear that
vaccinations lead deaths by approximately 65 days, as this is the point
where the two variables become maximally negatively correlated and *h*
is negative. In other words, this is the point where an increase in
vaccinations most strongly correlates with a decrease in deaths. This
correlation is approximately  − 0.313 which is not significantly strong
but certainly noteworthy. Again, the caveat needs to be added that our
results are only as good as our data, and given the simple nature of our
analysis, it is difficult to factor in the multitude of potential
variables that could also be impacting the death numbers.

The last part of our analysis involves examining the relationship
between the season and deaths/cases. The COVID-19 virus is thought to
spread mainly from person to person through respiratory droplets
produced when an infected person coughs, sneezes, or talks. Thus, the
different activities people engaged in in different seasons, as well as
the weather conditions, might have had a significant impact on the
spread of COVID-19. Before examining this impact, we started our
analysis by defining the four seasons as:

-   Fall: September, October, November
-   Winter: December, January, February
-   Spring: March, April, May
-   Summer: June, July, August

When our data was faceted by season, we found that the winter has the
highest mean and median case count, followed by the fall, summer, and
spring. We also wanted to see if including the season as a predictor
improved our model of deaths versus cases. To test this theory, we used
the main versus interaction effects method we learned this semester. In
other words, we compared the model leaving the rate of change of deaths
per case the same by season (main effects) to the model where the rate
of change of deaths per case changes by season. By adding the season
variable as a predictor, we were able to increase the adjusted
*R*<sup>2</sup> value, suggesting that it makes sense to factor in
seasonality into our model. However, a caveat must be added that we only
have data for approximately two years of COVID-19 (two cycles of
seasons), so it is possible that seasonality might not have as much of
an effect given future seasonal data.

## Presentation

Our presentation can be found [here](presentation/presentation.html).

## Data

Surveillance Review and Response Group, 2020, *Centers for Disease
Control and Prevention, COVID-19 Response. COVID-19 Case Surveillance
Public Data Access, Summary, and Limitations*, electronic dataset,
Centers for Disease Control and Prevention,
<https://data.cdc.gov/Case-Surveillance/United-States-COVID-19-Cases-and-Deaths-by-State-o/9mfq-cb36>.

NCIRD, 2020, *COVID-19 Vaccinations in the United States, Jurisdiction*,
electronic dataset, Centers for Disease Control and Prevention,
<https://data.cdc.gov/Vaccinations/COVID-19-Vaccinations-in-the-United-States-Jurisdi/unsk-b7fc>.

## References

-   <https://online.stat.psu.edu/stat510/lesson/8/8.2>
-   <https://data.cdc.gov/Case-Surveillance/United-States-COVID-19-Cases-and-Deaths-by-State-o/9mfq-cb36>
-   <https://data.cdc.gov/Vaccinations/COVID-19-Vaccinations-in-the-United-States-Jurisdi/unsk-b7fc>
