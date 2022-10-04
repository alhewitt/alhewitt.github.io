---
title: "Machine Learning"
date: 2022-08-28
last_modified_at: 2022-10-04
permalink: /machine-learning/
categories:
  - PhD
  - Machine Learning
tags:
  - Lancaster
  - Machine Learning
  - Kaggle
  - Unfinished
toc: true
toc_sticky: true
toc_item: 
---

While looking at internships that I might find interesting to do during my PhD, I found several which involved machine learning. This was something I had attended talks and [workshops](https://astrostatistics.psu.edu/su21/index.html) on before but never really considered having a proper go at. I decided to start learning, choosing to focus on implementation rather than theory to begin with. This page shows my journey into the wonderful world of machine learning.

## [Iris](https://github.com/alhewitt/backup-website/blob/main/Iris/Iris.ipynb)
My first project is supposedly the "Hello World!" of machine learning. Following the walkthrough [here](https://machinelearningmastery.com/machine-learning-in-python-step-by-step/), I trained several algorithms on a dataset containing Iris flower characteristic and species using stratified 10-fold cross validation. Then, the best algorithm (chosen using precision) was tested using a 20% slice of the original dataset which had been withheld from it during training. The result is the SVM (Support Vector Machines) algorithm with an accuracy of 0.97.

## [Keras](https://github.com/alhewitt/backup-website/blob/main/Keras/Keras.ipynb)
My second project is an introduction to deep machine learning. It follows the walkthrough [here](https://machinelearningmastery.com/tutorial-first-neural-network-python-keras/). It focuses on using Keras which wraps the libraries Theano and TensorFlow. In this project, a deep neural network is trained to predict whether Pima people will have an onset of diabetes in 5 years using numerical medical information. A 4 layer sequential model is used. The input (8 nodes) and 2 hidden layers (12 and 8 nodes) use rectified linear unitactivation functions (ReLU) while the output layer uses a sigmoid function (1 node). For the loss function binary cross-entropy is used and adam is chosen for the optimiser. The result is an model with a ~77% accuracy rate. 

## Moving on to [Kaggle](https://www.kaggle.com/amyhewitt/code)
At this point I became aware of Kaggle, which hosts machine learning competitions and courses. On top of this, you can run code directly on their website which means I can change device without issues.

### [COURSE: Intro to Machine Learning](https://www.kaggle.com/learn/intro-to-machine-learning)
I began by following the first course, Intro to Machine Learning. This tutorial walks you through using decision trees to model the price of a house based off various factors. It covers overfitting and how the maximum number of leaf nodes affects things, then introduces random forest as a method of reducing MAE (mean absolute error). In the end, my results are submitted to the competition where they recieved a score of 21217.91640 (MAE). The notebook which was submitted can be found [here](https://github.com/alhewitt/alhewitt.github.io/blob/main/Kaggle/Intro_to_Machine_Learning.ipynb). To see the certificate of completion, [click here]()

### [Titanic](https://www.kaggle.com/competitions/titanic/overview)
I then decided to attempt uploading to a competition from scratch. I chose the titanic competition as it is very beginner friendly and has plenty of guides. After reading through a few attempts made by other people, I gave it a go. The competition involves predicting whether passengers died or survived based on various information like their name, ticket fare, class, age, whether they had other family on board etc. There were several missing variables which I tried to fill in rather than delete rows as there wasn't a huge amount of data to start with. 

Here are some of the methods I used to fill missing values:
 - The cabin has a lot of missing values and there are several missing ages. I will remove the cabin column since it is unlikely to be very informative with the majority of data being missing.
- Due to the "women and children first" order, the age may be very informative and so I did not want to remove it completely. I used averages for each title (Mr, Mrs, Miss etc) to fill in the missing ages.
- The ticket number was be dropped as it is not informative. Cabin was majority empty values so was deleted.
- For Embarked, I filled in the missing data using the price of the type of ticket purchased.
- And for the missing fare, I filled in the data using the ticket type and place of embarkment.

I then tested various models and found that a Random Forest Classifier produced the best results with an accuracy of 0.844 on the train data (cross validation: 0.861, 0.722, 0.833, 0.833, 0.886). My model's predictions on the test data produced a score of 0.75837 when submitted to the competition. This corresponds to the top 84%. I look forward to coming back to this project after learning more and seeing how much I can improve.

A copy of the submitted notebook can be found on [Kaggle](https://www.kaggle.com/code/amyhewitt/titanic-machine-learning-from-disaster/).

### [COURSE: Intro to Deep Learning](https://www.kaggle.com/learn/intro-to-deep-learning)
This was mostly a refresher and a more in-depth look into deep learning than my [Keras](https://alhewitt.github.io/machine-learning/#keras) project above. It covered the structure of DL networks, how to use Tensorflow, early stopping, special layers such as dropout and batch normalisation, and cross-entropy. Here are (brief) summaries on each of the above terms:
  - **Deep Learning networks**: A series of hidden layers in which the program can change the weights and biases in order to improve according to a given loss function.
  - **Early stopping**: Used to prevent a model from overfitting (where the loss on the training dataset decreases but the validation loss does not/rises. It looks at the loss over time for the validation dataset. If there is not an improvement (`min_delta`) for a certain number of epochs (`patience`) it will go back to the model with the weights with the best validation loss.
  - **Dropout layer**: Another tool in the arsenal against overfitting. This removes (drops out) a fraction (`rate`) of the input units for a layer. This is a similar effect to random forest. It was like multiple smaller networks all working together to find paterns opposed to one larger one.
  - **Batch normalisation**: This can be used on slow or unstable training. It normalises the batch to have a mean of 0 and standard deviation of 1.
  - **Cross entropy**: A type of loss function that can be used for binary data (yes or no). It converts from real values to a continuous probability.

### [COURSE: Computer Vision](https://www.kaggle.com/learn/computer-vision)
This was something I was very excited to learn as I had seen examples before and had always found them incredibly impressive. Here are summaries of the terms I learnt during this course:
  - **Convolutional base**: Made up of mostly convolutional layers which extract the features (i.e. colour, shape) of the image.
  - **Dense head**: Usually made up of dense layers which determine the class of the image (i.e. what the image is of).
  - **Transfer learning**: Reusing an already trained model rather than building one from scratch.
  - **Feature extraction**:
    -  First, filter the image for a specific feature (convolution layer),
    -  then detect that feature within the filtered image (ReLU),
    -  finally condense the image to enchance the feature (maximum pooling).
  -  **Convolution**: Mathematically, convolution is an integral that expresses the amount of overlap of one function (kernel) as it is shifted over another function. In ML, it is similar, but the kernel is the weights.  
  - **Feature map**: The result of the application of the filter.
  - **Maximum pooling**: Looks at batches of activations (pixels) and replaces with the maximum in that batch (one big pixel of the maximum brightness). This has the positive effect of increasing the ratio of useful pixels to less useful zero pixels. Also, since this reduces the size of the images, more can be produced.
  - **Translation invariance**: When maximum pooling is applied repeatedly to an image, features close together can get lost (merged together) while features far apart stay independent. This can be useful when there might be differences in perspective or framing.
  - **Global average pooling**: Used as an alternative to some dense layers in the head. Converts from 2D data to the 1D needed by the classifier by replacing each feature map with its global average.
  - **Stride**: How far should the window (kernel) move at each step. This is usually 1 in the case of convolution layers so pixels are not skipped, but it is usually set higher for maximum pooling.
  - **Padding**: How edge pixels should be handled. 
    -  Setting `padding='same'` puts zeros around the border of the input so that the output is the same size.
    -  Setting `padding='valid'` means the convolution window stays entirely within the input, however the output will be smaller.
  -  **Data augmentation**: It is always good to train your model on as much data as possible. By rotating and/or adjusting the colour/contrast of images, you can create additional, fake data.
