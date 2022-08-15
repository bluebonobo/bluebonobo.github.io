---
layout: post
title:  "Coursera JHU Data Science Capstone Application "
date:   2022-08-11 23:00:00 -0400
categories: setup
---
The Coursera Johns Hopkins Data Science specialization consists of 9 courses followed by a capstone project. I describe here my journey, the process, resources, artefacts and submission for the capstone project. See details [here](https://www.coursera.org/learn/data-science-project)


## Application  
The [Shiny Application](https://bluebonobo.shinyapps.io/CapstoneProjectShinyApp/) developed for the Capstone assignment predicts the next word in a sentence. The application is written in R using Shiny framework. The application is deplopyed on the ShinyApp.io 

The user enters a series of word and the model predicts the next word using a Natural Language Statistical Model. The user interface is shown below. A documentation tab presents the content also available in this presentation

The application is deployed on ShinyApp.io, a Shiny application hosting service provided by RStudio. Note that in order to deploy the application on ShinyApps.io using a free subscription, I had to reduce the size of the ngrams files. To do so I built the ngrams files based on a sample corpus as the full ngrams files would create a out of memory error when running on ShinyApps.io. This error is widely reported in the forums and most students worked around this by using sample corpus. The complete .rds ngrams files can be found in my [github repository](https://github.com/bluebonobo/coursera_hopkins_capstoneproject)


**screenshot homepage** ![home](https://raw.githubusercontent.com/bluebonobo/coursera_hopkins_capstoneproject/main/shinyapp/CapstoneShinyApp/WWW/homepage.png){:class="img-responsive" :width="25%"}

## The Presentation

The slidify presentation required for the project completion can be found in Rpubs [here](https://rpubs.com/bluebonobo/capstoneproject)
