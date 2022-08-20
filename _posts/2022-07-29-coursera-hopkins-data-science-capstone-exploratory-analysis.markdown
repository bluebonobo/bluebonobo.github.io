---
layout: post
title:  "Coursera JHU Data Science Capstone Exploratory Analysis"
date:   2022-07-29 15:00:00 -0400
categories: setup
---

In statistics, exploratory data analysis is an approach of analyzing data sets to summarize their main characteristics, often using statistical graphics and other data visualization methods. This page presents the results of the exploratory data analysis phase of the JHU Coursera Capstone project.

## Exploratory data analysis

For each file in the english language (blogs, news and twitter), we build a VCorpus object, we clean the VCorpus by removing whitepaces, convert all to lower case, remove English stop words, remove punctuation, remove numbers, remove profanity and stem. We then tokenzie and finally create a DocumentTermMatrix.

*full analysis has been posted on Rpubs [here](https://rpubs.com/bluebonobo/capstone_project_week2)*  


We show the top 10 words and a wordcloud for each file below.

### Blogs File Analysis
The Sample Blogs file we are going to analyze consists of **899288** lines and **364816** terms.

![top10Blogs](/assets/2022-07-29-coursera-hopkins-data-science-capstone-exploratory-analysis/top10BlogTerms.png){:class="img-responsive" :width="25%"}

### News File Analysis
The Sample Blogs file we are going to analyze consists of **1010242** lines and **271382** terms.
![top10News](/assets/2022-07-29-coursera-hopkins-data-science-capstone-exploratory-analysis/top10NewsTerms.png){:class="img-responsive" :width="25%"}

### Twitter File Analysis
The Sample Blogs file we are going to analyze consists of **2360148** lines and **388357** terms.
![top10Twitter](/assets/2022-07-29-coursera-hopkins-data-science-capstone-exploratory-analysis/top10TwitterTerms.png){:class="img-responsive" :width="25%"}



