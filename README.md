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
  
  - (i) visually explore the dataset so we can have a better understanding of what is the most disputed issue in the UN in the 21st century and which countries seem to have the strongest agreement/disagreement on such issue;
  - (ii) analyze if and how countries voting pattern are affected for environmental issues.

## Outline

  - Set up the environment
  - Exploratory Data Analysis
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
  
  We can see that, on the Country-axis, for the top 10 countries from Seychelles to Belize, the percentages for "yes" votes were very large, above 90 percent. And But until about the threshold of 55 percent can we see other countries that were still considered likely to be agreeable in the voting sessions. This shows the likelihood of having countries with large share of votes for "yes" is high. Meanwhile, the bottom 10 countries were consisted of a mixture of agreeable and disagreeable countries. Again, this implies that there were not many countries that posed an opposition to a voting session. Note that, most of the disagreeable countries were powerhouse (France, United Kingdom, Federal Republic of Germany, and United States). 
  
  Now, we explore the percentage of 'yes' votes in the UN from 1946 to 2019, using a time series plot. 
  
  ![Figure 2](https://github.com/quanghieu31/DPSS_2022_CapstoneProject/blob/main/images/percentage-of-voting-yes-in-UN-_1946-2019.png)
  
## Look in more details (the UN issues and the countries in UNSC)

  The six "umbrella" issues that UN have covered the most since 1946.  
  
  ![Table 2](https://github.com/quanghieu31/DPSS_2022_CapstoneProject/blob/main/images/issues.png)
  
  [United Nations Security Council](https://www.un.org/securitycouncil/) holds the power to determine a possible threat to the peace or act of aggression. Basically, the Council can make any necessary call for peaceful means, recommendations, or adjustment of terms of settlement. The council is currently consisted of the United States, Unided Kingdom, France, China, and Russia. 
  
  Now, let's explore how these five countries in the UN Security Council have displayed their average percentage of 'yes' votes compared to each other, using *facet_wrap* function. 
  
  ![Figure 3](https://github.com/quanghieu31/DPSS_2022_CapstoneProject/blob/main/images/yes-among-UNSC.png)
  
  We might also want to compare these voting patterns to the world's average percentage of 'yes' votes (the "world" here contains the non-members of UN Security Council). 
  
  ![Figure 4](https://github.com/quanghieu31/DPSS_2022_CapstoneProject/blob/main/images/yes-among-UNSC-and-world.png)
  
## Disputed issues (take Russia as a baseline for comparison)

  We will look into the top 50 issues that have been dividing opinions the most in the UN in the 21st century. To evaluate the dividing issues, I created a column that take value of 1 when the vote was ‘yes’, a value of 0 when the vote was ‘abstain’, and a value of -1 when the vote was ‘no’. Then, I calculated the variance among these votes' numeric values (the higher variance, the higher dispute).  Note that the dataset was not perfect - there were missing values (NA). 
  
  ![Table 3](https://github.com/quanghieu31/DPSS_2022_CapstoneProject/blob/main/images/top50_disputed.png)
  
  Given the history of Russia, I think this country can be used to compare to other countries. In particular, I will analyze what country had a voting pattern opposite to Russia (based on the top 50 disputed topics). Here is a plot that shows how other countries' vote relates to Russia - top 10 countries with a higher share of correlation with Russia's pattern of voting for the top 50 disputed issues and bottom 10 countries as well.
  
  ![Figure 5](https://github.com/quanghieu31/DPSS_2022_CapstoneProject/blob/main/images/disputed-russia.png)
  
## Regression analysis  

  






