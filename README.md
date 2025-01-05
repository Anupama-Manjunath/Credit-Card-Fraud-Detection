# Credit-Card-Fraud-Detection
This project focuses on detecting fraudulent credit card transactions using machine learning techniques. 

The dataset is obtained from Kaggle and contains transactions made by credit cards in September 2013 by European cardholders. It spans two days of transactions, out of which 492 are fraudulent and the remaining 284,315 are legitimate. 
The dataset is highly imbalanced, with the fraudulent transactions (positive class) accounting for only 0.172% of the total.

The dataset includes only numerical input variables that result from a PCA transformation. The original features are not available due to confidentiality issues. The features V1, V2, … V28 are the principal components derived using PCA, while the features Time and Amount have not been transformed.

## Key Steps:

### 1. Data Preprocessing
The data is cleaned, and features such as 'Time' and 'Amount' are scaled using **RobustScaler** to handle outliers.

### 2. Handling Imbalanced Classes
Since fraudulent transactions are much fewer than legitimate ones, **SMOTE (Synthetic Minority Over-sampling Technique)** is used to balance the dataset.

### 3. Modeling
A **Random Forest Classifier** and **Decision Tree Classifier** are trained to predict fraudulent transactions. **Stratified K-Fold Cross-Validation** is used to ensure that each fold maintains the same proportion of fraudulent and non-fraudulent transactions, helping to prevent bias during training and evaluation.

### 4. Evaluation
The model performance is evaluated using metrics such as **Recall** and **ROC-AUC**. The model performs well, particularly in detecting fraudulent transactions with minimal false positives.

- After applying SMOTE and cross-validation, the model shows a significant improvement in recall (from 0.76 to 0.85), indicating better detection of fraudulent transactions compared to the previous version without SMOTE.

- Macro Average- the model demonstrates strong performance with metrics such as precision: 0.94, recall: 0.92, and F1-score: 0.93, indicating that the model has a high capacity to correctly identify fraudulent transactions while minimizing false positives. Specifically, the recall of 0.92 indicates that 92% of actual fraudulent transactions are correctly identified, which is crucial for fraud detection, while the precision of 0.94 suggests that only 6% of transactions flagged as fraudulent are false positives.

## Results:
The model has an ROC-AUC score of 0.98 and is excellent at distinguishing between legitimate and fraudulent transactions. Moreover, the model gets more accurate in predicting fraudulent transactions after addressing class imbalance

## Tools and Libraries:
- **Python**
- **Scikit-learn**: For building and evaluating machine learning models.
- **Imbalanced-learn**: For handling class imbalance using SMOTE.
- **Matplotlib/Seaborn**: For EDA and visualizing model results (such as confusion matrix and ROC curve)

## Conclusion:
This project demonstrates the use of machine learning techniques in detecting fraudulent credit card transactions, offering a reliable tool for financial institutions to reduce fraud.
