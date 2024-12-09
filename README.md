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

## Results

The key findings and results of the project are summarized below:

- **Logistic Regression**: Achieved an accuracy of XX% with precision and recall scores of YY% and ZZ%, respectively.
- **Decision Tree**: Achieved an accuracy of XX% with precision and recall scores of YY% and ZZ%, respectively.
- **Random Forest**: Achieved an accuracy of XX% with precision and recall scores of YY% and ZZ%, respectively.
- **SVM**: Achieved an accuracy of XX% with precision and recall scores of YY% and ZZ%, respectively.
- **XGBoost**: Achieved an accuracy of XX% with precision and recall scores of YY% and ZZ%, respectively.



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




