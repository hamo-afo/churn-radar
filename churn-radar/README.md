# Churn Radar

Predicting Telco customer churn with machine learning: data cleaning, EDA, model building, and a Streamlit app.

Built as part of the **Verstech Internship Program, Track 1: AI / Machine Learning** (6-week roadmap).

## Project Purpose

Telecom companies lose revenue when customers leave. This project builds a machine learning model that predicts whether a customer is likely to churn, so the company can act before the customer leaves.

## Dataset

- **Name:** Telco Customer Churn (sample data originally published by IBM, available on [Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn))
- **Size:** 7,043 customers, 21 columns
- **Target:** `Churn` (Yes / No)
- **Features:** customer demographics, services used, contract and billing details, tenure, monthly and total charges

## Libraries

Python 3.10 or 3.11, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, Joblib, Streamlit.

## Installation and Run Steps

```bash
git clone https://github.com/hamo-afo/churn-radar.git
cd churn-radar
pip install -r requirements.txt
jupyter notebook 01_preprocessing.ipynb
```

The raw dataset (`WA_Fn-UseC_-Telco-Customer-Churn.csv`) is included in the repo. Run all cells in the notebook to regenerate the cleaned files.

## Project Structure (so far)

```
churn-radar/
|-- 01_preprocessing.ipynb          # Week 1: data cleaning and preprocessing
|-- WA_Fn-UseC_-Telco-Customer-Churn.csv   # raw dataset
|-- data/
|   |-- processed/
|       |-- telco_cleaned.csv       # cleaned, readable version (for EDA)
|       |-- telco_encoded.csv       # fully numeric version (for modeling)
|-- requirements.txt
|-- README.md
```

The folders will be reorganized in Week 5 into `notebooks/`, `src/`, `models/` and `app.py`.

## Progress

| Week | Focus | Status |
|------|-------|--------|
| 1 | Dataset and Preprocessing | Done |
| 2 | Exploratory Data Analysis (EDA) | Upcoming |
| 3 | Model Development | Upcoming |
| 4 | Evaluation and Improvement | Upcoming |
| 5 | End-to-End ML Project | Upcoming |
| 6 | Deployment and Documentation | Upcoming |

## Week 1: Results

- Fixed `TotalCharges` (stored as text) and filled its 11 missing values with the median.
- Dropped `customerID`, removed 22 duplicate rows (7,043 to 7,021 rows).
- Merged "No internet service" / "No phone service" into "No".
- Encoded the target (Yes/No to 1/0) and the other text columns with one-hot encoding.
- Split the data 80/20 (stratified) and scaled it with a scaler fitted on training data only, to avoid data leakage.

## Future Improvements

- EDA with charts and written insights
- Compare Logistic Regression, Decision Tree and Random Forest
- Handle class imbalance (about 73% stayed, 27% churned) and tune the best model
- Streamlit app for live predictions
