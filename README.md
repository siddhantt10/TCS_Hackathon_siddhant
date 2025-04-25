## TCS_Hackathon_siddhant

# Credit Risk Prediction with Machine Learning

This repository contains Python code to predict credit risk for loan applicants using the German Credit dataset. The project focuses on developing a machine learning model to classify applicants into good and bad credit risks based on their financial and personal attributes.

## Dataset

The original German Credit dataset consists of 1000 entries with 20 categorical and symbolic attributes. For this project, the dataset was preprocessed and simplified to focus on the following attributes:

- **Age**: Numeric value representing the age of the applicant.
- **Sex**: Categorical variable ('male', 'female').
- **Job**: Numeric variable representing job categories (0 - unskilled and non-resident, 1 - unskilled and resident, 2 - skilled, 3 - highly skilled).
- **Housing**: Categorical variable indicating housing status ('own', 'rent', 'free').
- **Saving Accounts**: Categorical variable indicating savings level ('little', 'moderate', 'quite rich', 'rich').
- **Checking Account**: Numeric variable indicating checking account balance in Deutsch Mark (DM).
- **Credit Amount**: Numeric variable indicating the amount of credit requested in DM.
- **Duration**: Numeric variable indicating the duration of the credit in months.
- **Purpose**: Categorical variable indicating the purpose of the credit ('car', 'furniture/equipment', 'radio/TV', 'domestic appliances', 'repairs', 'education', 'business', 'vacation/others').
- **Classification**: Target variable where '1' denotes good credit risk and '0' denotes bad credit risk.

## Approach

### 1. Data Preprocessing

- **Data Loading and Cleaning**: Loaded the dataset and handled missing values. Encoded categorical variables using label encoding and handled numeric variables appropriately.
  
### 2. Model Development

- **Feature Selection**: Selected relevant features based on their potential impact on credit risk.
- **Model Selection**: Chose RandomForestClassifier as the predictive model due to its ability to handle complex relationships and feature importance analysis.

### 3. Model Training and Evaluation

- **Data Splitting**: Split the dataset into training and testing sets (80% training, 20% testing).
- **Model Training**: Trained the RandomForestClassifier on the training data.
- **Model Evaluation**: Evaluated model performance using accuracy score and classification report (precision, recall, F1-score).

### 4. Model Interpretation

- **Feature Importance**: Analyzed feature importances to understand which attributes have the most significant influence on credit risk predictions.
- **Visualization**: Created bar plots to visualize feature importances for better interpretation.

## Requirements

- Python 3.x
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn

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

3. Run the main script to train and evaluate the model:

   ```bash
   python credit_risk_prediction.py
   ```

4. View model performance metrics and feature importances in the console output.

