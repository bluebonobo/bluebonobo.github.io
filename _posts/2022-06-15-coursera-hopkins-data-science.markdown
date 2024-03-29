---
layout: post
title:  "Coursera JHU Data Science Capstone Introduction"
date:   2022-06-15 21:30:00 -0400
categories: setup
---
The Coursera Johns Hopkins Data Science specialization consists of 9 courses followed by a capstone project. I describe here my journey, the process, resources, artefacts and submission for the capstone project. See details [here](https://www.coursera.org/learn/data-science-project)

In partnership with a corporate partner Swiftkey, the goal of the Capstone project is to build a smart keyboard that makes it easier for people to type. One cornerstone of their smart keyboard is predictive text models (equivalent to autofill for next word). Developing basic understanding of Natural Language processing and Text Mining is required

## TASK 0 : Understanding the problem

>Familiarization with NLP : As a first step toward working on this project, we familiarize ourselves with Natural Language Processing, Text Mining, and the associated tools in R. 

### Natural Language Processing Wikipedia Page
*review of the [wikipedia page](https://en.wikipedia.org/wiki/Natural_language_processing)*   
>Natural language processing (NLP) is a subfield of linguistics, computer science, and artificial intelligence concerned with the interactions between computers and human language, in particular how to program computers to process and analyze large amounts of natural language data. The goal is a computer capable of "understanding" the contents of documents, including the contextual nuances of the language within them. The technology can then accurately extract information and insights contained in the documents as well as categorize and organize the documents themselves.

>Challenges in natural language processing frequently involve speech recognition, natural-language understanding, and natural-language generation.

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

### Questions to consider

1. What do the data look like?   
The dataset is organized in 4 folders (1 folder per language), each folder contains 3 files of text (.txt extension). Each file has a different media source (blog, news and twitter). Each file is around 75Mb.

2. Where do the data come from?   
The corpora are collected from publicly available sources by a web crawler. The crawler checks for language, so as to mainly get texts consisting of the desired language. Once the raw corpus has been collected, it is parsed further, to remove duplicate entries and split into individual lines. Approximately 50% of each entry is then deleted. 

3. Can you think of any other data sources that might help you in this project?   
I think that additional social media sources would benefit this project by introducing less formal language. I especially think that Reddit corpus. I would also add a corpus of public domain books. I would also add exommerce product reviews.

4. What are the common steps in natural language processing?   
>The five phases of NLP involve lexical (structure) analysis, syntactic analysis (parsing), semantic analysis (meaning), discourse integration, and pragmatic analysis. S

5. What are some common issues in the analysis of text data? 
- Contextual words and phrases and homonyms
- Synonyms
- Irony and sarcasm
- Ambiguity
- Errors in text or speech
- Colloquialisms and slang
- Domain-specific language
- Low-resource languages   

6. What is the relationship between NLP and the concepts you have learned in the Specialization? 
Since the 80s, NLP has been relying on Statistical Methods, Machine Learning and Neural Network which are part of Data Science. Exploratory analkysis, intference, data products and practical Machine Learning concepts and courses of the specialization will be directly applied to the NLP capstone project.  

7. how to load the dataset in R?



## TASK 1 : Getting and Cleaning the data

>Tasks to accomplish
>1. Tokenization - identifying appropriate tokens such as words, punctuation, and numbers. Writing a function that takes a file as input and returns a tokenized version of it.   
>2. Profanity filtering - removing profanity and other words you do not want to predict.





