# EARLY DETECTION OF DIABETES

## Project Overview

This project aims to build and evaluate predictive models to detect early onset diabetes using health-related features such as glucose level, BMI, age, and insulin. 

The project compares multiple machine learning models, applies preprocessing and regularization, and prioritizes model interpretability and recall.This ensures the best chance of identifying at-risk patients early.

## Objectives

- Can we predict whether a patient is likely to develop diabetes using health-      related features such as glucose, BMI, and age?
-Which features have the greatest influence on diabetes prediction, and how can    we interpret their impact?
-Can we improve predictive performance by tuning a decision Tree Classifier, and   how does it compare to a simple baseline model?

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
- **Decision Tree** was easy to explain but prone to overfitting without depth control.

## Key Insights

- **Glucose** and **BMI** were the most influential predictors.
- Feature transformation and regularization significantly improved model performance.
- Choosing a model with **high recall** is essential in medical settings to minimize false negatives.

#


