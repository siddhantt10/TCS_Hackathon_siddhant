## TCS_Hackathon_siddhant

# Credit Risk Prediction using Machine Learning

This repository contains Python code to predict credit risk for loan applicants using the German Credit dataset. The project utilizes machine learning techniques, specifically Random Forest and XGBoost classifiers, to classify applicants into high-risk and low-risk categories based on their financial and personal attributes.

## Dataset

The German Credit dataset consists of 1000 entries with 20 categorical and numeric attributes. For this project, the dataset has been preprocessed and simplified to focus on the following attributes:

- **Age**: Numeric value representing the age of the applicant.
- **Sex**: Categorical variable ('male', 'female').
- **Job**: Numeric variable representing job categories (0 - unskilled and non-resident, 1 - unskilled and resident, 2 - skilled, 3 - highly skilled).
- **Housing**: Categorical variable indicating housing status ('own', 'rent', 'free').
- **Saving Accounts**: Categorical variable indicating savings level ('little', 'moderate', 'quite rich', 'rich').
- **Checking Account**: Numeric variable indicating checking account balance in Deutsch Mark (DM).
- **Credit Amount**: Numeric variable indicating the amount of credit requested in DM.
- **Duration**: Numeric variable indicating the duration of the credit in months.
- **Purpose**: Categorical variable indicating the purpose of the credit ('car', 'furniture/equipment', 'radio/TV', 'domestic appliances', 'repairs', 'education', 'business', 'vacation/others').
- **Risk**: Target variable created based on 'Credit Amount' and 'Duration', indicating high-risk (1) or low-risk (0).

## Approach

### 1. Data Loading and Initial Exploration

- **Library Imports**: Import necessary libraries such as Pandas, kagglehub, and KaggleApi.
- **Dataset Download**: Use kagglehub or KaggleApi to download the "German Credit" dataset from Kaggle and load it into a Pandas DataFrame (`df`).
- **Initial Data Inspection**: Utilize `df.head()`, `df.info()`, and `df.isnull().sum()` to view the data, understand its structure, and handle missing values.

### 2. Data Preprocessing

- **Handling Missing Values**: Fill missing values in 'Saving Accounts' and 'Checking Account' with 'unknown'.
- **Encoding Categorical Features**: Convert categorical columns like 'Sex', 'Housing', etc., into numerical representations using Label Encoding.
- **Scaling Numerical Features**: Scale numerical features like 'Age', 'Credit Amount', and 'Duration' using StandardScaler to normalize their range.

### 3. Target Variable Definition

- **Risk Classification**: Create a new target variable 'Risk' based on the median values of 'Credit Amount' and 'Duration'. If 'Credit Amount' is above the median and 'Duration' is below the median, set 'Risk' to 1; otherwise, set it to 0.

### 4. Model Training and Evaluation (Random Forest)

- **Data Splitting**: Split the dataset into training and testing sets using train_test_split.
- **Model Initialization and Training**: Initialize a RandomForestClassifier and train it on the training data.
- **Model Evaluation**: Evaluate the RandomForestClassifier on the test set using metrics like classification_report and confusion_matrix.
- **Feature Importance**: Visualize feature importances from the RandomForestClassifier to understand which attributes most influence credit risk predictions.

### 5. Model Training and Evaluation (XGBoost with Hyperparameter Tuning)

- **XGBoost Model and Grid Search**: Implement an XGBoost classifier and perform GridSearchCV to find optimal hyperparameters for the model.
- **Model Evaluation**: Evaluate the best XGBoost model on the test set using metrics similar to RandomForestClassifier.

## Objective

The primary goal of this project is to develop accurate machine learning models that can predict credit risk based on applicant information. The 'Risk' variable, defined during preprocessing, serves as the target variable for prediction.

## Model Working (Random Forest and XGBoost)

Both Random Forest and XGBoost are ensemble learning methods that combine multiple decision trees to make predictions. Here's how they operate in this context:

- **Decision Trees**: Each model utilizes decision trees, which use a series of if-else conditions based on features (e.g., age, credit amount) to arrive at predictions.
- **Random Forest**: Constructs a forest of decision trees, each trained on a random subset of the data and features. Predictions are averaged across all trees to enhance accuracy and reduce variance.
- **XGBoost**: Builds decision trees sequentially, with each subsequent tree focusing on correcting errors made by previous trees. This gradient boosting approach iteratively improves model performance by minimizing a loss function.

## Achieving the Objective

- **Feature Engineering**: The creation of the 'Risk' variable from 'Credit Amount' and 'Duration' facilitates the framing of credit risk prediction as a classification task.
- **Model Training**: Both RandomForestClassifier and XGBoost models are trained on preprocessed data, learning patterns and relationships between features and the target variable.
- **Prediction and Evaluation**: Models predict credit risk for new applicants based on learned patterns, evaluated using metrics like accuracy, precision, recall, and F1-score to assess generalization to unseen data.

## Usage

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/credit-risk-prediction.git
   cd credit-risk-prediction
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Run the main script to train and evaluate the models:

   ```bash
   python credit_risk_prediction.py
   ```

4. View model performance metrics and feature importances in the console output.


