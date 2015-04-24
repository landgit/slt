---
title       : course project
subtitle    : predict car's fuel efficiency 
author      : Land
job         : please use right or left arrow key to nevigate these slides.
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Predictive the fuel efficiency of your car

* Fuel efficiency is one of features that we consider when we buying a car.

* Here, we define the fuel efficiency as “Miles/ gallon”.

* we develop the predicting model by use the data "mtcars"


```r
head(mtcars)
```

```
##                    mpg cyl disp  hp drat    wt  qsec vs am gear carb
## Mazda RX4         21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
## Mazda RX4 Wag     21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
## Datsun 710        22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
## Hornet 4 Drive    21.4   6  258 110 3.08 3.215 19.44  1  0    3    1
## Hornet Sportabout 18.7   8  360 175 3.15 3.440 17.02  0  0    3    2
## Valiant           18.1   6  225 105 2.76 3.460 20.22  1  0    3    1
```

--- .class #id 

## Building Linear Regression Model

* We choose 2 features, type of transmission and 1/4 mile time as predictors.

* The “Miles/ gallon” is our outcome. 

* Use simple linear regression

* R code:

```r
fit2 <- lm(mpg ~ factor(am) + qsec, mtcars)
```

---

## Result




```r
summary(fit2)$coefficients
```

```
##               Estimate Std. Error   t value     Pr(>|t|)
## (Intercept) -18.889281  6.5969729 -2.863326 7.710583e-03
## factor(am)1   8.876331  1.2896638  6.882670 1.461462e-07
## qsec          1.981870  0.3601293  5.503218 6.270759e-06
```

So our prediction model will be:

* If the transmission of the car is automatic:
-18.88 + 1.98 * 1/4 mile time

* If the trans mission of the car is manual:
-18.88 + 8.87 + 1.98 * 1/4 mile time  

*you can find the app here:
[https://land.shinyapps.io/car-app/](https://land.shinyapps.io/car-app/)

---
## Reference

Henderson and Velleman (1981), Building multiple regression models interactively. Biometrics, 37, 391–411.


