---
title: 'Mueller Report Volume 1'
author: 'weiss'
date: '2019-07-07'
slug: 'mueller-report-volume-1'
categories: ['R']
tags: ['R']
---



## R Markdown

This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.

When you click the **Knit** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:


```r
load('/users/sweiss/src/mueller_report/data/mueller_plots.rdata')
plot(campaign_members_by_group)
```

![plot of chunk cars](figure/cars-1.png)

```r
plot(mueller_network)
```

![plot of chunk cars](figure/cars-2.png)

```r
plot(ts_relations_plot)
```

![plot of chunk cars](figure/cars-3.png)

```r
plot(russian_network)
```

![plot of chunk cars](figure/cars-4.png)

## Including Plots
