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

![image](https://github.com/user-attachments/assets/6fb6648e-40b9-4d47-a760-6209888dddb3)

## Expected Results


### 4.5 Comparison of Algorithm Performance

| Algorithm          | Data Balancing | Precision (1) | Recall (1) | F1-Score (1) | AUC Score | Train Acc | Test Acc | Δ (Train-Test) | Overfitting Risk |
|--------------------|----------------|---------------|------------|--------------|-----------|-----------|----------|----------------|------------------|
| Logistic Regression | ROS            | 69%           | 91%        | 78%          | 0.9564    | 88%       | 86%      | 2%             | Low              |
| Decision Trees      | ROS            | 67%           | 91%        | 77%          | 0.9330    | 88%       | 85%      | 3%             | Low              |
| Random Forest       | ROS            | 75%           | 86%        | 80%          | 0.9529    | 96%       | 89%      | 7%             | Moderate         |
| XGBoost             | ROS            | 75%           | 81%        | 78%          | 0.9444    | 99%       | 88%      | 11%            | High             |

---

#### Key Findings

1. **Logistic Regression**: Logistic Regression achieved a test accuracy of 86%, with high recall (91%) for identifying churners but lower precision (69%), indicating a tendency to misclassify non-churners as churners. It demonstrated good generalization with minimal overfitting and identified `Lifetime` and `Avg_class_frequency_current_month` as the most influential features.Its AUC score of 0.9564 is the highest among all models, confirming its strong ability to distinguish between churners and non-churners.

2. **Decision Trees**: Decision Trees achieved a test accuracy of 85%, with strong recall (91%) for churners but reduced precision (67%). The model showed mild overfitting, with `Lifetime`, `Month_to_end_contract`, and `Avg_class_frequency_current_month` emerging as the key predictors of churn. Its AUC score of 0.9330 is the lowest among the models, reflecting its slightly weaker ability to separate classes compared to others.

3. **Random Forest**: Random Forest outperformed Logistic Regression and Decision Trees with a test accuracy of 89%. It balanced precision (75%) and recall (86%) for churners, demonstrating good generalization with moderate overfitting. Feature importance analysis reinforced the dominance of `Lifetime`, followed by `Avg_class_frequency_current_month` and `Month_to_end_contract`. Its AUC score of 0.9529 is the second-highest, indicating excellent class separation and reinforcing its strong performance.


4. **XGBoost**: XGBoost achieved the highest training accuracy (99%) but exhibited overfitting, with test accuracy dropping to 88%. While recall for churners remained strong at 81%, precision was 75%, similar to Random Forest. The model identified `Lifetime` as the most critical predictor, followed by `Month_to_end_contract`. Its AUC score of 0.9444 is competitive, but the overfitting risk limits its reliability despite its strong class separation capability.

#### Conclusion

Random Forest emerged as the best-performing model due to its balance between accuracy, precision, recall, and generalization capability. While XGBoost delivered competitive performance, its higher overfitting risk limits its reliability without further tuning. Despite Logistic Regression having the highest AUC score, its lower precision makes it less suitable for practical deployment compared to Random Forest. Overall, Random Forest is recommended for predicting customer churn, supported by actionable insights from feature importance analysis and its strong AUC score.




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

This project successfully predicted customer churn for FitLife Gym using various machine learning algorithms. The results can help the gym proactively address member concerns, reduce churn rates, and enhance customer satisfaction. Deployment, a critical phase of the CRISP-DM lifecycle, exceeded the scope of this project but remains essential for production environments. Future research should explore modeling without data balancing to evaluate the impact of imbalanced datasets on performance. Additionally, applying data balancing techniques such as SMOTE (Synthetic Minority Oversampling Technique) and comparing results with no balancing will provide deeper insights into their effectiveness. Parameter optimization using Grid Search should also be conducted to fine-tune hyperparameters and reduce overfitting (e.g. XGBoost). Incorporating pipelines for efficient model training and evaluation will streamline workflows and reduce redundancy. Finally, expanding the scope to include advanced algorithms like deep learning will enable a comparison of traditional machine learning models with neural network-based approaches.



