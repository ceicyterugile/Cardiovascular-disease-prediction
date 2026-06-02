# 10-Year Coronary Heart Disease (CHD) Risk Prediction

## Project Overview & Objective
The primary objective of this project is to build and evaluate a Logistic Regression model to predict the 10-year risk of Coronary Heart Disease (CHD) in patients using clinical and behavioral data. 

Beyond standard model fitting, this project focuses on classification metric selection and optimal probability threshold tuning. In a healthcare predictive environment, selecting the default `0.5` decision threshold is rarely optimal; this pipeline programmatically shifts the threshold to align with clinical utility and patient-risk minimization.

## Dataset & Environmental Architecture
- **Data Source:** Framingham Cardiovascular Disease Dataset (Sourced from Kaggle).
- **Development Platform:** Google Colab Ecosystem (`.ipynb` architecture).
- **Core Features Analyzed:** Demographic attributes (Age, Male), behavioral indicators (currentSmoker, cigsPerDay), and physiological telemetry (totChol, sysBP, diaBP, BMI, heartRate, glucose).

## Requirements & Technical Pipeline
1. **Exploratory Data Analysis & Data Cleaning:** Handled structural null values, verified feature data types, and scaled numerical predictors.
2. **Predictive Modeling:** Fitted a Logistic Regression framework to map non-linear log-odds for the binary target variable (`TenYearCHD`).
3. **Metric Optimization Strategy:** Evaluated precision-recall curves and ROC-AUC curves to move past basic accuracy scores.

## Classification Metric Selection & Threshold Optimization

### 1. The Chosen Metric: Recall (Sensitivity)
- **Strategic Argumentation:** In medical diagnostic modeling for life-threatening conditions like CHD, **Recall (Sensitivity)** is prioritized as the primary metric. 
- **The Rationale:** A **False Negative** (predicting a patient is safe when they are actually at high risk of heart disease) is catastrophically dangerous, as it leads to a total denial of life-saving preventative treatment. A **False Positive** (predicting a high risk for a healthy patient) merely triggers follow-up clinical testing or lifestyle changes, representing a minor cost compared to a missed diagnosis.

### 2. Threshold Calibration Methodology
- To maximize Recall while maintaining an acceptable baseline of overall model Precision, the decision threshold was programmatically lowered away from the standard `0.5` mark. 
- **Outcome:** Shifting the threshold downwards allows the model to catch significantly more positive instances of high risk, successfully optimizing the safety parameters of the clinical system.

---

##  Repository Contents
- `chd_risk_prediction.ipynb`: The complete, fully documented Google Colab notebook containing all Python code, Logistic Regression outputs, and metric evaluations.
