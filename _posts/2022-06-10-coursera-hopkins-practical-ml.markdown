---
layout: post
title:  "Coursera JHU Practical Machine Learning"
date:   2022-06-10 09:30:00 -0400
categories: setup
---

For the Practical Machine Learning course, the students were asked to analyze a dataset from the Quantified Self Movement. This is a classification problem where we are asked to assess whehter exercise measurment provided as test qualify for corret or incorrect execution of the exercise. Correct execution and different types of incorrect executions were provided to train models. 

My work can be found on [my Github account](https://bluebonobo.github.io/coursera_hopkins_practicalmachinelearning/)

To summarize the work : After exploring, visualizing and cleaning the data, I train 3 models suited for a classifiation problem (Decision Tree Model, Gradient Boost Model, and Tree Bag). I perform a kfold cross validation when training each model. After comparing the accuracy and confusion matrices for each model, the TreeBag model performs best and I decide to proceed to the predition part of the assignmnent using the Treebag model

The data for this project come from [this source](http://groupware.les.inf.puc-rio.br/har). At time of submiting the assignment this link is not working, I found [this link](https://perceptualui.org/publications/velloso13_ah.pdf) instead

I use the R [caret package](https://github.com/topepo/caret/) to split the data, train the models and predict the type of errors if any for a new set of exercise data. 
Caret stands for Classification And REgression Training. The package contains tools for:
- data splitting
- pre-processing
- feature selection
- model tuning using resampling
- variable importance estimation

I highly recommend reading this [introduction to Caret Package](https://cran.r-project.org/web/packages/caret/vignettes/caret.html)

#### Decision tree 
{% highlight r %}
    DTModel_Fit <- train(classe ~ ., method = "rpart", trControl = trainControl(method = "cv", number = 5, verboseIter = FALSE), data = training, na.action = na.pass)
    DTModel_Pred <- predict(DTModel_Fit, newdata = testing)
    DTModel_CM <- confusionMatrix(DTModel_Pred, as.factor(testing$classe))
{% endhighlight %}

#### Bagging tree bag
{% highlight r %}
    TreeBagModel_Fit <- train(classe ~ ., method = "treebag", trControl = trainControl(method = "cv", number = 5, verboseIter = FALSE), data = clean_data_training, na.action = na.pass)
    TreeBagModel_Pred <- predict(TreeBagModel_Fit, newdata = testing)
    TreeBagModel_CM <- confusionMatrix(TreeBagModel_Pred, as.factor(testing$classe))
{% endhighlight %}

#### Gradient boost
{% highlight r %}
    GBMModel_Fit <- train(classe ~ ., method = "gbm", trControl = trainControl(method = "cv", number = 5, verboseIter = FALSE), data = clean_data_training, na.action = na.pass)
    GBMModel_Pred <- predict(GBMModel_Fit, newdata = testing)
    GBMModel_CM <- confusionMatrix(GBMModel_Pred, as.factor(testing$classe))
{% endhighlight %}


