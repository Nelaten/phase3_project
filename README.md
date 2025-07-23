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

The dataset used is derived from the **Telco Customer Churn dataset**, a public dataset that captures customer profiles over multiple attributes. It includes:

- **Demographic Variables**: Gender, SeniorCitizen, Partner, Dependents  
- **Service Subscriptions**: PhoneService, InternetService, StreamingTV, etc.  
- **Account Information**: Contract type, PaperlessBilling, PaymentMethod, Tenure, MonthlyCharges, TotalCharges  
- **Churn Label**: Indicates whether a customer left within the last month

The dataset consists of over 7,000 observations with a mix of categorical and numerical features. These variables provide a rich base for understanding churn behavior.

---

## 3. Model

### Approach

A **Logistic Regression** model was selected due to its balance of simplicity, interpretability, and strong performance in binary classification problems. The approach followed these key steps:

1. **Data Cleaning**:
   - Removed rows with missing or invalid entries (e.g., blank TotalCharges).
   - Converted categorical variables into numeric form using one-hot encoding.

2. **Feature Engineering**:
   - Created derived variables where relevant (e.g., tenure groups).
   - Standardized numerical features to bring them to a common scale.

3. **Train-Test Split**:
   - The dataset was split into 80% training and 20% testing to evaluate generalization.

4. **Model Training**:
   - Used scikit-learn’s LogisticRegression with default parameters and L2 regularization.

5. **Threshold Analysis**:
   - Explored different probability thresholds for optimal decision boundary.

---

## 4. Evaluation

The performance of the logistic regression model was evaluated using several key metrics:

### ✅ ROC Curve & AUC
- The **ROC curve** visualized the trade-off between sensitivity (TPR) and specificity (1 - FPR).
- The **AUC score of 0.8053** shows strong model discrimination ability between churners and non-churners.

### ✅ Confusion Matrix
Provided insight into the number of:
- **True Positives** (correct churn predictions),
- **True Negatives** (correct non-churn predictions),
- **False Positives** (incorrect churn predictions),
- **False Negatives** (missed churners).

### ✅ Classification Report
- **Precision**: How many predicted churns were actual churns.
- **Recall**: How many actual churns were correctly predicted.
- **F1-Score**: Harmonic mean of Precision and Recall.
- These scores indicated a balanced performance, with a slight trade-off to minimize false negatives (missed churners).

### ✅ Interpretability
Feature coefficients from logistic regression revealed which features influenced churn:
- Contract Type and Tenure were among the most influential.
- Monthly Charges and Internet Service also had strong predictive power.

---

## 5. Conclusion

This project successfully demonstrates that **Logistic Regression** can be an effective baseline model for churn prediction, with good interpretability and actionable insights.

**Key Takeaways**:
- Contract length, monthly charges, and internet service type are strong churn predictors.
- Logistic Regression offers sufficient predictive accuracy (AUC = 0.8053) and transparency.
- The model can be a useful tool in guiding customer retention efforts and decision-making.

---

## 🔍 Recommendations

1. **Enhance Data Collection**: Capture additional behavioral data such as usage patterns, customer support interactions, and satisfaction scores to improve prediction accuracy.

2. **Segmented Retention Campaigns**: Use model predictions to tailor engagement strategies for high-risk groups, especially month-to-month contract holders and high bill customers.

3. **Model Improvement**:
   - Experiment with ensemble methods (Random Forest, XGBoost) for higher accuracy.
   - Explore feature selection or dimensionality reduction for performance optimization.

4. **Deploy and Monitor**:
   - Deploy the model into a production environment (e.g., integrated into a CRM system).
   - Continuously monitor performance and retrain the model with new data.

5. **Customer Lifetime Value Integration**:
   - Combine churn prediction with customer lifetime value (CLV) modeling to prioritize intervention efforts on high-value customers.

---

