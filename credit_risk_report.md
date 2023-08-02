# Module 12 Report Template

## Overview of the Analysis

Credit Risk Report

The purpose of the analysis is to create a linear regression model to predict the credit risk or worthiness of potential borrowers. The dataset provided had information describing the size of the loan (amount requested), interest rate, borrower income, debt to income ratio, number of accounts, derogatory marks (negative remarks of failure to pay on your credit report), total debt and loan status. The loan status had only two possible values, 0 or 1 indicating healthy loan or high-risk loan respectively.

The goal of the model was to use the data provided excluding the loan status parameter to train and see if the predictions could match the loan status parameter. For that reason, the dataset was divided into labels and features, the labels had the loan status parameter, and the features included the rest of the dataset. A value count of the labels was performed to check the balance of the dataset, which was determined to be weighted towards the healthy side of the loan status parameter.

The next step of the analysis included the creation of our test and training set using the function “train_test_split” with a random state equal to one. At this point the data is divided into a training set with around 75% of the data and a testing set with the remaining 25% of the data. 

Two models where created, the first one used a logistic regression classifier and the second utilized a logistic regression classifier plus a random over sampler to balance the dataset.

Results
Model 1: Logistic Regression Classifier without Balancing

•	Trains on the original imbalanced dataset with 75,036 healthy loans (class 0) and 2,500 high-risk loans (class 1).
•	Overall accuracy of 99%.
•	Precision to identify healthy loans (class 0) is 100%, indicating no false positives for healthy loans.
•	Precision to identify high-risk loans (class 1) is 87%, implying some false positives for high-risk loans.
•	F1 score for healthy loans is 1, indicating a perfect balance between precision and recall for class 0.
•	F1 score for high-risk loans is 0.88, showing a reasonably balanced trade-off between precision and recall for class 1.
•	Recall score for healthy loans is 1, indicating no false negatives for healthy loans (class 0).
•	Recall score for high-risk loans is 0.89, suggesting that some high-risk loans (class 1) were not identified.

Model 2: Logistic Regression Classifier with Random Over Sampler

•	Utilizes "random_over_sampler" to balance the training dataset, resulting in a model trained with 56,277 loans of each class.
•	Overall accuracy of 100%.
•	Precision to identify healthy loans (class 0) is 100%.
•	Precision to identify high-risk loans (class 1) is 87%.
•	F1 score for healthy loans is 1, indicating a perfect balance between precision and recall for class 0.
•	F1 score for high-risk loans is 0.93, showing an improved balance between precision and recall for class 1 compared to Model 1.
•	Recall score for healthy loans is 1, indicating that all healthy loans (class 0) were correctly identified.
•	Recall score for high-risk loans is 1, indicating that all high-risk loans (class 1) were correctly identified.

Summary:

Model 2, the Logistic Regression Classifier with Random Over Sampler, is the better model. Although both models exhibit high overall accuracy and precision for healthy loans, Model 2 outperforms Model 1 in terms of recall and F1 score for high-risk loans (class 1). This improvement is due to the use of the random over sampler, which balances the training dataset by generating additional synthetic samples of the minority class (high-risk loans). As a result, Model 2 achieves better performance in identifying high-risk loans, with a higher F1 score and perfect recall, meaning that all high-risk loans were correctly classified.
By addressing the class imbalance issue, Model 2 demonstrates enhanced predictive capabilities for both healthy and high-risk loans, making it the preferred choice for predicting credit risk or worthiness of potential borrowers. However, it is essential to consider other evaluation metrics and investigate further if class imbalance or other issues may be affecting the model's performance.


