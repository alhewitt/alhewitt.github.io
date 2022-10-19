---
title: "Machine Learning"
date: 2022-08-28
last_modified_at: 2022-10-19
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
header:
  teaser: /assets/img/ml/ml.jpg
  image: /assets/img/ml/ml_banner.jpg
  caption: "Photo credit: [Conny Schneider](https://unsplash.com/@choys_?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)"
---  

While looking at internships that I might find interesting to do during my PhD, I found several which involved machine learning. This was something I had attended talks and [workshops](https://astrostatistics.psu.edu/su21/index.html) on before but never really considered having a proper go at. I decided to start learning, choosing to focus on implementation rather than theory to begin with. This page shows my journey into the wonderful world of machine learning.

## [Iris](https://github.com/alhewitt/backup-website/blob/main/Iris/Iris.ipynb)
{% capture fig_img %}
![Foo]({{ "/assets/img/ml/iris.jpg" | relative_url }})
{% endcapture %}
<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
</figure>  


My first project is supposedly the "Hello World!" of machine learning. Following the walkthrough [here](https://machinelearningmastery.com/machine-learning-in-python-step-by-step/), I trained several algorithms on a dataset containing Iris flower characteristic and species using stratified 10-fold cross validation. Then, the best algorithm (chosen using precision) was tested using a 20% slice of the original dataset which had been withheld from it during training. The result is the SVM (Support Vector Machines) algorithm with an accuracy of 0.97.

## [Keras](https://github.com/alhewitt/backup-website/blob/main/Keras/Keras.ipynb)
My second project is an introduction to deep machine learning. It follows the walkthrough [here](https://machinelearningmastery.com/tutorial-first-neural-network-python-keras/). It focuses on using Keras which wraps the libraries Theano and TensorFlow. In this project, a deep neural network is trained to predict whether Pima people will have an onset of diabetes in 5 years using numerical medical information. A 4 layer sequential model is used. The input (8 nodes) and 2 hidden layers (12 and 8 nodes) use rectified linear unitactivation functions (ReLU) while the output layer uses a sigmoid function (1 node). For the loss function binary cross-entropy is used and adam is chosen for the optimiser. The result is an model with a ~77% accuracy rate. 

## Moving on to [Kaggle](https://www.kaggle.com/amyhewitt/code)
At this point I became aware of Kaggle, which hosts machine learning competitions and courses. On top of this, you can run code directly on their website which means I can change device without issues.

### [COURSE: Intro to Machine Learning](https://www.kaggle.com/learn/intro-to-machine-learning)
I began by following the first course, Intro to Machine Learning. This tutorial walks you through using decision trees to model the price of a house based off various factors. It covers overfitting and how the maximum number of leaf nodes effects things, then introduces random forest as a method of reducing MAE (mean absolute error). In the end, my results are submitted to the competition where they recieved a score of 21217.91640 (MAE). The notebook which was submitted can be found [here](https://github.com/alhewitt/alhewitt.github.io/blob/main/Kaggle/Intro_to_Machine_Learning.ipynb).

### [COMPETITION: Titanic](https://www.kaggle.com/competitions/titanic/overview)
{% capture fig_img %}
![Foo]({{ "/assets/img/ml/header_titanic.jpeg" | relative_url }})
{% endcapture %}
<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
</figure>
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


### [COMPETITION: Petals to the Metal](https://www.kaggle.com/competitions/tpu-getting-started)
{% capture fig_img %}
![Foo]({{ "/assets/img/ml/header_petals.png" | relative_url }})
{% endcapture %}
<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
</figure>
At the end of the [computer vision](https://alhewitt.github.io/machine-learning/#course-computer-vision) course, this competition was recommended. There was a notebook aready completed which could be forked and then edited to improve the score (initially 0.04265). My edited version, which was submitted to the competition, can be found [here](https://www.kaggle.com/code/amyhewitt/create-your-first-submission). 

Changes I made to improve the score:
  - Added stopper function
  - Changed pretrained model to Xception
  - Adjusted the training schedule
  - Added augmentation to the dataset (before it is fed to the model), however this slows it down too much so is not activated right now

The final score is 0.94012 which is 26th on the leaderboard (as of 05/10/2022).
{% capture fig_img %}
![Foo]({{ "/assets/img/ml/petal_score.png" | relative_url }})
{% endcapture %}
<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
</figure>
As of 18/10/2022, this submission has been awarded (my first) bronze medal.

### [COURSE: Intermediate Machine Learning](https://www.kaggle.com/learn/intermediate-machine-learning)
This course builds on the [introduction course](https://alhewitt.github.io/machine-learning/#course-intro-to-machine-learning). It covers how to prepare your data for modelling, how to clean up the code and methods for finding optimal parameters for the models. Here are some 

  - **Imputation**: Missing values must be dealt with somehow. Imputation means replaces those missing values with something like the mean or median of all the results etc. Sometimes it can be advantageous to add a new column which records whether inputation happened on that row.
  - **Categorical variable**: When the result of a variable can only be a set number of values, for example: agree, disagree, unsure. 
  - **Ordinal encoding**: The method of transforming catagotical variables into integer values for better interpretation by ML models.
  - **One-hot encoding**: Another method of dealing with catagorical variables is to give each response its own column filled with true and false values (1s and 0s).
  - **Cardinality**: The number of unique entries of a caragorical variable. Columns with high cardinality would need many new columns to be dealt with using the one-hot method, so often ordinal encoding is used, or they are just dropped. One-hot is usually used on columns with low cardinality.
  - **Pipeline**: Pipelines combine preprocessing and modelling steps together. They also make cross-validation easier to perform.
  - **Cross-validation**: Running the modelling process on seperate subsets of the data, using a seperate fraction as validation each time. This produces n measures of model quality. This is useful in particular in cases where there is a limited amount of data as it accounts for random effects from a chosen validation set.
  - **Ensemble methods**: A method which combines the result of multiple models, such as random forests where each forest is a model.
  - **Gradient boosting**: Gradient boosting will add more and more models to an ensemble in order to reduce loss. Gradient descent is used on the loss function to determine the new parameters, which is where the name comes from. The `XGBoost` library stands for extreme gradient boosting and can be used to implement it. Some important parameters are explained below:
    - `n_estimators` corresponds to the number of models to include usually 100-1000. 
    - `early_stopping_rounds` states how many cycles with no improvement are needed before it stops.
    - `learning_rate` is the value which the previous predictions are multiplied by before being added.
    - `n_jobs` allows for parallelisation on different cores.
  - **Data leakage**: When training data contains different information about the target than the data being used for predictions. This causes high performance on training sets but low scores in production. There are two main types:
    - **Target leakage**: Where data included in the original training data contains information which will not be available at the time predictions are made. For example, some information is changed over time and then the models are trained on the data after those changes are made, but when using the model to make predictions in real time, the information will not have been changed, and will look different to what the model trained on. To avoid this, any variable updated or created after the model was trained should not be used.
    - **Train-test contamination**: When the information used for validation effects the training process. An example is preprocessing on the whole data set and then splitting it into test and train.


### [COURSE: Time Series](https://www.kaggle.com/learn/time-series)
This course builds on the [Intermediate Machine Learning](https://alhewitt.github.io/machine-learning/#course-intermediate-machine-learning) course and covers using ML to predict changes over time, such as finantial forcasts. Below are summaries of terms this course covered.
  - **Linear regression**: Linear regression involves estimating a relationship between variables by fitting straight lines to them. The weights are sometimes called regression coefficients and the bias is called the intercept.
  - **Time-step features**: Features that can be derived directly from the time index. For example, a dummy variable which counts the time step. This would produce a linear fit with time on the x-axis.
  - **Lag features**: Shifting observations so the previous value is included in a new column. This produces a lag plot where observations are plotted against the previous observation.
  - **Serial dependence**: When an observation can be predicted from pervious observations. For example, when a system can effect itself.
  - **Trend**: A long-term change in the mean of a series. When adding as a column, the shape of the trend (once known) can be used to fit more than just straight lines. For example, if it is a quadratic, you can square the time dummy.
  - **Moving average**: A way to smooth out data points so that trends can be seen. It is done by taking a mean in a window around each data point. When used as a feature, should not be centred.
  - **Deterministic process**: A process which can be completely determined (not random).
  - **Splines**: An alternative to polynomials for fitting trends. Not very good for forcasting but can help show patterns and isolate them (detrending).
  - **Detrending**: Removing trends from data to keep it around 0.
  - **Seasonality**: When a time series changes in a periodic fashion.
  - **Indicators**: A feature for modelling seasonality where seasons are plotted on top of each other to identify the trend within the season. This is done by one-hotting (and dropping one). Useful for situations with fewer data points per season.
  - **Fourier features**: Fourier analysis in mathematics is a way of breaking down functions depending on space or time into functions depending on frequency by representing it as a sum of various sinusiodal waves. In ML it is useful for situations with lots of data points per season where one-hotting indicators would be impractical.
  - **Autocorrelation**: The correlation a time series has with its lags. Only measures linear dependence.
  - **Partial autocorrelation**: How much the correlation of a lag contributes once the effect of previous lags has been accounted for. When plotted as a correlogram, it can show which lags are helpful.
  - **Component**: A component of a time series is a term in the model which when all are combined, fits the time series.
  - **Residual**: The difference between the model prediction and the real data. They represent what the model failed to learn about the target. If the residuals contain only noise, the model is complete.
  - **Hybrid forcasting**: You can use one algorithm to fit the original time series and then another to fit the residual series. They would then be added to get the overall predictions. Predictions from one model can be used as a feature of another.
  - **Feature-transforming algorithms**: Algorithms which learn a function which takes a feature as an input and then performs operations to produce an output resembling target values. For example: linear regresion and neural networks. They can extrapolate target values beyond training set.
  - **Target-transforming algorithms**: Algorithms which use features to group and average values in the training set to make predictions. For example, decision trees and nearest neighbours.
  - **Forcast origin**: The time at which a forecast is made, or the last time for which training data is available.
  - **Forcast horizon**: The time for which a forcast is being made. It is often described in terms of how many time steps it is.
  - **Lead time**: The difference between the start of the forcast horizon and the origin due to the use of lag features.
  - **Multistep forcasting strategies**:
    - **Multioutput model**: Use a model which gives multiple outputs naturally like linear regression and neural networks.
    - **Direct strategy**: Train the model for each step in the forcast. One models one step ahead, the next models two steps ahead etc. This is helpful as predicting different numbers of steps ahead are different problems. 
    - **Recursive strategy**: Train a single one-step model and use the forcasts to update the lag features for the next step. Errors in first step will propagate into next step so should not be used for long horizons.
    - **DirRec strategy**: A combination of direct and recursive strategies. Use one model to predict the first step and then use the forcast from it as new lag features in the next model. Captures serial dependence better than direct but is prone to error propagation like recursive.
