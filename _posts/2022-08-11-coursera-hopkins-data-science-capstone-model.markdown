---
layout: post
title:  "Coursera JHU Data Science Capstone Models"
date:   2022-08-11 15:00:00 -0400
categories: setup
---
The Coursera Johns Hopkins Data Science specialization consists of 9 courses followed by a capstone project. I describe here my journey, the process, resources, artefacts and submission for the capstone project. See details [here](https://www.coursera.org/learn/data-science-project)

This page presents the model used to deliver the Next Word Application

## NGrams and Backoff strategy

*What are Ngrams : fan n-gram is a contiguous sequence of n items from a given sample of text or speech.*

*What is the backoff strategy : an n-gram is a contiguous sequence of n items from a given sample of text or speech.*

For each file in the english language (blogs, news and twitter), we build a VCorpus object, we clean the VCorpus by removing whitepaces, convert all to lower case, remove English stop words, remove punctuation, remove numbers, remove profanity and stem. We then tokenzie and finally create a DocumentTermMatrix.

We show the top 10 words and a wordcloud for each file below.

### Application - do new page here. another update
The Sample Blogs file we are going to analyze consists of **899288** lines and **364816** terms.

[Shiny Application](https://bluebonobo.shinyapps.io/CapstoneProjectShinyApp/){:class="img-responsive" :width="25%"}

### The Presentation

The pitch presentation can be found in Rpubs .
[here](https://rpubs.com/bluebonobo/capstoneproject){:class="img-responsive" :width="25%"}

