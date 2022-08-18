---
layout: post
title:  "Coursera JHU Data Science Developing Data Products"
date:   2022-06-11 09:30:00 -0400
categories: R
---

In this course, we are looking at ways and formats available to present data science analysis and presentations. These are refered to as Data Products. The course exclusively uses the R language and R Studio plateform. Additionaly, We also describe how python and jupyter are used to produce data products

>A data product is the production output from a statistical analysis. Data products automate complex analysis tasks or use technology to expand the utility of a data informed model, algorithm or inference. This course covers the basics of creating data products using Shiny, R packages, and interactive graphics. The course will focus on the fundamentals of creating a data product that can be used to tell a story about data to a mass audience.

## Assignement and deliverable

The course can be found [here](https://www.coursera.org/learn/data-products). The shiny application developed can be found [here](https://bluebonobo.shinyapps.io/week4shinyapp/). It is hosted by RStudio on shinyapps.io

Course content 

1. Shiny, rCharts, manipulate, googleVis 
2. Presenting data analysis, slidify, R Studio presenter. 
3. Students creating and deploying their projects 
4. Creating R packages, classes and methods.

## Developing with R

I have used [RStudio](www.rstudio.com) to develop and run and publish R artifacts. 

### Knitr
knitr is an engine for dynamic report generation with R. It is a package in the programming language R that enables integration of R code into Pdf, LaTeX, LyX, HTML, Markdown, AsciiDoc, and reStructuredText documents. The purpose of knitr is to allow reproducible research in R through the means of literate programming. It is similar in purpose and funtion to Jupyter

Knitr-generated HTML can be published in Github and set as Github Pages for rendered/public access. and Jekyll for public blog

### Shiny Application
Building a Shiny Appication

### Slidify
Hosting/publishing presentations on RPubs



## Developing with Pyhton

### Locally
I found that installing Jupyter Extension on VSCode and running the notebook directly on VSCode is appropriate

[Jupyter Notebook](www.jupyter.org): The Classic Notebook Interface. The Jupyter Notebook is the original web application for creating and sharing computational documents. It offers a simple, streamlined, document-centric experience. IDE runs locally and generates ipynb files. VSCode Jupyter extensions can also execute this


### Sharing

[Github](www.github.com) and [Nbviewer](www.nbviewer.org) : A simple way to share Jupyter Notebooks. Enter the location of a Jupyter Notebook to have it rendered here. This can be used to render a ipynb shared on Github for example (this way to share ipynb is a popular way to share/render ipynb work)


[Colaboratory](https://colab.research.google.com/) in browser Python from Google
With Colab you can harness the full power of popular Python libraries to analyze and visualize data. The code cell below uses numpy to generate some random data, and uses matplotlib to visualize it. To edit the code, just click the cell and start editing.
With Colab you can import an image dataset, train an image classifier on it, and evaluate the model, all in just a few lines of code. Colab notebooks execute code on Google's cloud servers, meaning you can leverage the power of Google hardware, including GPUs and TPUs, regardless of the power of your machine. All you need is a browser.

