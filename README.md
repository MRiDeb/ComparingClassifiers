
# Comparing Classifiers
Practical Application III: Comparing Classifiers
Please find the code here: [GitHub Link](https://github.com/MRiDeb/ComparingClassifiers/blob/main/prompt_III.ipynb)

## Will a consumer subscribe to a Fixed Deposit (FD)?
This dataset comes from the UCI Machine Learning repository. The data is from a Portuguese banking institution and is a collection of the results of multiple marketing campaigns. We will make use of the article accompanying the dataset for more information on the data and features.

The data was collected from 17 campaigns and 79,354 contacts and occurred between May 2008 and November 2010.



Exploratory Data Analysis:
![image](https://github.com/user-attachments/assets/51fa40dc-06a0-4a48-ac70-f0411e0b80ff)

## Baseline Model
Before we build our first model, we want to establish a baseline using DummyClassifier. What is the baseline performance that our classifier should aim to beat?

Baseline accuracy score:
{'accuracy': 0.8023696222200641, 'precision': 0.11274934952298352, 'recall': 0.1138353765323993, 'f1_score': 0.11328976034858387, 'Time': 0.003927946090698242}

Since this is an imbalanced class, we will take the F1 score as the baseline, which is around 11%. Our models should perform better than this.

Next, we will look into simple models using KNN, Logistic Regression, Decision Tree, and SVC, and measure their accuracies.

![image](https://github.com/user-attachments/assets/534ed629-be6c-4233-a5f5-d51087624aca)

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

![image](https://github.com/user-attachments/assets/717a8511-587b-4507-8d39-a3e97241d6c6)

We see a slight improvement in F1 scores, but nothing major. We also tried to play with parameters, but nothing significant changed.

Next, we tried the RandomForestClassifier with minor improvement.
![image](https://github.com/user-attachments/assets/b563cade-25b0-4200-86e1-18c22f95c6e4)



