---
layout: default
title: Machine Learning
rank: 3
---

# Machine Learning
While looking at internships that I might find interesting to do during my PhD, I found several which involved machine learning. This was something I had attended talks and [workshops](https://astrostatistics.psu.edu/su21/index.html) on before but never really considered having a proper go at. I decided to start learning, choosing to focus on implementation rather than theory to begin with. This page shows my journey into the wonderful world of machine learning.

## [Iris](https://github.com/alhewitt/alhewitt.github.io/blob/main/Iris/Iris.ipynb)
My first project is supposedly the "Hello World!" of machine learning. Following the walkthrough [here](https://machinelearningmastery.com/machine-learning-in-python-step-by-step/), I trained several algorithms on a dataset containing Iris flower characteristic and species using stratified 10-fold cross validation. Then, the best algorithm (chosen using precision) was tested using a 20% slice of the original dataset which had been withheld from it during training. The result is the SVM (Support Vector Machines) algorithm with an accuracy of 0.97.

## [Keras](https://github.com/alhewitt/alhewitt.github.io/blob/main/Keras/Keras.ipynb)
My second project is an introduction to deep machine learning. It follows the walkthrough [here](https://machinelearningmastery.com/tutorial-first-neural-network-python-keras/). It focuses on using Keras which wraps the libraries Theano and TensorFlow. In this project, a deep neural network is trained to predict whether Pima people will have an onset of diabetes in 5 years using numerical medical information. A 4 layer sequential model is used. The input (8 nodes) and 2 hidden layers (12 and 8 nodes) use rectified linear unitactivation functions (ReLU) while the output layer uses a sigmoid function (1 node). For the loss function binary cross-entropy is used and adam is chosen for the optimiser. The result is an model with a ~77% accuracy rate. 

## Moving on to [Kaggle](https://www.kaggle.com/amyhewitt/code)
At this point I became aware of Kaggle, which hosts machine learning competitions and courses. On top of this, you can run code directly on their website which means I can change device without issues.

### [Intro to Machine Learning](https://www.kaggle.com/learn/intro-to-machine-learning)
I began by following the first course, Intro to Machine Learning. This tutorial walks you through using decision trees to model the price of a house based off various factors. It covers overfitting and how the maximum number of leaf nodes affects things, then introduces random forest as a method of reducing MAE (mean absolute error). In the end, my results are submitted to the competition where they recieved a score of 21217.91640 (MAE). The notebook which was submitted can be found [here](https://github.com/alhewitt/alhewitt.github.io/blob/main/Kaggle/Intro_to_Machine_Learning.ipynb).

### [Titanic](https://www.kaggle.com/competitions/titanic/overview)
I then decided to attempt uploading to a competition from scratch. I chose the titanic competition as it is very beginner friendly and has plenty of guides. After reading through a few attempts made by other people, I gave it a go. The competition involves predicting whether passengers died or survived based on various information like their name, ticket fare, class, age, whether they had other family on board etc. There were several missing variables which I tried to fill in rather than delete rows as there wasn't a huge amount of data to start with. 

Here are some of the methods I used to fill missing values:
 - The cabin has a lot of missing values and there are several missing ages. I will remove the cabin column since it is unlikely to be very informative with the majority of data being missing.
- Due to the "women and children first" order, the age may be very informative and so I did not want to remove it completely. I used averages for each title (Mr, Mrs, Miss etc) to fill in the missing ages.
- The ticket number was be dropped as it is not informative. Cabin was majority empty values so was deleted.
- For Embarked, I filled in the missing data using the price of the type of ticket purchased.
- And for the missing fare, I filled in the data using the ticket type and place of embarkment.

I then tested various models and found that a Random Forest Classifier produced the best results with an accuracy of 0.844 on the train data (cross validation: 0.861, 0.722, 0.833, 0.833, 0.886). My model's predictions on the test data produced a score of 0.75837 when submitted to the competition. This corresponds to the top 84%. I look forward to coming back to this project after learning more and seeing how much I can improve.

A copy of the submitted notebook can be found on [GitHub](https://github.com/alhewitt/alhewitt.github.io/blob/main/Kaggle/titanic-machine-learning-from-disaster.ipynb) and on [Kaggle](https://www.kaggle.com/code/amyhewitt/titanic-machine-learning-from-disaster/).

[back](https://alhewitt.github.io/)
