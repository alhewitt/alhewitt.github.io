---
title: "Titanic"
date: 2022-11-02
permalink: /machine-learning/titanic/
categories:
  - PhD
  - Machine Learning
tags:
  - Lancaster
  - Machine Learning
  - Kaggle
  - Unfinished
classes: wide
---  

{% capture fig_img %}
![Foo]({{ "/assets/img/ml/header_titanic.jpeg" | relative_url }})
{% endcapture %}
<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
</figure>
After following the [Introduction to Machine Learning](https://www.kaggle.com/learn/intro-to-machine-learning) course on Kaggle, I decided to attempt uploading to a competition from scratch. I chose the [titanic competition](https://www.kaggle.com/competitions/titanic/overview) as it is very beginner friendly and has plenty of guides. After reading through a few attempts made by other people, I gave it a go. The competition involves predicting whether passengers died or survived based on various information like their name, ticket fare, class, age, whether they had other family on board etc. There were several missing variables which I tried to fill in rather than delete rows as there wasn't a huge amount of data to start with. 

Here are some of the methods I used to fill missing values:
 - The cabin has a lot of missing values and there are several missing ages. I will remove the cabin column since it is unlikely to be very informative with the majority of data being missing.
- Due to the "women and children first" order, the age may be very informative and so I did not want to remove it completely. I used averages for each title (Mr, Mrs, Miss etc) to fill in the missing ages.
- The ticket number was be dropped as it is not informative. Cabin was majority empty values so was deleted.
- For Embarked, I filled in the missing data using the price of the type of ticket purchased.
- And for the missing fare, I filled in the data using the ticket type and place of embarkment.

I then tested various models and found that a Random Forest Classifier produced the best results with an accuracy of 0.844 on the train data (cross validation: 0.861, 0.722, 0.833, 0.833, 0.886). My model's predictions on the test data produced a score of 0.75837 when submitted to the competition. This corresponds to the top 84%. I look forward to coming back to this project after learning more and seeing how much I can improve.

A copy of the submitted notebook can be found on [Kaggle](https://www.kaggle.com/code/amyhewitt/titanic-machine-learning-from-disaster/).
