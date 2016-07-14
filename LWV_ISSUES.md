---
title: "LWV ISSUE"
author: "OLufemi Adesanya"
date: "July 13, 2016"
output: 
  html_document:
         keep_md: true
---
### Dataset Import and summary
```{r}
getwd()
LWData <-read.csv("LWV_Data.csv")
LWData1 <- data.frame(LWData)
LWPop <-LWData1[!is.na(LWData1$control),]
head(LWPop, 20)
summary(LWPop)

```
### The first 100 rows from the population shows that majority of the voters are old and non hispanic people. The popluation does not reflect sample representation of young and hispanc voters




### Descriptive statistics
```{r}
library(pastecs) #descriptive statistics package
options(scipen =  100) #change format display for descriptive statistics
options (digits = 2) #change format display for descriptive statistics
stat.desc(LWPop, basic = F) #Basic Descriptive statistics of the population
```
### This shows the count of old and young people included in the population. The result shows more old people constitute the population. 


### Counts of Population
```{r}
table(LWPop$Young.Hispanic.Status) #to do a count of young voters
table(LWPop$Young.Voter)  #sum of all young voter compared to old voters
table(LWPop$Voter.Category) #to do a count of young voter
table(LWPop$control) #sample population for control group
table(LWPop$post) #sample population for post group
table(LWPop$flyer) #sample population for flyer group
table(LWPop$VOTED2014) #number of people who voted from the population of 24000
```

### Here, we plotted the sample data and the whole data to compare our young and hispanic voters representation.The majority voters in the whole data are non young and non hispanic. This is not a representative of what the researcher will like to perform.

### Plot
```{r}
plot(LWPop$Young.Hispanic.Status) #Graphical representation to validate Sampling error for sample population
plot(LWData1$Young.Hispanic.Status) #Graphical representation of all population
```
