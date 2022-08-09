# DPSS_2022_CapstoneProject

# DPSS_Summer_Capstone

![UChicago Harris](https://github.com/wang8063/DPSS_Summer_Capstone/blob/master/IMAGES/DPSS.png)
  
  This is the capstone of DPSS in 2019 about Hate Crime in USA which is designed by Daniel Snow

## Background:

  Recent years, according to the FBI or Justice Research and Statistics Association data published, we can see the hate crime rate is increasing and each year, across America, an average of 250,000 people are victimized by hate crimes – criminal expressions of bigotry that terrorize entire communities and fray the social fabric of our country. In order to figure out what is the most important feature in the hate crime and in what extend this feature influences the hate crime rate, we run multi linear regression from income equality, degree, race raio, religious, citizen and non- citizen ratio to build the regression model. As well as demographat and republican ratio and Jewish people.
  
  The purpose of making such a policy is to establish guidelines for identifying and investigating hate crimes and assisting victimized individuals and communities. A swift and strong response by law en- forcement can help stabilize and calm the city as well as aid in a victim’s recovery.

## Main Purpose 
  
  The following is the purpose of this capstone:

  In this Capstone Project, you will examine the potential causes/correlates of hate crimes in the United States. The goal is to replicate this analysis from FiveThirtyEight using updated hate crime data and additional regressors. Prior to starting your project, please read this Southern Poverty Law Center brief which provides background information on hate crimes and hate crime data collection in the United States.
  
  Data for this project will be collected the Kaiser Family Foundation, FBI, and U.S. Census. You will also need to gather two additional state-level metrics to include in your analysis (from any source).
  
In two pages, describe the nature of hate crime data in the United States, including how it is collected and its potential biases (1-2 paragraphs). Next, describe your findings from the tasks below (3-4 paragraphs). Clearly outline your regression specification and detail why you chose your two additional regressors. Suc- cinctly interpret your map as well, noting any geographic anomalies and their potential causes. Embed your regression table, map, and plot in your final memo.

In this project, you can expenct to see how I answer the following questions:

## Tasks:

* 1. loading data and combine the acs and all other variables

* 2. Create a regression incorporating each of your downloaded variables and think about do we need interaction terms? Fixed effects? Include the results of our regression as a nicely formatted table using stargazer.

* 3. Using state-level geographic data from the Census, create a map of hate crimes per 100k population. It should look close to the map in the original article, but with a different style/theme and with potentially different trends.

* 4. Create one additional non-map plot using your state-level data. Try to make something that is mean- ingful and visually striking. Here is where your choice of regressor can really have a large benefit.

* 5. using the FBI hate crimes website, gather the aggregate number of hate crimes for each year since 2008 and create a plot that displays the change in hate crimes per 100k over time.


### Environment

We will mainly use R studio and the version of R for this project is 3.6.0. And use the packages of tidyverse, tidycensus and ggplot

```{r include=FALSE, warning=FALSE, message=FALSE}
library(tm)
library(SnowballC)
library(wordcloud)
library(RColorBrewer)
library(tidyverse)
library(tidycensus)
library(stargazer)
library(ggplot2)
library(gganimate)
library(ggrepel)
library(reshape2)
```
