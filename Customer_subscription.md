# Customer Subscription Analysis

## Overview

The company has launched a mobile app with a free and paid upgrade version. The upgraded version is provided for free for 24 hours to collect the customer’s behavior.

The main goal is to sell the premium version at a low advertisement cost to eliminate budget while enhancing subscriptions.

### Purpose
Help the company to identify customers that are inclined to subscribe, so they could only advertise to those who do not want to subscribe, which saved partial advertisement costs. 

Further, the company could attain more subscribers by promoting offers to those customers who do not intend to subscribe.

## Approach

### Exploratory Data Analysis

Descriptive Statistics of numerical variables.

![Screen Shot 2022-09-01 at 7 38 01 PM](https://user-images.githubusercontent.com/88747464/188030278-96b1426f-e7ce-44e3-bbd6-ee44929262e6.png)

Analyze categorical features.

![Screen Shot 2022-09-01 at 7 38 30 PM](https://user-images.githubusercontent.com/88747464/188030290-623fb076-e69a-4bba-afdb-c0a2562dfc64.png)

![Screen Shot 2022-09-01 at 7 36 31 PM](https://user-images.githubusercontent.com/88747464/188030389-aa2a1ce5-e929-464d-b8e6-81d939d32454.png)

![Screen Shot 2022-09-01 at 7 36 22 PM](https://user-images.githubusercontent.com/88747464/188030401-6a16ff93-b307-4437-a0ea-203c2ac08e5a.png)
![Screen Shot 2022-09-01 at 7 36 12 PM](https://user-images.githubusercontent.com/88747464/188030409-4b3744c6-6bde-4517-ad6e-16c268ce752f.png)

![Screen Shot 2022-09-01 at 7 36 42 PM](https://user-images.githubusercontent.com/88747464/188030426-786df93d-77d6-42ec-88e7-c8f39c45f09f.png)

### Feature Selection - Logistic Regression
1. Prevent **Multicollinearity** by dropping large **Variance Inflation Factors** (VIF).

2. Select the features with high weights.

![Screen Shot 2022-09-01 at 7 47 37 PM](https://user-images.githubusercontent.com/88747464/188031122-fab57b48-491b-4766-bd2a-71f03af5c53a.png)
![Screen Shot 2022-09-01 at 7 51 26 PM](https://user-images.githubusercontent.com/88747464/188031270-8b76bcb2-6af9-4902-a75f-b32d91cf2c64.png)

### Feature Selection - Random Forest Classification

![Screen Shot 2022-09-01 at 7 57 55 PM](https://user-images.githubusercontent.com/88747464/188031717-086f2c0e-1ca6-47ab-81fa-6d7e8b123c51.png)

Since the accuracy of Logistic Regression is only 50%, and the accuracy of Random Forest Classification is 72%.

Random Forest feature selection technique would be chosen.

Top 5 features for customer enrollment are `VerifyPhone`, `remain_screen_list`, `VerifyDateOfBirth`, `numscreens`, and `location`.

### Final Data Set

![Screen Shot 2022-09-01 at 8 00 32 PM](https://user-images.githubusercontent.com/88747464/188031924-ce1a9f7e-781b-4d4c-af3b-1cf793e8e273.png)

## Findings

| Logistic Regression | K-Nearest Neighbors | Decision Tree Classification |
| --- | --- | --- | 
| Accuracy: 75.5% | Accuracy: 75.5% | Accuracy: 75.5% |
|![Screen Shot 2022-09-01 at 8 08 52 PM](https://user-images.githubusercontent.com/88747464/188032882-fd3f9127-7123-46ba-af9d-6a2e1e255c70.png) | ![Screen Shot 2022-09-01 at 8 10 11 PM](https://user-images.githubusercontent.com/88747464/188032895-4c455333-fdf1-4431-8680-96b916d26166.png) | ![Screen Shot 2022-09-01 at 8 14 17 PM](https://user-images.githubusercontent.com/88747464/188033140-9050a730-09c4-4387-a9a9-7e17c41bd17f.png) |
|![Screen Shot 2022-09-01 at 8 09 08 PM](https://user-images.githubusercontent.com/88747464/188032937-4ea86288-ae6f-430d-a43c-967ec7e3e864.png) | ![Screen Shot 2022-09-01 at 8 17 58 PM](https://user-images.githubusercontent.com/88747464/188033432-cca2a837-893d-4910-938c-aad0c6bedc90.png) | ![Screen Shot 2022-09-01 at 8 18 30 PM](https://user-images.githubusercontent.com/88747464/188033443-1e8dfaf2-76ee-4ed3-9efa-bedb1e644557.png) |
|![Screen Shot 2022-09-01 at 8 09 21 PM](https://user-images.githubusercontent.com/88747464/188032985-a5ef7083-8d95-4eb1-b050-f7d0120c2f04.png) | ![Screen Shot 2022-09-01 at 8 10 28 PM](https://user-images.githubusercontent.com/88747464/188032989-a86a11c4-437b-4db1-9968-4aebd909dbe2.png) | ![Screen Shot 2022-09-01 at 8 14 38 PM](https://user-images.githubusercontent.com/88747464/188033159-feb30f20-a3af-4db0-99b8-bb8aee1d8cc6.png) |
| ROC AUC: 81.1% | ROC AUC: 82.0% | ROC AUC: 81.2% |
| ![Screen Shot 2022-09-01 at 8 08 45 PM](https://user-images.githubusercontent.com/88747464/188032913-1fa3cd86-2f33-4f01-8235-730771ad2a92.png) | ![Screen Shot 2022-09-01 at 8 10 06 PM](https://user-images.githubusercontent.com/88747464/188032921-38ac463b-4662-4848-84a1-3ad76b493e19.png) | ![Screen Shot 2022-09-01 at 8 14 09 PM](https://user-images.githubusercontent.com/88747464/188033170-5012c9e3-d503-43c6-80aa-e11646a9da9c.png) |
| ![Screen Shot 2022-09-01 at 8 11 03 PM](https://user-images.githubusercontent.com/88747464/188033003-31ed2586-e5ea-49fb-ae66-cbe24f2969e0.png) | ![Screen Shot 2022-09-01 at 8 10 46 PM](https://user-images.githubusercontent.com/88747464/188033009-9bf7d3ae-f644-4eb7-8796-e6d2ed4734bc.png) | ![Screen Shot 2022-09-01 at 8 19 42 PM](https://user-images.githubusercontent.com/88747464/188033530-dc13e779-98a0-4c5d-8e48-c713e8a76d01.png) |

| Extreme Gradient Boost (XGB) | Adaptive Boost (AdaBoost) |
| --- | --- |
| Accuracy: 76.4% | Accuracy: 75.6% | 
|![Screen Shot 2022-09-01 at 8 21 59 PM](https://user-images.githubusercontent.com/88747464/188033966-98a09f53-5097-4f58-96bb-8e9b56642d08.png) | ![Screen Shot 2022-09-01 at 8 22 44 PM](https://user-images.githubusercontent.com/88747464/188033973-abb34a88-175a-4b5d-8277-9b1f6cb4b3b2.png) |
|![Screen Shot 2022-09-01 at 8 22 07 PM](https://user-images.githubusercontent.com/88747464/188033991-ff79beb2-0a05-4677-a5a1-ab1952e7a18c.png) | ![Screen Shot 2022-09-01 at 8 22 53 PM](https://user-images.githubusercontent.com/88747464/188034000-e3c6853e-286a-44b4-b876-e72fcd57c924.png) |
|![Screen Shot 2022-09-01 at 8 22 15 PM](https://user-images.githubusercontent.com/88747464/188034009-c971f988-3aa2-44ed-86e1-1a2aad9fbecb.png) | ![Screen Shot 2022-09-01 at 8 23 26 PM](https://user-images.githubusercontent.com/88747464/188034020-22a3e8a0-009a-4633-84d9-a513aa7bc9a2.png) |
| ROC AUC: 82.9% | ROC AUC: 81.5% |
|![Screen Shot 2022-09-01 at 8 21 51 PM](https://user-images.githubusercontent.com/88747464/188034046-b5c87cf8-893c-484e-bbad-7706b47f45d7.png) | ![Screen Shot 2022-09-01 at 8 22 38 PM](https://user-images.githubusercontent.com/88747464/188034050-1f228f06-f6f1-4364-954e-88a4bc9d68c2.png) |
|![Screen Shot 2022-09-01 at 8 23 05 PM](https://user-images.githubusercontent.com/88747464/188034060-e0c26b36-3793-4329-ade6-8d231a8553ac.png) | ![Screen Shot 2022-09-01 at 8 23 17 PM](https://user-images.githubusercontent.com/88747464/188034069-52713c32-d42f-4c79-91e6-3d19637187bc.png) |

## Summary

Overall, the above models achieved similar performance with an accuracy of around 75%. 

2 models would be recommended with the best performance.

#### Extreme Gradient Booster
* Highest Accuracy
* Highest Roc-Auc score
* Highest Precision - 'Yes'
* Highest Recall - 'No'
* Greatest performance on Lift Curve

#### Logistic Regression
* Most accurate predictions on the testing dataset
* Highest Precision - 'No'
* Highest Recall - 'Yes'

## Further Insights

One **limitation** of Logistic Regression would be the assumption of **linearity** between predicted and response features.

`Random Forest`, `Gaussian Naive Bayes`, `Support Vector Machine`, and `Voting Classifier` models were also conducted for this study, but the results are not as good as the above models.

If the company wants higher accuracy in the estimation, **cross-validation** techniques for hyperparameter tuning could be considered.

However, this would be **time-consuming** and **computationally intensive** for a large dataset. 

## Resources

Customers_to_Subscription_Through_App_Behavior. (2021, April 6). Kaggle. Retrieved September 20, 2022, from https://www.kaggle.com/datasets/hkhamnakhalid/customers-to-subscription-through-app-behavior?select=clean_FineTech_appData.csv

Thorn, J. (2021, December 13). The Lift Curve: Unveiled - Towards Data Science. Medium. Retrieved September 20, 2022, from https://towardsdatascience.com/the-lift-curve-unveiled-998851147871


