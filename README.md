# Identifying Customer Churn

The goal of this project was to create a binary classification model to determine which customers are likely to leave the telecom company. Once customers are identified, the customer service team will contact them proactively to determine why they might leave. Resulting strategies to lower churn could include addressing individual customer concerns by customer service or general engineering improvements or sales policy changes.
To identify general improvements, it is not necessary to identify every churn instance, only enough to get sufficient customer feedback.


# Data Understanding

The dataset contained 20 features. The correlation shows how different variables relate to each other.

As you can see, there isn't a lot of perfect correlation among the variables except the few exceptions of minutes and charges.

This however is to be expected as the charges are determined directly by the minutes spent on the call.


# Evaluation Criteria

I built six models to determined the best predictor of customer churn. The models were evaluated on:

F1 Score - a measure of both precision (true positives/predicted positives) and recall (predicted true positives/actual true positives)

Accuracy - the total number of predictions the model gets correct

Confusion Matrix - shows True Negatives, False Positives, False Negatives, True Positives

The confusion matrix will be the most important criterion. Since the goal of this project is to identify potential churn customers and contact them to determine the reason for their dissatisfaction, we don't need to talk to every single one to determine the main reasons for churn. The assumption here is that the reasons for churn are not unique to each customer but rather shared among many customers. It is important that those customers we do speak with are likely to leave, so that the reasons for dissatisfaction that we identify are the reasons customers leave. So the evaluation will focus on the true positive to false positive ratio for each model.

# Logistic Regression Model

This model had a high number (182) of instances in which it incorrectly classified non-churn as churn while also correctly predicting 72 instances of churn.

The model is not yet optimal for use as it has  a high degree of incorrect results needing further tuning.

([Churn Data Images/output.png](https://github.com/Brandon2698/Phase3_Project/blob/main/Churn%20Data%20Images/output.png?raw=true))

# Random Forest Model

There were 76 correctly predicted instances of churn despite only 23 instances of non-churn incorrectly classified as churn.

This means this is a better model but the 25 false negatives indicate potential missed opportunities for getting customers at risk of churn.

[![Random Forest Model](images/RandomForest.jpg)](https://github.com/Brandon2698/Phase3_Project/blob/main/Churn%20Data%20Images/output1.png?raw=true)

# Gradient Boost Model

The Gradient Boost model predicted 79 instances of customer churn with only 30 instances of incorrect predictions.

This model produced the highest accuracies so was chosen for further fine tuning.

[![Gradient Boost Model](images/GradientBoost.jpg)](https://github.com/Brandon2698/Phase3_Project/blob/main/Churn%20Data%20Images/output2.png?raw=true)

# Evaluation (ROC)

As per the Receiver Operating Characteristic curve, the Random Forest and Gradient Boost model have the best predictive performances shown by their high AUCs.

The knn and logistic regression models have the poorest predictive abilities.

[![ROC Model](images/ROCModel.jpg)](https://github.com/Brandon2698/Phase3_Project/blob/main/Churn%20Data%20Images/output3.png?raw=true)

# False Positive - False Negative Trade-off

In this trade-off, decrease of the false positives was prioritized to slightly increasing the false negatives.

This reduces the risk of losing customers incorrectly classified as non-churned aiding the business’goals.

[![Confusion Matrix](images/ConfusionMatrix.jpg)](https://github.com/Brandon2698/Phase3_Project/blob/main/Churn%20Data%20Images/output5.png?raw=true)

# Evaluation

Our model can correctly make predictions for approximately 93.7% of the customers, indicating that the model's predictions were accurate for the majority of the customers. Out of all the customers predicted as churned, approximately 69.44% of them actually churned, indicating that when the model identified a customer as churned, it was correct around 69.44% of the time. 

Our model successfully captured about 86.96% of the customers who truly churned. The F1 score of 79.2% indicates that our model achieved a balanced trade-off between correctly identifying churned customers and minimizing false predictions.

# Conclusion

In conclusion, both the Random Forest model and the Gradient Boost model show good performance in predicting customer churn. However, the Random Forest model has a slightly lower testing accuracy and precision compared to the other model. This suggests that the GB model may have a better balance between false positive and false negative predictions.
The trade-off between identifying as many churn cases as possible (high recall) and minimizing false positive predictions (high precision) is necessary for our analysis as it improves the predictive performance of our model and serves the objective of our stakeholder.
The features that contribute the most to whether a customer churns or not include 'customer service calls', 'total day charge', 'total day minutes', 'total international calls', and 'total eve minutes'.

# Recommendations

Assess the Pricing Structure: Syria Tel should consider examining charges and researching methods for optimizing pricing plans or introducing flexible pricing options to satisfy the different needs of customers. 
Targeted Retaining Strategies: According to the model's projections, the organization should focus on customers who are more likely to churn. Identifying these clients ahead of time allows the organization to interact with them proactively, offering specific rewards, discounts, or upgraded services to encourage continuous loyalty. 
Customer Sectioning: Syria Tel should separate its customers depending on their churn propensity, allowing it to better customize its marketing and retention efforts. 



