# Gym-Retention-Prediction 


## Project Overview: Customer Churn Prediction for FitLife Gym

This project aims to predict customer churn for FitLife Gym, a growing chain of fitness centers. By analyzing historical membership data, the project seeks to identify patterns and predict which members are likely to leave. The objective is to help FitLife Gym reduce churn rates, increase customer lifetime value, and enhance member satisfaction through personalized engagement strategies.

## Dataset

The dataset used for this project contains information about gym members, their demographics, membership details, and gym usage patterns. The target variable is `Churn`, which indicates whether a member has churned (1 = Yes, 0 = No).

### Features
- `gender`: Gender of the member (1 = Male, 0 = Female)
- `Near_Location`: Whether the member lives near the gym (1 = Yes, 0 = No)
- `Partner`: Whether the member is an employee of a partner company (1 = Yes, 0 = No)
- `Promo_friends`: Whether the member joined through a promotion with friends (1 = Yes, 0 = No)
- `Phone`: Whether the member provided their phone number (1 = Yes, 0 = No)
- `Contract_period`: Length of the membership contract in months (e.g., 1, 6, or 12 months)
- `Group_visits`: Whether the member attended group classes (1 = Yes, 0 = No)
- `Age`: Age of the member in years
- `Avg_additional_charges_total`: Average total additional charges incurred by the member
- `Month_to_end_contract`: Number of months remaining until the membership contract ends
- `Lifetime`: Total number of months the member has been with the gym
- `Avg_class_frequency_total`: Member's average frequency of attending gym classes per week over their lifetime
- `Avg_class_frequency_current_month`: Member's average frequency of attending gym classes per week in the current month

## Project Workflow

The project follows the CRISP-DM methodology:

### 1. Business Understanding
Define the project goals and understand the business context to align the analysis with stakeholder needs.

### 2. Data Understanding
Explore and analyze the dataset to identify key features, relationships, and potential challenges such as missing values or data imbalances.

### 3. Data Preparation
Clean, transform, and preprocess the data to ensure it is ready for modeling, addressing issues like missing values, encoding, scaling, and data splits.

### 4. Modeling
Select and train appropriate algorithms to develop predictive models, optimizing performance through hyperparameter tuning and cross-validation.

### 5. Evaluation
Assess the model’s effectiveness using relevant metrics and ensure it meets the business objectives.

### 6. Deployment
Integrate the final model into production, enabling practical applications and ensuring continuous performance monitoring.

## Expected Results

| Algorithm | Data Balancing | Precision (1) | Recall (1) | F1-Score (1) | Train Acc | Test Acc | CV Acc | Δ (Train-Test) | Δ (Train-CV) | Overfitting Risk |
|-----------|---------------|---------------|-------------|--------------|-----------|-----------|---------|----------------|---------------|-----------------|
| LogReg | None | 0.81 | 0.81 | 0.81 | 0.89 | 0.90 | 0.91 | -0.01 | -0.02 | Low |
| LogReg | ROS | 0.85 | 0.90 | 0.87 | 0.88 | 0.87 | 0.86 | 0.01 | 0.02 | Low |
| LogReg | SMOTE | 0.89 | 0.94 | 0.91 | 0.91 | 0.91 | 0.90 | 0.00 | 0.01 | Low |
| SVM | None | 0.82 | 0.81 | 0.81 | 0.89 | 0.90 | 0.90 | -0.01 | -0.01 | Low |
| SVM | ROS | 0.84 | 0.91 | 0.87 | 0.89 | 0.87 | 0.85 | 0.02 | 0.04 | Low |
| SVM | SMOTE | 0.88 | 0.93 | 0.90 | 0.92 | 0.90 | 0.89 | 0.02 | 0.03 | Low |
| XGBoost | None | 0.77 | 0.76 | 0.77 | 0.99 | 0.88 | 0.88 | 0.11 | 0.11 | High |
| XGBoost | ROS | 0.90 | 0.98 | 0.94 | 0.99 | 0.93 | 0.87 | 0.06 | 0.12 | High |
| XGBoost | SMOTE | 0.90 | 0.93 | 0.91 | 0.99 | 0.91 | 0.88 | 0.08 | 0.11 | High |
| DecTree | None | 0.70 | 0.75 | 0.72 | 1.00 | 0.85 | 0.84 | 0.15 | 0.16 | Very High |
| DecTree | ROS | 0.89 | 0.99 | 0.94 | 1.00 | 0.93 | 0.84 | 0.07 | 0.16 | Very High |
| DecTree | SMOTE | 0.86 | 0.86 | 0.86 | 1.00 | 0.86 | 0.85 | 0.14 | 0.15 | Very High |
| RandFor | None | 0.82 | 0.78 | 0.80 | 1.00 | 0.89 | 0.88 | 0.11 | 0.12 | High |
| RandFor | ROS | 0.90 | 0.98 | 0.94 | 1.00 | 0.94 | 0.88 | 0.06 | 0.12 | High |
| RandFor | SMOTE | 0.89 | 0.91 | 0.90 | 1.00 | 0.90 | 0.89 | 0.10 | 0.11 | High |



