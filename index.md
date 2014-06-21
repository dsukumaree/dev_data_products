---
title       : Child Height Predictor
subtitle    : A Shiny App 
author      : Coursera
job         : Student
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
---

## Introduction

1. Most parents are curious to see how tall/short their child will be
2. Child Height Predictor app predicts child's height based on sex and mid-parental height
3. Simple and easy to use!

--- .class #id 

## Shiny App Interface

<iframe src = 'assets/img/screenshot.png' height='600px'></iframe>

--- 

## Prediction Algorithm

1. This height prediction is based on the sex adjusted midparental height and the methods below.
2. For girls: subtract 13 cm from the father's height and average with the mother's height.
3. For boys: add 13 cm to the mother's height and average with the father's height.
4. 13 cm is the average difference in height of women and men.
5. For both girls and boys, 8.5 cm on either side of this calculated value (target height) represents the 3rd to 97th percentiles for anticipated adult height.

[Reference](http://medcalc3000.com/HeightPotential.htm).

--- 

## Example

Example : Working it out in R


```r
## Mother's Height in cm
mHeight <- 150
## Father's Height in cm
fHeight <- 170
## child's sex: 1 for female and 2 for male
cSex <- 1
if (cSex == 1) cHeight <- ((fHeight - 13) + mHeight)/2  else  cHeight <- ((mHeight + 13) + fHeight)/2 
cHeight
```

```
## [1] 153.5
```

---
