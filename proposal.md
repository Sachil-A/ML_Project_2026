# A Machine Learning Framework for Credit Card Fraud

# Detection and Risk Scoring

### Neeraj Kulkarni 2022B5A71067G

### Aman Dash 2022A3PS1143G

### Atharva Mandhaniya 2022B1A70037G

### Sachil Abbimane 2022B5A70070G

### Ashmit Gupta 2022B1A71374G

### Neha Desai 2022A7PS0005G

### Pranav Deshpande 2022B3A71204G

### Vikram Virat Chiluveru 2022A7PS0665G

## 1. Introduction

The increasing reliance on digital payment systems has led to a corresponding rise in fraudulent
financial transactions. Detecting such fraud in a timely and reliable manner remains a challenging
problem due to the highly imbalanced nature of transaction data and the continuously evolving
behaviour of fraudulent actors. In practical settings, fraud detection systems must balance two
competing objectives: maximizing detection rates while minimizing false alarms that may inconve-
nience legitimate users.
This project proposes to develop a machine learning framework for credit card fraud detection
that goes beyond binary classification. In addition to predicting the likelihood of fraud, the system
will incorporate anomaly detection techniques and behavioural features to construct a risk scoring
mechanism, thereby better reflecting real-world decision processes used in financial systems.

## 2. Problem Formulation

Let each transaction be represented by a feature vector x ∈ Rdwith an associated label y ∈ { 0 , 1 }
indicating legitimate or fraudulent activity. The primary task is to learn a function f (x) that
estimates the probability of fraud.
However, due to class imbalance and the presence of previously unseen fraud patterns, we
extend this formulation by incorporating unsupervised anomaly detection. The final objective is
to compute a composite risk score:

```
R(x) = αf (x) + βA(x) + γg(x)
```
where f (x) denotes the supervised model output, A(x) represents an anomaly score, and g(x)
captures behavioural features derived from transaction history.


## 3. Datasets

The primary dataset used in this project will be:

- European Credit Card Fraud Dataset (Vesta / Kaggle): This dataset contains 284,
    anonymized transactions with 492 fraudulent instances. Features are transformed using PCA,
    making it suitable for studying high-dimensional data and dimensionality reduction tech-
    niques.

```
To provide contextual grounding and support analytical insights, we will additionally refer to:
```
- RBI Annual Reports on Frauds: Aggregate statistics on digital payment frauds in India.
- NPCI / UPI Transaction Reports: Publicly available summaries of transaction volumes
    and fraud trends.

While the latter datasets are not transaction-level, they will be used to contextualize observed
patterns and motivate the problem setting in the Indian scenario.

## 4. Methodology

The proposed system consists of multiple components designed to address different aspects of the
problem.

### 4.1 Supervised Learning

We will establish baseline predictive performance using classical classification models such as lo-
gistic regression. However, our primary predictive power will be derived from ensemble methods,
specifically Random Forests and Gradient Boosting algorithms like XGBoost or LightGBM. These
ensemble techniques are considered the industry standards for tabular fraud data and will be eval-
uated under different data preprocessing strategies.

### 4.2 Handling Class Imbalance

Given the skewed distribution of classes, we will explore techniques such as Synthetic Minority
Oversampling Technique (SMOTE), undersampling, and class-weighted loss functions. The effect
of these methods on model performance will be systematically analyzed.

### 4.3 Unsupervised Learning

To detect anomalous transactions that may not follow previously observed fraud patterns, unsuper-
vised techniques such as K-means clustering and Isolation Forest will be employed. These methods
provide complementary signals to supervised predictions.


### 4.4 Dimensionality Reduction

Principal Component Analysis (PCA) will be used both as a preprocessing step and as a tool for
visualization. Its role in improving model performance and interpretability will be examined.

### 4.5 Feature Engineering

Given the anonymized nature of the PCA-transformed dataset, we will focus on engineering features
based on the explicit Time and Amount variables. This will include strategies such as binning
transactions by the hour of the day to identify peak fraud times, as well as scaling the Amount
feature to handle extreme outliers. These context-derived features are expected to improve the
detection of suspicious activity.

### 4.6 Risk Scoring and Decision Layer

The outputs of the above components will be combined into a unified risk score. Based on predefined
thresholds, each transaction will be categorized into different action levels (allow, flag, or block),
simulating a real-world fraud detection pipeline.

## 5. Evaluation

Given the class imbalance, standard accuracy is not an appropriate metric. Instead, we will focus
on:

- Precision, Recall, and F1-score
- Receiver Operating Characteristic (ROC) and AUC
- False positive rate
- Cost-sensitive evaluation reflecting financial impact

```
Comparisons will be made across different models and preprocessing strategies.
```
## 6. Expected Contributions

The project is expected to demonstrate:

- The effectiveness of combining supervised and unsupervised approaches
- The impact of imbalance handling techniques on model performance
- A practical risk scoring framework for fraud detection
- Insights into transaction behaviour and fraud patterns


## 7. Timeline (3 Weeks)

Week 1: Data preprocessing, exploratory analysis, and baseline models (logistic regression, deci-
sion tree).
Week 2: Implementation of imbalance handling techniques, unsupervised models, and feature
engineering.
Week 3: Integration of risk scoring system, model evaluation, and preparation of final results
and visualizations.

## 8. Conclusion

This project aims to bridge the gap between theoretical machine learning models and practical
fraud detection systems by incorporating multiple learning paradigms and emphasizing decision-
making under uncertainty. The combination of predictive modeling, anomaly detection, and risk
scoring provides a more comprehensive approach to the problem than standard classification-based
methods.


