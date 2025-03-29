# Heart-Disease-Risk-Assessment-
# Heart Disease Prediction and Explainability

## Overview
This project aims to predict heart disease using an **ensemble machine learning model** while providing model interpretability through **LIME** and **SHAP** explanations. The dataset used is the **Heart Disease UCI dataset**, which includes various clinical attributes used to diagnose the presence of heart disease.

Our pipeline follows these key steps:
- **Data preprocessing**: Handling missing values, feature scaling, and dataset splitting.
- **Model training**: Building an ensemble model using Logistic Regression, Random Forest, and Gradient Boosting.
- **Evaluation**: Measuring accuracy, precision, recall, F1-score, and visualizing confusion matrices.
- **Interpretability**: Explaining model decisions using LIME and SHAP.

---

## Dataset
The dataset contains clinical attributes such as **age, cholesterol levels, resting blood pressure, exercise-induced angina, maximum heart rate, and more.** The target variable indicates whether a patient has heart disease (**1: Disease, 0: No Disease**).

---

## Model Selection
We use a **VotingClassifier** to combine the strengths of three models:
- **Logistic Regression**: A simple and interpretable linear model.
- **Random Forest Classifier**: A robust, tree-based model that captures complex patterns.
- **Gradient Boosting Classifier**: A powerful boosting algorithm improving prediction accuracy.

The ensemble model achieves **higher accuracy** and **better generalization** compared to individual models.

---

## Model Performance
### **Accuracy and Classification Report**
- **Overall Accuracy**: **96.59%** on the test set.
- **Precision, Recall, and F1-score**: Scores are high (~0.95 to 0.98), demonstrating strong predictive performance.

### **Confusion Matrix**
|         | Predicted No Disease | Predicted Disease |
|---------|----------------------|-------------------|
| **Actual No Disease** | 98                   | 2                 |
| **Actual Disease**    | 5                    | 100               |

This shows that the model has **high precision and recall**, with minimal misclassifications.

---

## Model Explainability
### **LIME (Local Interpretable Model-agnostic Explanations)**
LIME provides an **interpretable breakdown** of how individual predictions are made. It identifies the most **influential features** for a single prediction.

**Key findings from LIME:**
- **Feature importance**: Attributes like **thalach (maximum heart rate), thal, and oldpeak** had the highest impact.
- **Probability Distribution**: The model predicted a probability of **0.57 for No Disease** and **0.43 for Disease** in an example case.

### **SHAP (SHapley Additive exPlanations)**
SHAP provides a **global explanation** of the model's behavior, showing the contribution of each feature to the final prediction.

**Key findings from SHAP:**
- The **base probability** (expected value) was **0.55**, meaning the model is naturally inclined to predict a balanced probability.
- **Features contributing to disease risk** (red in SHAP force plot):
  - Some attributes like **thal, oldpeak, and cp (chest pain type)** increased the probability of predicting disease.
- **Features reducing disease risk** (blue in SHAP force plot):
  - Other features like **restecg and exercise-induced angina** lowered the risk prediction.

The SHAP force plot visualizes how each feature influences the final decision, making the model's predictions more transparent.

---
##Model Testing On unseen data 
I extract 2 rows from the provided data then i test the model on this data without the target the model predict the 2 rows coorectly where the prediction 
and the probaility were saved in predictions_testingheart.csv 
---
## Conclusion
This project successfully demonstrates a **highly accurate ensemble model** for heart disease prediction. More importantly, it showcases **explainability techniques** to make the model’s decisions **transparent and interpretable**, which is essential for **medical applications** where trust in AI models is crucial.

### **Key Takeaways:**
✅ **High accuracy** (96.59%) with minimal false predictions.  
✅ **LIME explanations** reveal which features influence a specific prediction.  
✅ **SHAP analysis** provides a global and local understanding of feature importance.  
✅ **Ensemble learning** improves model robustness and generalization.  

This project can be further expanded by testing **additional models**, incorporating **deep learning approaches**, or adding **feature engineering** techniques for improved performance.

---