---

## Key Findings

## Model Performance Summary

### Best Overall Models
- SMOTE-balanced Logistic Regression
  - Most stable performance (Train: 0.91, Test: 0.91, CV: 0.90)
  - Excellent balance of precision/recall for both classes
  - Minimal overfitting (Δ Train-Test: 0.00)

- ROS-balanced Random Forest
  - Highest test accuracy (0.94)
  - Strong class 1 metrics (Precision: 0.90, Recall: 0.98)
  - Moderate overfitting risk (Δ Train-Test: 0.06)

### Impact of Balancing
- **SMOTE Benefits**:
  - Improved minority class recall (+0.13 on average)
  - More stable cross-validation scores
  - Reduced overfitting in tree-based models

- **ROS Effects**:
  - Highest overall performance gains
  - Slightly more variance in predictions
  - Better recall but lower precision

### Overfitting Analysis
- **High Risk**: Decision Trees (Δ Train-Test > 0.14)
- **Moderate Risk**: XGBoost, Random Forest (Δ Train-Test: 0.06-0.11)
- **Low Risk**: Logistic Regression, SVM (Δ Train-Test < 0.02)

### Model-Specific Insights
- Tree-based models (Decision Tree, Random Forest, XGBoost)
  - Perfect training scores (1.00) indicate overfitting
  - Larger train-test accuracy gaps
  - Better performance with balanced datasets

- Linear models (Logistic Regression, SVM)
  - More stable across different data balancing techniques
  - Smaller train-test performance gaps
  - More consistent cross-validation scores



## Requirements

### Running Locally

To run this project locally on your machine:

1. **Clone the repository**:
    ```bash
    git clone https://github.com/LEAN-96/Gym-Retention-Prediction.git
    cd Gym-Retention-Prediction
    ```

2. **Set up a virtual environment**:

    Using `venv`:
    ```bash
    python3 -m venv env
    source env/bin/activate  # On Windows use `env\Scripts\activate`
    ```

    Or using `conda`:
    ```bash
    conda create --name ml-env python=3.11
    conda activate ml-env
    ```

3. **Install project dependencies**:
    Install all required Python packages by running:
    ```bash
    pip install -r requirements.txt
    ```

4. **Launch Jupyter Notebook**:
    Start Jupyter Notebook by running:
    ```bash
    jupyter notebook
    ```
    Open the notebook (`gym_retention_prediction.ipynb`) in your browser through the Jupyter interface.

### Running Online via MyBinder

For users who prefer not to install any software locally, you can run this notebook online using MyBinder.

Click the MyBinder button below to launch the notebook in an interactive environment:

[![Binder](https://mybinder.org/badge_logo.svg )](https://mybinder.org/v2/gh/LEAN-96/Gym-Retention-Prediction.git/HEAD?labpath=notebooks )

Once MyBinder loads:
1. Navigate to your notebook (`gym_retention_prediction.ipynb`) in the file browser on the left.
2. Click on the notebook file to open it.
3. Run all cells by selecting "Run All" from the "Cell" menu or pressing `Shift + Enter` for individual cells.

By using MyBinder, you can explore and execute all parts of this notebook without installing anything locally.


## Conclusion

This project successfully predicted customer churn for FitLife Gym using various machine learning algorithms. The results can help the gym proactively address member concerns, reduce churn rates, and enhance customer satisfaction. Future work could include exploring additional features, testing other algorithms, and deploying the model in a real-world environment to continuously monitor and improve its performance.




