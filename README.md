# machine-learning
This repository contains my first attempts at doing small machine learning projects in order to get familiar with it.

## Iris
My first project is supposedly the "Hello World!" of machine learning. Following the walkthrough [here](https://machinelearningmastery.com/machine-learning-in-python-step-by-step/), I trained several algorithms on a dataset containing Iris flower characteristic and species using stratified 10-fold cross validation. Then, the best algorithm (chosen using precision) was tested using a 20% slice of the original dataset which had been withheld from it during training. The result is the SVM (Support Vector Machines) algorithm with an accuracy of 0.97.

## Keras
My second project is an introduction to deep machine learning. It follows the walkthrough [here](https://machinelearningmastery.com/tutorial-first-neural-network-python-keras/). It focuses on using Keras which wraps the libraries Theano and TensorFlow. In this project, a deep neural network is trained to predict whether Pima people will have an onset of diabetes in 5 years using numerical medical information. A 4 layer sequential model is used. The input (8 nodes) and 2 hidden layers (12 and 8 nodes) use rectified linear unitactivation functions (ReLU) while the output layer uses a sigmoid function (1 node). For the loss function binary cross-entropy is used and adam is chosen for the optimiser. The result is an model with a ~77% accuracy rate. 
