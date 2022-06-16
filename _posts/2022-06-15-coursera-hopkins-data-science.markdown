---
layout: post
title:  "Coursera Johns Hopkins Data Science Capstone"
date:   2022-06-15 21:30:00 -0400
categories: setup
---
The Coursera Johns Hopkins Data Science specialization consists of 10 courses followed by a capstone project. I describe here the process, resources, artefacts and submission for this project. See details [here](https://www.coursera.org/learn/data-science-project)

## Few words about the Capstone project   
In partnership with a corporate partner Swiftkey, the goal is to build a smart keyboard that makes it easier for people to type. One cornerstone of their smart keyboard is predictive text models (equivalent to autofill for next word). Developing basic understanding of Natural Language processing and Text Mining is required

## Familiarization with NLP
As a first step toward working on this project, you should familiarize yourself with Natural Language Processing, Text Mining, and the associated tools in R. 

### Natural Language Processing Wikipedia Page
*review of the [wikipedia page](https://en.wikipedia.org/wiki/Natural_language_processing)*   
Natural language processing (NLP) is a subfield of linguistics, computer science, and artificial intelligence concerned with the interactions between computers and human language, in particular how to program computers to process and analyze large amounts of natural language data. The goal is a computer capable of "understanding" the contents of documents, including the contextual nuances of the language within them. The technology can then accurately extract information and insights contained in the documents as well as categorize and organize the documents themselves.

Challenges in natural language processing frequently involve speech recognition, natural-language understanding, and natural-language generation.

History of NLP : Symbolic NLP (1950-1990) (rule based), Statistical NLP (1990-2000), Neural NLP (2010-present)


### Text Mining
*review of the [text mining in R](https://www.jstatsoft.org/article/view/v025i05)*
THis paper present the tm package which provides a framework for text mining applications within R. 

Preprocessing
1. Data import
2. Stemming : the process of erasing word suffixes to retrieve their radicals. It is a common technique used in text mining research, as it reduces complexity without any severe loss of information for typical applications (especially for bag-of-words).  
3. Whitespace elimination : the removal of white space and the conversion to lower case. For both tasks tm provides transformations
4. Stop Word removal : Stopwords are words that are so common in a language that their information value is almost zero, in other words their entropy is very low. Therefore it is usual to remove them before further analysis. 

Applications
1. Count based evluation
2. Simple text clustering
3. Simple text classification


### CRAN Text Processing resources
*revidew of the [CRAN resources](https://cran.r-project.org/web/views/NaturalLanguageProcessing.html)*

### how to load the dataset in R?


### Questions to consider

1. What do the data look like?
2. Where do the data come from?
3. Can you think of any other data sources that might help you in this project?
4. What are the common steps in natural language processing?
5. What are some common issues in the analysis of text data?
6. What is the relationship between NLP and the concepts you have learned in the Specialization?


## Understanding the problem
We download the capstone dataset which consists of 3 text files containing respectively tweats, blogs and news text. The dataset covers 4 languages : English, Russian, Finish and German. Size of the dataset is around 600MB
