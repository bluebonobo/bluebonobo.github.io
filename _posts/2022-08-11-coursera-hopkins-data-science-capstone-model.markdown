---
layout: post
title:  "Coursera JHU Data Science Capstone Model and Algorithm"
date:   2022-08-11 15:00:00 -0400
categories: setup
---

This page presents the model used to deliver the Next Word Application

## NGrams and Backoff strategy

*What are Ngrams : fan n-gram is a contiguous sequence of n items from a given sample of text or speech.*

*What is the backoff strategy : an n-gram is a contiguous sequence of n items from a given sample of text or speech.*

For each file in the english language (blogs, news and twitter), we build a VCorpus object, we clean the VCorpus by removing whitepaces, convert all to lower case, remove English stop words, remove punctuation, remove numbers, remove profanity and stem. We then tokenzie and finally create a DocumentTermMatrix.

To build the model, we use a corpus of blogs, news and twitter entires provided as part of the assignment.

We have cleaned up the blogs, news and twitter entries to remove stop words, profanity

## The Model 

The text resources are loaded in a VCorpus object which is then tokenized. We tokenize the corpus in bigrams, trigrams and 4grams
We then build a DocumentTerm Matrix and calculate frequencies of each gram
The model is statistical based on a n-grams approach see this article or this article

Useful readings on ngrams model can be found in [this article](https://towardsai.net/p/nlp/how-do-language-models-predict-the-next-word) and [this article2](https://towardsdatascience.com/sentence-generation-with-n-gram-21a5eef36a1b)

## The Algorithm

Given the number of words in the input text, we look up the most frequent bigram, trigram or 4gram.
If the ngram lookup does not return a match, we call the (n-1)gram lookup. This strategy is refered to as backoff. Meaning the highest order ngram lookup is called and if no match is identified, the algorithm backs off to the next lower order ngram and so on.