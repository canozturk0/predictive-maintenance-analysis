# Predictive Maintenance: Machine Failure Prediction

## Project Overview

This project focuses on predicting industrial machine failures using sensor data and machine learning techniques.

The main objective is to explore machine operating conditions, identify patterns associated with machine failures, and compare different classification algorithms.

The project was developed using Python and the UCI AI4I 2020 Predictive Maintenance Dataset.

## Dataset

**Source:** UCI Machine Learning Repository – AI4I 2020 Predictive Maintenance Dataset

- Total observations: 10,000
- Total columns: 14
- Target variable: `Machine failure`
- Machine failure cases: 339 (3.39%)
- Normal operating cases: 9,661 (96.61%)

The dataset contains machine operating measurements, including:

- Air temperature
- Process temperature
- Rotational speed
- Torque
- Tool wear
- Product type

The dataset is synthetic and was designed to represent predictive maintenance scenarios.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Project Workflow

The project consists of the following steps:

1. Data loading and inspection
2. Data quality assessment
3. Exploratory data analysis (EDA)
4. Descriptive statistics and data visualization
5. Correlation analysis
6. Feature preparation and encoding
7. Train-test splitting
8. Machine learning model development
9. Model evaluation and comparison
10. Feature importance analysis

Failure-mode indicators were excluded from the predictor variables to prevent data leakage.

The dataset was divided into training (80%) and testing (20%) sets using stratified sampling.

## Machine Learning Models

Three classification algorithms were implemented:

- Logistic Regression
- Decision Tree
- Random Forest

Class weighting was used to address the imbalance between normal operating cases and machine failures.

Standardization was applied to Logistic Regression through a Scikit-learn pipeline.

## Model Performance

The models were evaluated using Accuracy, Precision, Recall, F1-Score, ROC-AUC, and PR-AUC.

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC | PR-AUC |
|---|---:|---:|---:|---:|---:|---:|
| Logistic Regression | 0.8245 | 0.1418 | 0.8235 | 0.2419 | 0.9070 | 0.3817 |
| Decision Tree | 0.9365 | 0.3314 | 0.8529 | 0.4774 | 0.8762 | 0.5465 |
| Random Forest | 0.9760 | 0.6429 | 0.6618 | 0.6522 | 0.9588 | 0.7040 |

Random Forest achieved the highest overall F1-Score, ROC-AUC, and PR-AUC.

However, Decision Tree achieved the highest recall, detecting 58 out of 68 actual machine failures.

This comparison demonstrates the importance of considering false alarms and missed failures when selecting a predictive maintenance model.

## Key Findings

- Machine failures represent only 3.39% of the dataset.
- Random Forest achieved the strongest overall performance across several evaluation metrics.
- Decision Tree detected more actual failures than the other models.
- Torque, rotational speed, and tool wear were the three most important features in the Random Forest model.
- Feature importance reflects predictive contribution, not causation.

## Limitations

- The dataset is synthetic and may not fully represent real industrial conditions.
- The target variable is highly imbalanced.
- Model performance may differ when applied to real-world industrial data.
- The models were evaluated using a single train-test split.
- Feature importance does not establish causal relationships.

## References

1. Matzka, S. (2020). *Explainable Artificial Intelligence for Predictive Maintenance Applications*. AI4I 2020. DOI: 10.1109/AI4I49448.2020.00023.

2. UCI Machine Learning Repository. (2020). *AI4I 2020 Predictive Maintenance Dataset*. DOI: 10.24432/C5HS5C.

3. McKinney, W. (2010). *Data Structures for Statistical Computing in Python*.

4. Harris, C. R., et al. (2020). *Array Programming with NumPy*. Nature, 585, 357–362.

5. Hunter, J. D. (2007). *Matplotlib: A 2D Graphics Environment*. Computing in Science & Engineering, 9(3), 90–95.

6. Waskom, M. L. (2021). *seaborn: Statistical Data Visualization*. Journal of Open Source Software, 6(60), 3021.

7. Pedregosa, F., et al. (2011). *Scikit-learn: Machine Learning in Python*. Journal of Machine Learning Research, 12, 2825–2830.
