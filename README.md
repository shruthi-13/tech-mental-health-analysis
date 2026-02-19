# Mental Health in Tech – Analysis & Modeling using Python

## Table of Contents
- [Project Overview](#project-overview)
- [Problem Statement](#problem-statement)
- [Motivation](#motivation)
- [Dataset](#dataset)
- [Preprocessing & Cleaning](#preprocessing--cleaning)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Modeling](#modeling)
  - [Regression](#regression)
  - [Classification](#classification)
  - [Hyperparameter Tuning](#hyperparameter-tuning)
- [Visualizations](#visualizations)
- [Tools & Libraries](#tools--libraries)
- [Key Insights](#key-insights)
- [Repository Structure](#repository-structure)
- [Usage](#usage)
- [License](#license)

## Project Overview
This project analyzes survey data from tech professionals to explore factors influencing mental health issues and whether they seek treatment. Predictive models are built to identify key indicators and support early intervention strategies.

## Problem Statement
Identify factors influencing whether a tech professional develops mental health issues and seeks treatment.

## Motivation
- The tech industry is known for high stress and burnout.  
- Early identification of mental health risk factors helps employers design better wellness programs and interventions.


## Dataset
**Source:** OSMI Mental Health in Tech Survey  
**Description:** Survey of tech professionals including demographic, workplace, and mental health-related information.  
**Columns Include:**  
`Age, Gender, family_history, treatment, work_interfere, no_employees, remote_work, tech_company, benefits, care_options, wellness_program, seek_help, anonymity, leave, mental_health_consequence, phys_health_consequence, coworkers, supervisor, mental_health_interview, phys_health_interview, mental_vs_physical, obs_consequence, comments`


## Preprocessing & Cleaning
- Dropped unnecessary columns: `Timestamp, state, comments, self_employed, Country`  
- Filled missing values for `work_interfere` with `"Don't know"`  
- Standardized `Gender` to `Male`, `Female`, `Other`  
- Filtered invalid `Age` values (0–100) and removed duplicates  
- Encoded categorical columns using `LabelEncoder`  
- Converted `treatment` to binary target for classification and probability target for regression

## Exploratory Data Analysis (EDA)
- Visualized distributions of key features  
- Analyzed correlations between workplace factors and mental health treatment  
- Explored demographic trends, work interference, and employee counts

## Modeling

### Regression
- **Target:** `treatment_prob` (probability of seeking treatment)  
- **Models Used:** Linear Regression, Decision Tree Regressor, Random Forest Regressor  
- **Performance:** Decision Tree and Random Forest achieved R² = 1.0 (overfitting indication)  

### Classification
- **Target:** `treatment` (Yes = 1, No = 0)  
- **Models Used:** Logistic Regression, Decision Tree Classifier, Random Forest Classifier  
- **Best Accuracy:**  
  - Logistic Regression: 0.792  
  - Decision Tree: 0.784  
  - Random Forest: 0.80  
- Confusion matrices and evaluation metrics (Precision, Recall, F1-Score) used for assessment

### Hyperparameter Tuning
- **Method:** `GridSearchCV` for Decision Tree Classifier  
- **Best Parameters:**  
```python
{'criterion': 'entropy', 'max_depth': 5, 'max_features': None,
 'min_samples_leaf': 4, 'min_samples_split': 2}
```
Best Cross-Validated Accuracy: 0.814
---

## Visualizations
- Confusion matrices for classification models  
- Decision Tree visualizations showing feature splits and feature importance

## Tools & Libraries
- Python 3.x  
- pandas, numpy  
- matplotlib, seaborn  
- scikit-learn (preprocessing, modeling, evaluation)

## Key Insights
- Workplace size, family history, and work interference are strong indicators of whether a professional seeks treatment  
- Decision Trees and Random Forests can overfit regression targets if not carefully tuned  
- Logistic Regression provides a simple and interpretable model for classification

## Repository Structure
## Repository Structure

Mental-Health-Tech/
│
├── Final.ipynb                # Jupyter notebook containing full analysis and modeling workflow
└── README.md                  # Project documentation

## Usage
Clone the repository:
```bash
git clone https://github.com/shruthi-13/shruthi-13.git

## Dataset

This project uses the **OSMI Mental Health in Tech Survey** dataset, which contains survey responses from tech professionals about mental health.  
You can download the data from the following public sources:

- **Kaggle (2014 version):** https://www.kaggle.com/osmihelp/osmi-mental-health-in-tech-survey  
- **Mendeley Data (2017–2021 compiled version):** https://data.mendeley.com/datasets/mmnzx4w8cg/1



