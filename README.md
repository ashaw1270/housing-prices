This repository contains the code for reproducing the results of our paper, [When Less is More: Evaluating Simplicity vs. Complexity in House Price Prediction](House%20Prices%20Paper.pdf).

Authors: Michael Kim, Anish Kushalapa, Adam Shaw (all authors contributed equally, names listed alphabetically).

## TL;DR

- Evaluated multiple ML models (linear regression, SVR, ridge, lasso, XGBoost, PCA) on a 545-sample housing dataset
- No model significantly outperformed standard linear regression ($R^2 = 0.68$)
- Simpler models proved more interpretable and equally effective—complexity wasn't necessary

## Abstract

Predicting house prices accurately is essential for buyers and sellers alike. This research explores the effectiveness of various machine learning algorithms—including multiple linear regression, support vector regression, ridge and lasso regularization, and XGBoost—in predicting house prices based on property features. Our analysis utilized a dataset from Kaggle, which was made up of 545 houses from the Boston metropolitan area, each described by 13 unique features. To address the high feature-to-sample-size ratio and reduce model variability observed in initial trials, we relied on a 5-fold cross-validation throughout the study, providing a more consistent and reliable estimate of model performance. Despite experimenting with complex models, our results show that standard linear regression demonstrates comparable performance with an $R^2$ of approximately 0.68, making it a robust and interpretable choice for this dataset.

## Introduction

Accurately predicting house prices using property features can provide crucial information to homebuyers, real estate agents, and policymakers. In this paper, we aim to extract valuable information from our dataset to create a model that accurately predicts price.

To train our model, we used the [Housing Prices Dataset](https://www.kaggle.com/datasets/yasserh/housing-prices-dataset) from Kaggle, which consisted of 545 houses, each with 13 features. In our early planning phase, we ruled out some models due to their incompatibility with our dataset. For example, we considered using neural networks; however, due to the limited sample size, we concluded that it would not be effective. Clustering algorithms such as k-nearest neighbors were also ruled out, as the dataset’s high proportion of categorical features could compromise performance. After eliminating these models, we narrowed it down to approaches better suited to the characteristics of our data.

## Conclusion

In this paper, we explore various machine learning models to predict house prices, beginning with standard multiple linear regression as our baseline, and moving on to more advanced techniques such as regularization methods, support vector regression, principal component analysis, and adjustments for multicollinearity using the variance inflation factor. After trying many different techniques, we could not find a model that produced significantly greater results than standard linear regression. One could argue that PCA or SVR produced better results, but we decided that these minor improvements were not practically significant. However, perhaps this is not a bad thing. A simple model like linear regression is more easily interpretable, and if a simple, interpretable model can be used without sacrificing performance, it can be more valuable for us to understand the data itself. Ultimately, this reinforces the idea that complexity is not always necessary—simple, well-understood models can be both effective and insightful.

We now take this time to discuss the limitations and future considerations for this project. In order to see if our models generalize well, we would like to test on other datasets. This would also give us insight into whether our models overfit or not. Since this dataset only contains 545 points, it is possible that the data does not capture enough of the variation or nuance in the very diverse housing market. More data to train and test on can help tune our models or even open the doors to different models that may perform better, like neural networks. We considered polynomial regression in our planning phase, but ultimately decided against it as the data looked linear, so a polynomial model may have a higher risk of overfitting. In terms of how the current models can be improved with the data we are currently using, we can consider interaction terms in linear regression. Since we already researched the multicollinearity of the features, this is a natural next step. We could also consider feature selection or outlier detection. We originally decided to keep all of our features and possible outliers to maximize the use of all our data, but it may be true that certain features or outliers are adding unwanted noise to our models.
