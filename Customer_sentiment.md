# Customer Reviews Analysis

## Overview

The company wants to improve customer satisfaction:
- Analyze customers' previous reviews from Amazon using **Natural Language Processing**.
- Predict future consumers' sentiments using **Neural Network**.

## Results

**Deep Learning Neural Network** - capable of performing text classification with high accuracy and lower-level computation. 

**Recurrent Neural Network (RNN)** - used for sentiment analysis, which would learn the writers' emotions by analyzing texts.

### Original Reviews vs. Cleaned Reviews

* Vocabulary Size: 1568
* Word Embedding Length: 6
* Max Sequence Length: 113

![Screen Shot 2022-07-17 at 2 42 59 PM](https://user-images.githubusercontent.com/88747464/179420295-11698c7c-46bf-4c5c-9371-18f1f4fdbdc2.png)

### Sequential API Model

![Screen Shot 2022-07-17 at 3 00 38 PM](https://user-images.githubusercontent.com/88747464/179420849-aff9084f-abcb-4ab8-83d1-80807eaa5b50.png)

![Screen Shot 2022-07-17 at 3 00 30 PM](https://user-images.githubusercontent.com/88747464/179420853-72fffa05-9bae-4448-a880-60bfa23638f9.png)
![Screen Shot 2022-07-17 at 3 00 23 PM](https://user-images.githubusercontent.com/88747464/179420854-64d74db9-ac02-4311-a978-f09823bb12cc.png)

| | Accuracy | Loss |
| --- | --- | --- |
| Training | 68% | 0.72 |
| Validation | 54% | 4.04 |
| Testing | 51% | 1.63 |

* **ROC-AUC** score is 0.52.

### Functional API Model

![Screen Shot 2022-07-17 at 3 06 10 PM](https://user-images.githubusercontent.com/88747464/179421057-33a5c058-2b4d-4dde-9123-630c83a085c5.png)

![Screen Shot 2022-07-17 at 3 06 18 PM](https://user-images.githubusercontent.com/88747464/179421070-b942c25c-ec80-4ca1-97c5-5a3de714270c.png)
![Screen Shot 2022-07-17 at 3 06 26 PM](https://user-images.githubusercontent.com/88747464/179421073-81b34a76-6aef-4583-a0e1-3478df7b40b2.png)

| | Accuracy | Loss |
| --- | --- | --- |
| Training | 97% | 0.12 |
| Validation | 79% | 0.42 |
| Testing | 74% | 0.56 |

* **ROC-AUC** score is 0.82.

### Early Stopping

Early Stopping Criteria were used to prevent the model from overfitting.

The maximum epochs of this model are 40, but it stopped training at 26 epochs since metrics were not improved anymore. 

![Screen Shot 2022-07-17 at 3 25 01 PM](https://user-images.githubusercontent.com/88747464/179422365-dc63a1c6-7264-4bb6-ba3b-46389461d343.png)

The final training epoch contains the best result. 

However, if the model trains for lesser epochs with a lower number of patience, this can result in a low accuracy score.

## Summary

Overall, the **Functional API** Model achieves a better performance, which should be used for future analysis.

* Dense hidden layers: **Rectified Linear Activation (ReLu) Function** (Results in higher accuracy than Sigmoid Function.)
* Dense output layer: **SoftMax Function**
* Loss Function: **Categorical Cross-entropy** (Results in higher accuracy than Binary Cross-entropy.)
* Optimizer: **Adam** (Handles noise and reduces overfitting to improve the model performance.)

If the company wants to predict future consumer sentiment, **Natural Language Processing** and **Neural Networks** are recommended.

They may further use another model for cross-validation to achieve higher accuracy results.

## Resources

UCI Machine Learning Repository: Sentiment Labelled Sentences Data Set. (2015). UCI Machine Learning Repository. https://archive.ics.uci.edu/ml/datasets/Sentiment+Labelled+Sentences



