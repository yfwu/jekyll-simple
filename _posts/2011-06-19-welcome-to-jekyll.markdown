---
layout: post
title:  "SQLflow"
date: 2020-06-19
categories: tools
---
SQL with built-in support of ML

[SQLFlow](https://sql-machine-learning.github.io/)

``` sql
SELECT * FROM iris.train 
TO TRAIN DNNClassifer 
WITH hidden_units = [10, 10], n_classes = 3, EPOCHS = 10 
COLUMN sepal_length, sepal_width, petal_length, petal_width LABEL class 
INTO sqlflow_models.my_dnn_model;
```