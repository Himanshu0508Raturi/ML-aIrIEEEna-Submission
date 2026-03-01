#  IEEE SB GEHU -- ML Challenge

## Binary Fault Detection using Machine Learning

------------------------------------------------------------------------

##  Overview

This repository contains my solution for the **IEEE SB GEHU ML
Challenge**.

The objective of the challenge is to build a robust binary
classification model capable of detecting whether a device is operating
normally or exhibiting a fault condition.

The dataset consists of:

-   **47 numerical features (F01 -- F47)**
-   **Target variable: `Class`**
    -   `0` → Normal\
    -   `1` → Faulty

This project follows a structured, reproducible, and
competition-oriented machine learning workflow.

------------------------------------------------------------------------

##  Methodology & Approach

### 1️⃣ Exploratory Data Analysis (EDA)

-   Verified dataset dimensions and structure
-   Checked for missing values
-   Analyzed statistical distributions
-   Evaluated class balance

### Key Observations:

-   Dataset is moderately balanced
-   No major missing value issues
-   Scaling not required for tree-based models
-   Tree-based models are suitable for tabular data

------------------------------------------------------------------------

### 2️⃣ Model Selection Strategy

Multiple classification algorithms were trained and compared:

-   Decision Tree
-   Random Forest
-   XGBoost

### Training Steps:

1.  Split `TRAIN.csv` into training and validation sets
2.  Trained candidate models
3.  Evaluated using Accuracy, Precision, Recall, F1-score
4.  Selected best-performing model
5.  Retrained best model on full dataset
6.  Saved final model as `.pkl` file

------------------------------------------------------------------------

##  Final Model

**Random Forest** demonstrated:

-   Highest validation accuracy
-   Strong recall for faulty class (`Class = 1`)

Final model file: rf_model.pkl

------------------------------------------------------------------------

##  Evaluation Focus

Special emphasis was placed on:

-   **Recall for Class 1 (Fault Detection)**

Detecting faults reliably is more important than minimizing false
alarms.

------------------------------------------------------------------------

## Project Structure

```ML-Challenge/
│
├── TRAIN.csv
├── TEST.csv
├── train.ipynb
├── rf_model.pkl
├── FINAL.csv
├── requirements.txt
└── README.md 
```

------------------------------------------------------------------------

##  Setup Instructions

### 1️⃣ Clone Repository

git clone https://github.com/Himanshu0508Raturi/ML-aIrIEEEna-Submission.git <br>
cd ML-aIrIEEEna-Submission

------------------------------------------------------------------------

### 2️⃣ Create Virtual Environment (Recommended)

python -m venv venv

Activate: venv/Scripts/Activate.ps1


------------------------------------------------------------------------

### 3️⃣ Install Dependencies

pip install -r requirements.txt


------------------------------------------------------------------------

##  Usage

### 🔹 Train Model

jupyter notebook

Run `train.ipynb` to:

-   Perform EDA
-   Train multiple models
-   Compare performance
-   Save best model
-   Generate FINAL.csv

------------------------------------------------------------------------

### 🔹 Generate Predictions

Example:
```
import joblib
import pandas as pd

model = joblib.load("best_model.pkl")
sample = pd.DataFrame({...})
prediction = model.predict(sample)
print(prediction)
```
------------------------------------------------------------------------

### 🔹 Submission Format
```
ID  CLASS
1   0
2   1
3   0
```
Ensure:

-   Same order as TEST.csv
-   Same number of rows

Generated file: FINAL.csv

------------------------------------------------------------------------

##  Conclusion

This project demonstrates:

-   Structured ML pipeline
-   Proper model comparison
-   Reliable validation strategy
-   Competition-ready implementation
