# ZENVY: Payroll Risk Scoring System

## Overview
ZENVY is a predictive analytics project designed to identify high-risk records in payroll systems. By analyzing employee attendance patterns, leave frequencies, performance ratings, and salary fluctuations, the system helps organizations proactively detect potential irregularities or risks in their payroll processing.

## Project Structure
- `Data.ipynb`: The main Jupyter Notebook containing the end-to-end data science workflow (EDA, Preprocessing, Modeling).
- `payroll_raw.csv`: Raw dataset containing 54,500 employee records and payroll metrics.

## Key Features
- **Data Preprocessing**: Automated handling of missing values using median/mode and removal of duplicate records.
- **Categorical Encoding**: Transformation of categorical variables like Department and Gender into numerical formats.
- **Feature Engineering**:
  - **Attendance Rate**: Calculates the ratio of actual working days to scheduled days.
  - **Leave Frequency**: Measures the density of leaves taken over the employee's tenure.
  - **Salary Change Percentage**: Tracks the growth or decline in salary relative to the previous baseline.
- **Exploratory Data Analysis (EDA)**: Comprehensive visualization of risk factors using boxplots to compare attendance, leaves, performance, and salary against risk labels.
- **Machine Learning Models**:
  - Logistic Regression
  - Random Forest Classifier
  - XGBoost Classifier

## Methodology
The project follows a systematic data science pipeline:
1. **Data Loading**: Importing the raw payroll dataset.
2. **Cleaning**: Dropping duplicates and imputing missing numerical values with medians.
3. **Encoding**: Applying Label Encoding to categorical features.
4. **Feature Engineering**: Creating derived metrics that are strong indicators of payroll risk.
5. **Visualization**: Identifying correlations and distributions through multi-plot grids.
6. **Model Training**: Dividing data into training and testing sets with stratified sampling.
7. **Cross-Model Comparison**: Evaluating models based on Accuracy and F1-Score to determine the most effective approach for imbalanced risk data.

## Justification for Model Selection
Mathematical analysis shows that decision-tree-based models (Random Forest and XGBoost) are superior for this domain. Payroll risk often follows overlapping logical thresholds (e.g., *low attendance* combined with *high leave frequency*), which are best captured by the **Information Gain** and recursive partitioning logic of tree models.

## How to Run
1. Ensure you have the following Python libraries installed:
   - `pandas`
   - `numpy`
   - `matplotlib`
   - `seaborn`
   - `scikit-learn`
   - `xgboost`
2. Open `Data.ipynb` in a Jupyter environment.
3. Execute the cells sequentially to reproduce the analysis and model results.


