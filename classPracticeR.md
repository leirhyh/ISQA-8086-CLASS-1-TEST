---
title: "DataViz - Data Foundations-Analysis and Statistics"
author: "Sachin Pawaskar"
date: "9/5/2017"
output:
  pdf_document: default
  html_document: default
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

# Data Foundations

## Data Preprocessing
In many circumstances, it is preferable to view the original raw data. In many domains, such as medical imaging, the data analyst is often opposed to any sort of data modifications, such as filtering or smoothing.

Why?
* For fear that important information will be lost or
* Deceptive artifacts may be added

Viewing raw data often identifies problems with the dataset, such as missing data, or outliers. But, Depending on the type of data and the visualization techniques to be applied, some form of pre-processing might be necessary.

## MetaData and Statistics
Information regarding a dataset of interest (its metadata) and statistical analysis can provide invaluable guidance in preprocessing the data.
* Helps with interpretation of formats of fields.
* May contain base reference point for some field.
* Unit of measurement.
* Symbol or Number used to denote missing values.
* Resolutions at which measurements were acquired.

Knowing this is important in selection the appropriate preprocessing operations and setting of parameters.

Statistical analysis can provide us with useful insights.
* Outlier Detection - may indicate erroneous data.
* Cluster analysis - can help segment the data into groups exhibiting strong similarities.
* Correlation Analysis - can help users eliminate redundant fields or highlight associations that might not have been apparent otherwise.

Common statistics about data
* Mean, and
* Standard Deviation

The most commonly used statistical plot in the distribution of data is?
* Histogram

```{r stat-mean-median-summary}
x <- rnorm (50)
y <- x + rnorm (50, mean=0, sd=0.5)
data <- as.data.frame(cbind(x,y))

mean(x)
median(x)
min(x)
max(x)
range(x)

summary(data)

```

## Including Plots

You can also embed plots, for example:

```{r plot-summary}

library(ggplot2)
ggplot(data, aes(x=x, y=y)) + geom_point(size=2)+theme(axis.text=element_text(size=12), axis.title=element_text(size=14), plot.title=element_text(size=20, face="bolde"))


