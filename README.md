
# Comparing Classifiers
Practical Application III: Comparing Classifiers
Please find the code here: [[GitHub Link](https://github.com/MRiDeb/ComparingClassifiers/blob/main/prompt_III.ipynb)]

## Will a consumer subscribe to a Fixed Deposit (FD)?
This dataset comes from the UCI Machine Learning repository. The data is from a Portuguese banking institution and is a collection of the results of multiple marketing campaigns. We will make use of the article accompanying the dataset for more information on the data and features.

The data was collected from 17 campaigns and 79,354 contacts and occurred between May 2008 and November 2010.



Exploratory Data Analysis:
![image](https://github.com/user-attachments/assets/77886af6-8eea-4597-b9f0-ec36220e733e)

![image](https://github.com/user-attachments/assets/ac5aa9a1-c146-461a-aa63-aba97015f9c4)
Based on the above bar chart:

Admin, Blue_collar and technician contributed to most of job data

Marital status - Unknown seems to be not present at all

University degree holders seem to contribute more to the Campaign

Default - has many unknown values

housing- yes and no values seems to equally distributed

loans - most people who denied have no loans

contact -  most people contacted through cell phone

month - May month had the most campaigning happened

Days of the week - seems to be equally distributed

poutcome- those who were not called previously seems to be contributing more and also #pdays is not contributing much to the prediction and hence can be dropped .

## Business Objective 
The business objective of the bank marketing campaign is to increase term deposit subscriptions by targeting high-potential clients. By leveraging customer data and previous campaign outcomes, the bank aims to optimize marketing efforts and resource allocation. The goal is to maximize conversions while minimizing costs and improving customer engagement.

## Baseline Model
Before we build our first model, we want to establish a baseline using DummyClassifier. What is the baseline performance that our classifier should aim to beat?

Baseline accuracy score:
{'accuracy': 0.8023696222200641, 'precision': 0.11274934952298352, 'recall': 0.1138353765323993, 'f1_score': 0.11328976034858387, 'Time': 0.003927946090698242}

Since this is an imbalanced class, we will take the F1 score as the baseline, which is around 11%. Our models should perform better than this.

Next, we will look into simple models using KNN, Logistic Regression, Decision Tree, and SVC, and measure their accuracies.
![image](https://github.com/user-attachments/assets/3c771791-eb9b-429f-90ba-dae1a7750f9a)




Running various models has improved the F1 score, but it is still around 51%, which is much better than the baseline. Now, let's work on improving the model and observe its effect on the F1 score.

## Improving the Model
Now that we have some basic models, we want to try to improve them. Below, we list a few things that were put in place:

PolynomialFeatures with Degree, which resulted in 1770 columns.

Followed by Sequential Feature Selector to select 5 columns:
nr.employed, 
job duration, 
pdays, 
contact month duration, 
month pdays, 
euribor3m, 
pdays, 
nr.employed^2

After this, I ran all four models again, and the following results were obtained:

![image](https://github.com/user-attachments/assets/708218e2-3bca-4e5b-bb90-bd9bf89e99fc)


We see a slight improvement in F1 scores, but nothing major. We also tried to play with parameters, but nothing significant changed.

Next, we tried the RandomForestClassifier with minor improvement.

![image](https://github.com/user-attachments/assets/feccd75d-8b8f-4acf-84cc-5ada0bedd187)


Finally, checking model accuracy by changing the number of features, it seems that around 10 features produce optimal results.

![image](https://github.com/user-attachments/assets/c5691740-968b-4046-b0c7-91a8533c4980)





