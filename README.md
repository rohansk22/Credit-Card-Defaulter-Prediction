# Credit-Card-Defaulter-Prediction
Supervised Classification models to predict credit card defaulters. Comparative Analysis of Logistic Regression, Decision Trees and Random Forest

In this project, we help banks to predict which of their customers will default on a payment. This dataset contains information on default payments, demographic factors, credit data, history of payment, and bill statements of credit card clients in Taiwan from April 2005 to September 2005.

There are 25 variables containing customer information - which we reduce to 20 by selecting only the feautures that are relevent and / or have a strong correlation to our target - default = Y or N. 

Here is the data for your reference: https://www.kaggle.com/datasets/uciml/default-of-credit-card-clients-dataset

Firstly, we need to determine if this is a classification problem or a regression problem. Since we  deterine whether a customer will default - Y, or not - N, we need to CLASSIFY the outcome. Hence, a classification problem. 

By excluding 'SEX', 'EDUCATION', 'MARRIAGE' and 'ID' columns, we have eliminate text data and focus only on numeric data to solve the problem. 

As we clean and split the data, we run into a problem. An imblance. The target variable has a significantly higher number of records with N's than Y's. 
The work around this is to add more data to the Y's or remove data from the N's. Adding data gives a larger bandwidth to train our models. 
We will try to balance the two by importing more 'Y' data into the data set. This is called as oversampling. Similarly if we remove records, it is called undersampling. Here, we balance the data by oversampling it using the SMOTE library.

Once we have the training and testing data, we import the classification models - Logistic regression, Random Forest and Decision Tree. 

Logistic Regression: 
In logistic regression, the relationship between the dependent variable and independent variables is modeled using logistic function (also known as the sigmoid function), which gives an S-shaped curve that can be used to model the probability of a binary outcome. The coefficients in the logistic regression model represent the change in the log odds of the binary outcome for a unit change in a predictor variable, holding all other predictors constant.

Decision Tree Classifier:

In a decision tree classifier, the algorithm splits the dataset into smaller subsets based on the feature(s) that provide the most information gain about the target variable. The process of splitting continues until a stopping criteria is met, such as the maximum tree depth is reached or all the samples in a leaf node belong to the same class.

A decision tree classifier is easy to interpret and can handle both continuous and categorical variables. However, it can easily overfit the training data and create a complex tree that is not generalizable to new data. To avoid this problem, various techniques such as pruning, ensemble methods, and setting the maximum tree depth, can be used.

Random Forest Classifier: 
In a random forest model, multiple decision trees are trained on different subsets of the training data. These subsets are created by randomly sampling the data with replacement, and each tree is trained on a different subset. The features used in each split are also chosen randomly, adding further diversity to the individual trees.

At prediction time, the random forest model aggregates the predictions of all individual trees by taking the mean (for regression problems) or the majority vote (for classification problems) to make a final prediction. The combination of many trees in a random forest model often results in improved accuracy compared to a single decision tree.


To conclude, the Random Forest model is a highly powerful machine learning algorithm that predicted the defaulter with an F1 score and accuracy of 0.85. 

