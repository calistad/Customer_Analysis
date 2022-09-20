# Customer Analysis

## Overview

Help a company to optimize sales while better understand the customers by conducting 4 data analysis.

* Classify 50,000 customers based on their behaviors to enhance subscriptions and eliminate budget.

* Combine products that would be likely purchased together by performing a Market Basket Analysis among 522,000+ transactions.

* Implement the Collaborative Filtering Recommender by analyzing 4300+ customers' purchases to suggest similar items.

* Improve customer satisfaction using NLP and Deep Learning models with 74% accuracy.

## Customer Classification

[Click here for a more detailed version]

The company launches a mobile app with the free version and the paid upgrade version. The company provided the upgrade version in the free version app for 24 hours to collect the customer’s behavior. 

The main goal is to sell the premium version app at a low advertisement cost to eliminate budget while enhancing subscriptions.

### Approach

![Screen Shot 2022-09-01 at 7 38 01 PM](https://user-images.githubusercontent.com/88747464/188030278-96b1426f-e7ce-44e3-bbd6-ee44929262e6.png)
![Screen Shot 2022-09-01 at 7 36 42 PM](https://user-images.githubusercontent.com/88747464/188030426-786df93d-77d6-42ec-88e7-c8f39c45f09f.png)

![Screen Shot 2022-09-01 at 7 36 22 PM](https://user-images.githubusercontent.com/88747464/188030401-6a16ff93-b307-4437-a0ea-203c2ac08e5a.png)
![Screen Shot 2022-09-01 at 7 36 12 PM](https://user-images.githubusercontent.com/88747464/188030409-4b3744c6-6bde-4517-ad6e-16c268ce752f.png)

Drop large Variance Inflation Factors (VIF) to prevent Multicollinearity.

![Screen Shot 2022-09-01 at 7 47 37 PM](https://user-images.githubusercontent.com/88747464/188031122-fab57b48-491b-4766-bd2a-71f03af5c53a.png)
![Screen Shot 2022-09-01 at 7 51 26 PM](https://user-images.githubusercontent.com/88747464/188031270-8b76bcb2-6af9-4902-a75f-b32d91cf2c64.png)

Feature Selection - Random Forest Classification

![Screen Shot 2022-09-01 at 7 57 55 PM](https://user-images.githubusercontent.com/88747464/188031717-086f2c0e-1ca6-47ab-81fa-6d7e8b123c51.png)

Final Data Set

![Screen Shot 2022-09-01 at 8 00 32 PM](https://user-images.githubusercontent.com/88747464/188031924-ce1a9f7e-781b-4d4c-af3b-1cf793e8e273.png)

## Finding

The top five most significant features for customer enrollment are `VerifyPhone`, `remain_screen_list`, `VerifyDateOfBirth`, `numscreens`, and `location`.

Two models would be recommended with the best performance.

#### Extreme Gradient Booster
* Highest Accuracy
* Highest Roc-Auc score
* Highest Precision - 'Yes'
* Highest Recall - 'No'
* Greatest performance on Lift Curve

#### Logistic Regression
* Most accurate predictions on testing dataset
* Highest Precision - 'No'
* Highest Recall - 'Yes'

| Extreme Gradient Boost (XGB) | Logistic Regression |
| --- | --- |
| Accuracy: 76.4% | Accuracy: 75.5% | 
|![Screen Shot 2022-09-01 at 8 21 59 PM](https://user-images.githubusercontent.com/88747464/188033966-98a09f53-5097-4f58-96bb-8e9b56642d08.png) | ![Screen Shot 2022-09-01 at 8 08 52 PM](https://user-images.githubusercontent.com/88747464/188032882-fd3f9127-7123-46ba-af9d-6a2e1e255c70.png) |
|![Screen Shot 2022-09-01 at 8 22 07 PM](https://user-images.githubusercontent.com/88747464/188033991-ff79beb2-0a05-4677-a5a1-ab1952e7a18c.png) | ![Screen Shot 2022-09-01 at 8 09 08 PM](https://user-images.githubusercontent.com/88747464/188032937-4ea86288-ae6f-430d-a43c-967ec7e3e864.png) |
|![Screen Shot 2022-09-01 at 8 22 15 PM](https://user-images.githubusercontent.com/88747464/188034009-c971f988-3aa2-44ed-86e1-1a2aad9fbecb.png) | ![Screen Shot 2022-09-01 at 8 09 21 PM](https://user-images.githubusercontent.com/88747464/188032985-a5ef7083-8d95-4eb1-b050-f7d0120c2f04.png) |
| ROC AUC: 82.9% | ROC AUC: 81.1% |
|![Screen Shot 2022-09-01 at 8 21 51 PM](https://user-images.githubusercontent.com/88747464/188034046-b5c87cf8-893c-484e-bbad-7706b47f45d7.png) | ![Screen Shot 2022-09-01 at 8 08 45 PM](https://user-images.githubusercontent.com/88747464/188032913-1fa3cd86-2f33-4f01-8235-730771ad2a92.png) |
|![Screen Shot 2022-09-01 at 8 23 05 PM](https://user-images.githubusercontent.com/88747464/188034060-e0c26b36-3793-4329-ade6-8d231a8553ac.png) | ![Screen Shot 2022-09-01 at 8 11 03 PM](https://user-images.githubusercontent.com/88747464/188033003-31ed2586-e5ea-49fb-ae66-cbe24f2969e0.png) |


## Product Analysis

### Approach

The dataset consists of 522,000+ transactions.

![Screen Shot 2022-09-19 at 9 55 17 PM](https://user-images.githubusercontent.com/88747464/191150426-0133d7db-0e53-4d27-a07d-6421946a48e5.png)

Analyze Support, Lift, and Confidence Metrics.

![Screen Shot 2022-09-19 at 9 55 37 PM](https://user-images.githubusercontent.com/88747464/191150596-da0bca2a-4d70-4bf4-ae60-9c0074d7883e.png)

![Screen Shot 2022-09-19 at 9 55 47 PM](https://user-images.githubusercontent.com/88747464/191150608-4bfaf82d-2710-451b-bca0-80ed34267167.png)

### Finding

* Apriori - Top 5 products with the highest support values.

![Screen Shot 2022-09-19 at 10 13 48 PM](https://user-images.githubusercontent.com/88747464/191152220-5715f01c-0d6d-40f3-9184-b737899b77f2.png)

* Association Rules

Top 5 products with the highest support and confidence values, given the lift value inidicates the relationship between items are not random.

![Screen Shot 2022-09-19 at 9 56 11 PM](https://user-images.githubusercontent.com/88747464/191150691-42b021a2-33f3-4d52-ad17-18b163eb3f27.png)


## Customer Purchases and Recommendations

### Approach

The dataset consists of 530,000+ transactions.

![Screen Shot 2022-09-19 at 10 07 18 PM](https://user-images.githubusercontent.com/88747464/191151791-8bfc3a49-7e92-425b-bb5d-0ff432879887.png)

* Customer to Product Matrix - Cosine Similarity

![Screen Shot 2022-09-19 at 10 11 54 PM](https://user-images.githubusercontent.com/88747464/191151996-137280db-cb81-4906-b775-2bc3b62fadce.png)

* Customer to Customer Matrix

![Screen Shot 2022-09-19 at 10 09 49 PM](https://user-images.githubusercontent.com/88747464/191151846-eae6efb2-3751-41d4-90d9-c96c920d21a7.png)

* Product to Product Matrix

![Screen Shot 2022-09-19 at 10 11 35 PM](https://user-images.githubusercontent.com/88747464/191152045-6753f745-3215-4607-9853-f1b0f825d463.png)

### Finding

Use the given `Customer ID` to get the recommend products based on customer similarity.

![Screen Shot 2022-09-19 at 10 15 30 PM](https://user-images.githubusercontent.com/88747464/191152447-85b33ac4-50d8-4632-b765-46adbd2a028d.png)

Use the given `Stock Code` to get the recommend products based on item similarity.

![Screen Shot 2022-09-19 at 10 16 58 PM](https://user-images.githubusercontent.com/88747464/191152592-b78d8143-65e9-4941-8d8d-a782cf5b283c.png)


## Customer Sentiment

### Approach

### Finding


## Resources

Dataset: https://www.kaggle.com/datasets/hkhamnakhalid/customers-to-subscription-through-app-behavior?select=clean_FineTech_appData.csv

Lift Curve: https://towardsdatascience.com/the-lift-curve-unveiled-998851147871













Analyze customer sentiment using Neural Network and NLP with 74% accuracy to improve customer satisfaction.

implementing Supervised Machine Learning Analysis with 5 data models and obtaining 76.4% accuracy.

Conduct Market Basket Analysis and Collaborative Filtering Recommender among 522,000+ transactions, increasing sales by suggesting similar items to customers.


