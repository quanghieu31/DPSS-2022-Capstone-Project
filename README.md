# DPSS 2022 Capstone Project: Analyze international policies

![UChicago Harris](https://github.com/wang8063/DPSS_Summer_Capstone/blob/master/IMAGES/DPSS.png)
  
  This project is based on the an R package dataset (unvotes). In this capstone project you will be working with the package called unvotes. It contains the voting history of countries in the United Nations General Assembly, along with information such as date, description, and topics for each vote. It was put together by David Robinson and you can go to this [webpage](https://cran.r-project.org/web/packages/unvotes/unvotes.pdf) to get more information about it.
  
  The creator responsible for assembling, cleaning, analyzing, and making this dataset public available was the researcher Erik Voeten ([more information](https://dataverse.harvard.edu/dataset.xhtml?persistentId=hdl:1902.1/12379)
  
  This project used three datasets from the unvotes package: 
  • ‘un_votes’: this dataset contains information on the voting history of the United Nations General Assembly. Contains one row for each country-vote pair;
• ‘un_roll_calls’: this dataset contains information on each roll call vote of the United Nations General Assembly;
• ‘un_roll_call_issues’: this dataset contains the issue (topic) classifications of roll call votes of the United Nations General Assembly. Many votes had no topic, and some have more than one.

## Background and information on UN Resolutions:

  A United Nations General Assembly Resolution is a decision or declaration voted on by all member states of the United Nations in the General Assembly. For instance, [here](https://www.un.org/securitycouncil/content/resolutions-adopted-security-council-2015) you can find the UN resolutions for 2015. The debate of an agenda at the UN is usually followed by the adoption of these resolutions. However, the voting session of such resolutions are done electronically by roll-call (countries can vote ‘yes’, ‘no’ and ‘abstain’). Thus, the voting normally reflects the degree of intergovernmental agreement and the state of global cooperation on a given topic.

## Main Purpose 
  
  Using R programming to
  • (i) visually explore the dataset so we can have a better understanding of what is the most disputed issue in the UN in the 21st century and which countries seem to have the strongest agreement/disagreement on such issue;
  • (ii) analyze if and how countries voting pattern are affected for environmental issues.

## Outline

  - Set up the environment
  - Exploratory Data Analysis
  - General plots
  - Affirmative voting intention among the UN Security Council versus the World
  - Issues that are dividing opinions in the UN
  - Regression analysis


## Environment

Coded in RStudio 4.2.1.

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
library(tidyverse)
library(unvotes)
library(dplyr)
library(ggplot2)
library(widyr)
library(broom)
library("mfx")
library(plm) 
library(gridExtra)
```

## Exploratory Data Analysis

  How many votes are there by each attribute?
  
  ![Table 1](https://github.com/quanghieu31/DPSS_2022_CapstoneProject/blob/main/images/eda1.png)
  
  Note that we are only examining countries that have voted more than 100 times. Now, let's see which countries are among the top ten (10) with a higher share of 'yes' votes and which are among the bottom ten (10). 
  
  ![Figure 1](https://github.com/quanghieu31/DPSS_2022_CapstoneProject/blob/main/images/top-10-and-bottom-10-countries-that-voted-yes.png)
  
  
  
  


