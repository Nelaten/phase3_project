# 📊 Customer Churn Prediction using Logistic Regression

## 1. Overview

Customer churn remains one of the most critical challenges in subscription-based industries. Predicting churn early gives organizations a competitive edge in implementing customer retention strategies. 

This project presents a supervised machine learning approach to **predicting customer churn** in a telecom company using **Logistic Regression**. The model aims to classify customers who are likely to churn (leave) the service, based on their demographic and service usage attributes. The resulting model is evaluated using key classification metrics and is intended to guide stakeholders in developing proactive customer engagement strategies.

---

## 2. Business and Data Understanding

### Business Problem

Customer churn directly affects profitability. Losing a customer often costs more than retaining one. For a telecom company, understanding what drives churn enables:
- **Retention strategy optimization**
- **Improved customer experience**
- **Efficient resource allocation**

### Target Stakeholders

- **Customer Retention Teams**: To proactively engage high-risk customers.
- **Marketing Department**: For targeted promotional offers and loyalty programs.
- **Data Analysts and Scientists**: For ongoing monitoring and model refinement.
- **Senior Management**: For strategic decisions on customer lifecycle management.

### Dataset Description

The dataset used is derived from the **Kaggle**, and it is a public dataset that captures customer profiles over multiple attributes. It includes:

- **International subscription plan**: Total charges and minutes
- **Voice-mail Subscription plan**: Total charges and minutes
- **Customer service calls**: Total number of calls, and freqency 
- **Churn Label**: Indicates whether a customer left or not

The dataset consists of over 3,333 observations with a mix of categorical and numerical features. These variables provide a rich base for understanding churn behavior.

---

## 3. Model

### Approach

A **Logistic Regression** model was selected due to its balance of simplicity, interpretability, and strong performance in binary classification problems. The approach followed these key steps:

1. **Data Cleaning**:
   - Checking the general structure and general information of the dataset.
   - Checking for duplicate variables and dropping irrelevant columns.
   - Converted categorical variables into numeric form using one-hot encoding.

2. **Feature Engineering**:
   - Checking the distribution of categorical variables and also numerical variables.
   - Standardized numerical features to bring them to a common scale.
   - Did a correlation analysis to identify relevant features.

3. **Train-Test Split**:
   - The dataset was split into 75% training and 25% testing to evaluate generalization.

4. **Model Training**:
   - Used scikit-learn’s LogisticRegression with default parameters and L2 regularization.
   - Used also random forest classifier as it is an ensemble model that is used to build many decision trees and combines their outputs.
   - Use of smote to adjust for class imbalance.

5. **Threshold Analysis**:
   - Explored different probability thresholds for optimal decision boundary.

---

## 4. Evaluation

The performance of the logistic regression model was evaluated using several key metrics:

### ✅ ROC Curve & AUC
- The **ROC curve** visualized the trade-off between sensitivity (TPR) and specificity (1 - FPR).
- The **AUC score of 0.8053** shows strong model discrimination ability between churners and non-churners.


### ✅ Classification Report
- **Precision**: For the logistic regression model only 31% churns were actual churns, and for the random forest classifier only 97% were correct.
- **Recall**: Amazingly the random forest classifier correctly identified 60% of actual churners, while for the logistic regression only 73% of the churns were correctly predicted.
- **F1-Score**: For the logistic regression it showed a 0.81 balance score, which is quite a good score. 
- These scores indicated a balanced performance, with a slight trade-off to minimize false negatives (missed churners).

### ✅ Interpretability
Feature coefficients from logistic regression revealed which features influenced churn:
- International plan, total international minutes and total day minutes were among the most influential.


---

## 5. Conclusion

This project successfully demonstrates that **Logistic Regression** can be an effective baseline model for churn prediction, with good interpretability and actionable insights, but we were able to see the difference between it and the **Random forest** which indeed has better predictive ability as a model.

**Key Takeaways**:
- International plan, total international minutes, and total day minutes are strong churn predictors.
- Logistic Regression offers sufficient predictive accuracy (AUC = 0.8053) and transparency, but Random forest performed significantly better and developed and AUC of 0.9329
- The Random forest classifier model can be a useful tool in guiding customer retention efforts and decision-making.

---

## 🔍 Recommendations

1. **Enhance Data Collection**: Capture additional behavioral data such as usage patterns, customer support interactions, and satisfaction scores to improve prediction accuracy.

2. **Segmented Retention Campaigns**: Use model predictions to tailor engagement strategies for high-risk groups, especially month-to-month contract holders and high bill customers.

3. **Model Improvement**:
   - Experiment more with ensemble methods (Random Forest, XGBoost) for higher accuracy.
   - Explore feature selection or dimensionality reduction for performance optimization.

4. **Deploy and Monitor**:
   - Deploy the model into a production environment (e.g., integrated into a CRM system).
   - Continuously monitor performance and retrain the model with new data.

5. **Customer Lifetime Value Integration**:
   - Combine churn prediction with customer lifetime value (CLV) modeling to prioritize intervention efforts on high-value customers.

---

