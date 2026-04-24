# ML Project 2026

# Credit Card Fraud Detection

This project explores different machine learning approaches for detecting fraudulent credit card transactions using a highly imbalanced dataset. The goal is to understand how various models behave under class imbalance and to evaluate their performance using metrics that are meaningful in real-world fraud detection settings.

## Dataset

The dataset used in this project is the publicly available credit card fraud dataset provided by the ULB Machine Learning Group. It contains anonymized transaction data where most features have been transformed using PCA. The dataset is highly imbalanced, with fraudulent transactions making up a very small fraction of the total.

## Project Structure

- `fraudDetectionProject.ipynb` — Main notebook containing data exploration, preprocessing, model training, and evaluation  
- `proposal.pdf` — Initial project proposal outlining objectives and approach  

## Approach

The workflow in this project includes:

1. **Exploratory Data Analysis**
   - Understanding class imbalance
   - Inspecting feature distributions and correlations

2. **Preprocessing and Feature Engineering**
   - Handling skewed features such as transaction amount
   - Creating additional features like transaction hour
   - Scaling features for model stability

3. **Modeling**
   - Logistic Regression with class weighting
   - Random Forest
   - XGBoost
   - Isolation Forest (unsupervised anomaly detection)

4. **Handling Class Imbalance**
   - Stratified train-test split
   - SMOTE for oversampling
   - Undersampling techniques

5. **Evaluation**
   - Precision, Recall, and F1-score
   - ROC-AUC and PR-AUC
   - Precision at top-k predictions
   - Cost-based evaluation to simulate real-world impact

6. **Hybrid Approach**
   - Combining supervised and unsupervised model outputs into a unified risk score

## Key Observations

- Class imbalance significantly affects model performance and evaluation.
- Metrics like accuracy and ROC-AUC can be misleading in this context.
- Precision-recall based metrics and cost-sensitive evaluation provide more meaningful insights.
- Combining different modeling approaches can improve detection performance in certain cases.

## Requirements

The project uses standard Python libraries, including:

- numpy  
- pandas  
- matplotlib  
- seaborn  
- scikit-learn  
- xgboost  
- imbalanced-learn  

## How to Run

1. Clone the repository:

git clone <repo-link>

2. Install dependencies:

pip install -r requirements.txt

3. Open the notebook:

jupyter notebook fraudDetectionProject.ipynb


4. Ensure the dataset is placed in the correct path as referenced in the notebook.

## Notes

This project is primarily exploratory and intended to compare different techniques for fraud detection rather than to build a production-ready system.