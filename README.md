# machine-learning
This repository contains my first attempts at doing small machine learning projects in order to get familiar with it.

## [Iris](Iris/Iris.ipynb)
My first project is supposedly the "Hello World!" of machine learning. Following the walkthrough [here](https://machinelearningmastery.com/machine-learning-in-python-step-by-step/), I trained several algorithms on a dataset containing Iris flower characteristic and species using stratified 10-fold cross validation. Then, the best algorithm (chosen using precision) was tested using a 20% slice of the original dataset which had been withheld from it during training. The result is the SVM (Support Vector Machines) algorithm with an accuracy of 0.97.

## [Keras](Keras/Keras.ipynb)
My second project is an introduction to deep machine learning. It follows the walkthrough [here](https://machinelearningmastery.com/tutorial-first-neural-network-python-keras/). It focuses on using Keras which wraps the libraries Theano and TensorFlow. In this project, a deep neural network is trained to predict whether Pima people will have an onset of diabetes in 5 years using numerical medical information. A 4 layer sequential model is used. The input (8 nodes) and 2 hidden layers (12 and 8 nodes) use rectified linear unitactivation functions (ReLU) while the output layer uses a sigmoid function (1 node). For the loss function binary cross-entropy is used and adam is chosen for the optimiser. The result is an model with a ~77% accuracy rate. 

## Moving on to [Kaggle](https://www.kaggle.com/amyhewitt/code)
At this point I became aware of Kaggle, which hosts machine learning competitions and courses. I began by following the first course, [Intro to Machine Learning](https://www.kaggle.com/learn/intro-to-machine-learning). This tutorial walks you through using decision trees to model the price of a house based off various factors. It covers overfitting and how the maximum number of leaf nodes affects things, then introduces random forest as a method of reducing MAE (mean absolute error). In the end, my results are submitted to the competition where they recieved a score of 21217.91640 (MAE). The notebook which was submitted can be found [here](Kaggle/Intro_to_Machine_learning.ipynb).
