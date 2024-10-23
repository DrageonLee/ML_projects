Fraudulen# Fraudulent Transaction Detection

This project aims to detect fraudulent transactions in a highly imbalanced credit card dataset using different machine learning models. Initially, an unsupervised anomaly detection approach was employed, but a shift to supervised learning with data balancing techniques yielded significantly better results.

## Table of Contents
- [Introduction](#introduction)
- [Challenges Faced](#challenges-faced)
- [Solutions Implemented](#solutions-implemented)
- [Results](#results)
- [Future Work](#future-work)
- [License](#license)

## Introduction
The task was to detect fraudulent transactions in a highly imbalanced credit card dataset. Initially, the unsupervised anomaly detection algorithm, Isolation Forest, was chosen with the assumption that it could effectively identify outliers representing fraudulent transactions.

### Preprocessing Details
- **Data Loading**: The dataset was loaded, and the target variable (Class) was separated from the features.
- **Scaling**: The `Time` and `Amount` columns were scaled using `StandardScaler` to ensure numerical stability.
- **Train-Test Split**: The dataset was split into training and test sets using stratified sampling to maintain the class distribution (fraud vs. non-fraud) across both sets.

The performance of the models was evaluated using metrics like accuracy, precision, recall, F1-score, and ROC-AUC.

## Algorithms Used
- **Isolation Forest (unsupervised learning)**: Initially selected for anomaly detection, assuming unsupervised methods would be sufficient for detecting fraud.
- **Random Forest and XGBoost (supervised learning)**: Later applied to compare and evaluate their performance in detecting fraud.
- **SMOTE**: Applied to handle the class imbalance by oversampling the minority class (fraudulent transactions).

## Challenges Faced
- **Data Imbalance**: Less than 0.2% of transactions were fraudulent, leading to severe imbalance issues, which made model training challenging.
- **Poor Performance of Isolation Forest**: Although Isolation Forest achieved over 99% accuracy, its recall (0.28) and F1-score (0.30) indicated it missed many fraudulent transactions.
- **Hyperparameter Tuning**: Adjusting parameters like `max_samples`, `n_estimators`, and `contamination` led to minimal improvements.
- **Threshold Adjustment**: Changing the decision threshold increased recall but significantly reduced precision and F1-score, leading to an unbalanced model.

## Solutions Implemented
- **Parameter Tuning**: Basic tuning of parameters such as `n_estimators` and `max_depth` was done to optimize the models.
- **Random Search for Parameter Optimization**: Applied to the Isolation Forest, but significant improvements were not observed, prompting a switch to supervised learning.
- **Supervised Learning Models**: Random Forest and XGBoost were chosen for comparison with Isolation Forest.
- **SMOTE (Synthetic Minority Over-sampling Technique)**: Applied to oversample the minority (fraudulent) class in the training set to address class imbalance.

## Results
### Isolation Forest
The Isolation Forest model initially performed poorly despite high accuracy:
- **Recall**: 0.28
- **Precision**: 0.31
- **F1-Score**: 0.30

Efforts to tune hyperparameters did little to improve the results, and using auto contamination increased recall but negatively impacted other metrics, making the model unreliable.

### Supervised Learning Results
Switching to Random Forest and XGBoost, both paired with SMOTE, resulted in significant improvements:
- **Random Forest + SMOTE**:
  - **Recall**: 0.83
  - **ROC-AUC**: 0.95
- **XGBoost + SMOTE**:
  - **Recall**: 0.84
  - **ROC-AUC**: 0.97

XGBoost + SMOTE outperformed the other models in detecting fraudulent transactions with high recall and ROC-AUC, indicating its superiority in this task.

### Confusion Matrix Analysis
The confusion matrix analysis was crucial for understanding how well the models distinguished between normal and fraudulent transactions:
- **Isolation Forest** had a significant number of False Negatives, indicating it struggled to detect fraud accurately.
- **Random Forest + SMOTE** reduced False Negatives, showing an improvement in fraud detection, but led to a slight increase in False Positives.
- **XGBoost + SMOTE** further reduced False Negatives while maintaining a reasonable number of False Positives, making it the best-performing model.

## Future Work
### Model Improvement
- **Apply Stacking Techniques**: Combine the strengths of Random Forest and XGBoost for further performance enhancement.

### Feature Engineering
- **Explore Additional Features**: Investigate transaction history patterns or customer demographics to improve fraud detection.

### Threshold Optimization
- **Detailed Threshold Optimization**: Fine-tune the balance between recall and precision for XGBoost.

### Class Imbalance
- **Alternative Sampling Techniques**: Investigate alternative oversampling or undersampling methods to handle class imbalance more effectively.

## Conclusion
In this project, we aimed to detect fraudulent transactions in a highly imbalanced dataset using various machine learning approaches. Initially, the unsupervised Isolation Forest method was applied but proved to be inadequate due to its low recall and high false negative rate. Transitioning to supervised learning models, specifically Random Forest and XGBoost combined with SMOTE, resulted in significant performance improvements. XGBoost with SMOTE emerged as the best-performing model, achieving high recall and ROC-AUC scores. Future improvements could involve stacking techniques, advanced feature engineering, and optimized threshold settings to further enhance fraud detection accuracy.

## License
This project is licensed under the MIT License - see the LICENSE file for details.
