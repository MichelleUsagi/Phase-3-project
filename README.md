# EARLY DETECTION OF DIABETES

## Project Overview

This project aims to build and evaluate predictive models to detect early onset diabetes using health-related features such as glucose level, BMI, age, and insulin. 

The project compares multiple machine learning models, applies preprocessing and regularization, and prioritizes model interpretability and recall.This ensures the best chance of identifying at-risk patients early.

## Objectives
-How accurately can our model predict diabetes in a patient?
- What is the model's general ability to differentiate between diabetic and non-diabetic patients?
-  What are the specific strengths and weaknesses of the model's predictions for each patient group?
## Stakeholder Benefit

This model can assist primary care physicians and insurance providers in early detection of at-risk patients, allowing for early intervention and cost-effective treatment planning.

## Dataset

The dataset used is the **Pima Indians Diabetes Dataset**, which includes features such as:
- Glucose
- BMI
- Age
- Insulin
- Skin Thickness
- Blood Pressure
- Diabetes Pedigree Function
- Outcome (target: 1 for diabetic, 0 for non-diabetic)

## Preprocessing Steps
1. **Missing Values** - replaced with the median.
2. **Skewed Feature Transformation**:
   - Log-transform - 'insulin', 'SkinThickness', and 'DiabetesPedigreeFunction'.
3. **Scaling** with StandardScaler.
4. **Train-Test Split** (80/20 with stratification on `Outcome`).

## Models Used
Logistic Regression - GridSearchCV ('C', 'penalty') 
Decision Tree - GridSearchCV ('depth', 'leaf')

##  Evaluation Metrics

- **Accuracy**: Overall prediction correctness.
- **Recall (Sensitivity)**: Ability to identify diabetic patients correctly.
- **Confusion Matrix**: Visual inspection of true/false positives and negatives.
- **Classification Report**: Full metrics (Precision, Recall, F1-score).

---

## Results

| Model                | Accuracy | Recall |
|---------------------|----------|--------|
| Logistic Regression | 0.73     | 0.72   |
| Decision Tree       | 0.75     | 0.85  |

## Interpretation
- **Logistic Regression** is highly interpretable and was improved using L1/L2 regularization.
- **Decision Tree** was easy to explain, but prone to overfitting without depth control.

## Key Insights

- **Glucose** and **BMI** were the most influential predictors.
- Feature transformation and regularization significantly improved model performance.
- Choosing a model with **high recall** is essential in medical settings to minimize false negatives.

# Recommendations and conclusions
1. How accurately can our model predict diabetes in a patient?
Conclusion: The tuned Decision Tree model demonstrated an 85% recall rate in identifying true diabetic cases, alongside an overall accuracy of 75%.
Recommendation: It is recommended to proceed with the tuned Decision Tree model. Its superior recall in identifying true diabetic cases makes it the most suitable choice for an early detection system where minimizing missed diagnoses is paramount.

2. What is the model's general ability to differentiate between diabetic and non-diabetic patients?
Conclusion: Both models showed strong discriminatory power, evidenced by an AUC of 0.81.
Recommendation: Further efforts should focus on fine-tuning the Decision Tree's classification threshold to optimally balance false positives and false negatives based on their specific costs in a real-world clinical setting.

3. What are the specific strengths and weaknesses of the model's predictions for each patient group?
Conclusion: The Decision Tree's strength lies in its high recall for the diabetic group. However, a weakness is a slightly higher rate of false positives in the non-diabetic group.
Recommendation: To enhance the model's overall utility, it is recommended to strategically address the Decision Tree's tendency for slightly higher false positives in the non-diabetic group. This could involve exploring techniques to improve precision without compromising the vital recall for diabetic patients.



