# Company-Bankruptcy-Prediction
Here we analyze the financial data of companies and create a classification model to predict bankruptcy

### Information about the given data :

1. target variable is 'Bankrupt?'
2. features > all other(94) columns represnting some form of financial data
3. The data tells us about all the financial parameters of a company and whether the company went bankrupt or not
4. This ia a Binary Classification problem since the target variable is bankrupt with two classes Yes and No (We can start with simple logistic regression model and later move to more complex Random Forest and compare the performances)

## Feature Engineering : 
There are 94 features which make the data complex. Here we can use PCA to perform feature engineering and reduce the no of dimensions(no of columns) maintaining the explained varinace at a high value

1. From the PCA transformation analysis it is found that 60 features contributes to 98% variance
2. Let us set the explained variance as 95% for further analysis

## Logistic Regression Modelling
Now that we have the trnasformed data with lesser dimension we create a Logistic Regression model on the transformed data 


**Logistic Regression model performance :**
1. Train Accuracy is 97% while Test Accuracy is 96% (little overfitting)
2. From the Confusion Matrix we can see 15 False Posiive cases which means in 15 cases the prediction was not bankrupcy but in reality it was bankrupcy. If we think bankrupcy as a critical problem to avoid, we need to reduce the False Positive cases

## Random Forest Modelling
Now lets check with Random Forest and find out if this model performs better to resolve the problem

### Finding max-depth : 
max_depth optimal value comes around 8 with Train accuracy of 97.7% and Test accuracy of 96.5%

## Hypertune the model using GridSearch 
We are going to use GridSearch to hypertune the model and check the performance


**Conclusions from the Grid Search analysis :**
1. We hypertuned the RandomForest model with Grid Search which gave an accuracy of 96.6% improved from 95.9% in Logistic Regression model
2. Another important achievement - We have reduced the number of False Positive cases to only 1 from 16. Considering bankruptcy as a critical event to avoid the model performs quite well on the given dataset
