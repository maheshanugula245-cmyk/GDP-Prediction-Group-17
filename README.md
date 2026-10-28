# 🌍 GDP Prediction of World Countries

## 📌 Project Overview

This project focuses on predicting the **GDP per capita of countries** using supervised Machine Learning techniques.

The project uses demographic, geographic, social, and economic characteristics of countries as input features to predict **GDP per capita**.

This project was developed as part of the **AI Automation** course at **University West, Sweden**.

---

## 🎯 Project Objective

The main objectives of this project are:

- To understand and analyze country-level data.
- To clean and preprocess the dataset.
- To perform exploratory data analysis.
- To identify relationships between different country characteristics and GDP.
- To apply supervised Machine Learning regression algorithms.
- To compare different Machine Learning models.
- To evaluate model performance using RMSE, MAE, and R².
- To develop a reusable preprocessing pipeline and trained model.
- To predict GDP per capita for unseen data.

---

## 📊 Dataset

The dataset contains information about different countries and their demographic, geographic, social, and economic characteristics.

### Target Variable

The target variable is:

**GDP ($ per capita)**

GDP per capita is separated from the input features and used as the target variable for supervised learning.

### Input Features

The project uses the following features:

- Population
- Area (sq. mi.)
- Pop. Density (per sq. mi.)
- Coastline (coast/area ratio)
- Net migration
- Infant mortality (per 1000 births)
- Literacy (%)
- Phones (per 1000)
- Arable (%)
- Crops (%)
- Other (%)
- Climate
- Birthrate
- Deathrate
- Agriculture
- Industry
- Service

---

## 🔄 Machine Learning Workflow

The project follows the following workflow:

```text
Country Dataset
       ↓
Data Loading
       ↓
Data Cleaning
       ↓
Missing Value Handling
       ↓
Duplicate Checking
       ↓
Exploratory Data Analysis
       ↓
Feature Engineering
       ↓
Separate Features (X) and Target (y)
       ↓
Train/Test Split
       ↓
Data Preprocessing Pipeline
       ↓
Model Training
       ↓
Model Comparison
       ↓
Cross-Validation
       ↓
Final Model Evaluation
       ↓
GDP Prediction
```

---

## 🧹 Data Preprocessing

The following preprocessing steps were performed:

1. Loaded the country GDP dataset.
2. Inspected the dataset structure.
3. Converted numerical data into appropriate formats.
4. Checked for duplicate records.
5. Identified and handled missing values.
6. Separated the target variable from the input features.
7. Performed feature engineering.
8. Split the data into training and testing datasets.
9. Applied preprocessing using a Machine Learning pipeline.
10. Saved the preprocessing pipeline for future predictions.

---

## 🔎 Exploratory Data Analysis

Exploratory Data Analysis (EDA) was performed to understand the dataset and relationships between variables.

The analysis included:

- Histograms
- Scatter plots
- Correlation analysis
- Feature distributions
- Relationship analysis between features and GDP
- Statistical summaries

These analyses helped to understand the structure of the data before applying Machine Learning models.

---

## ⚙️ Feature Engineering

Additional features were investigated/created to improve the representation of the country-level data.

Examples include:

- Natural Growth
- Industry + Service
- Service-Agriculture Gap

Feature engineering helps the Machine Learning models identify useful relationships between the input variables and GDP per capita.

---

## 🤖 Machine Learning Models

Three supervised regression algorithms were used for model comparison.

### 1. Linear Regression

Linear Regression models the relationship between the input features and GDP per capita using a linear relationship.

It provides a simple baseline model for comparison.

---

### 2. Decision Tree Regression

Decision Tree Regression uses a tree-like structure to learn relationships between the input features and GDP per capita.

It can model nonlinear relationships but can suffer from overfitting if the tree becomes too complex.

---

### 3. Random Forest Regression

Random Forest Regression combines multiple decision trees to produce a more robust prediction.

It can capture nonlinear relationships and is generally more resistant to overfitting than a single decision tree.

---

# 📏 Model Evaluation Metrics

The models were evaluated using three regression metrics.

## RMSE — Root Mean Squared Error

RMSE measures the magnitude of prediction errors.

A lower RMSE indicates better performance.

Large errors are penalized more heavily because the errors are squared before calculating the average.

---

## MAE — Mean Absolute Error

MAE measures the average absolute difference between the actual and predicted GDP values.

A lower MAE indicates better performance.

---

## R² — R-squared

R² measures how much of the variation in the target variable is explained by the model.

A higher R² indicates better performance.

An R² value of 1.0 represents a perfect fit, while values closer to 0 indicate that the model explains less of the variation.

---

# 🏆 Final Test Results

The final trained model was evaluated on the unseen test dataset.

| Metric | Final Result |
|---|---:|
| **RMSE** | **2981.3538** |
| **MAE** | **2281.2372** |
| **R²** | **0.8735624** |

### 📌 Interpretation

The final model achieved an **R² score of 0.87356**.

This means that approximately **87.36% of the variation in GDP per capita is explained by the model on the test dataset**.

The **MAE of 2281.24** means that the model's predictions differ from the actual GDP per capita by approximately 2281 GDP units on average.

The **RMSE of 2981.35** represents the overall magnitude of prediction errors, giving greater weight to larger errors.

> **Important:** Since this is a regression problem, the R² score should not be described as "87.36% accuracy." It is more appropriate to say that the model explains approximately 87.36% of the variation in GDP per capita.

---

# 📊 Model Comparison

The initial model comparison produced the following results:

| Model | RMSE | MAE | R² |
|---|---:|---:|---:|
| Linear Regression | 4269.97 | 2884.59 | 0.83159 |
| Decision Tree | 0.00 | 0.00 | 1.00000 |
| Random Forest | 1710.73 | 991.55 | 0.97297 |

These results were further investigated using cross-validation.

---

# 🔁 Cross-Validation Results

Cross-validation was performed to obtain a more reliable estimate of model performance.

| Model | Mean RMSE | Standard Deviation |
|---|---:|---:|
| **Random Forest** | **4441.73** | **1252.61** |
| Linear Regression | 5777.27 | 1257.34 |
| Decision Tree | 7297.17 | 1351.66 |

Based on the cross-validation results, **Random Forest achieved the lowest mean RMSE** among the three models.

Therefore, Random Forest showed the strongest generalization performance during cross-validation.

---

# ⚠️ Model Performance Observation

The initial Decision Tree comparison produced an RMSE of 0 and an R² of 1.0.

A perfect score can indicate that the Decision Tree has **overfitted the data**, especially if the evaluation was performed on training data.

Therefore, the test-set evaluation and cross-validation results are more useful for understanding how well the models generalize to unseen data.

The cross-validation results showed that Random Forest performed better than Linear Regression and Decision Tree based on mean RMSE.

---

# 💾 Saved Machine Learning Components

Two important Machine Learning components were saved for reuse.

### `GDP_prediction_model.pkl`

This file contains the trained Machine Learning model.

It can be loaded later to make predictions without training the model again from the beginning.

### `GDP_preprocessing_pipeline.pkl`

This file contains the preprocessing pipeline used to transform input data before it is provided to the Machine Learning model.

Using a saved preprocessing pipeline helps ensure that new data is processed consistently with the training data.

---

# 🔮 Prediction Process

For new country data, the prediction process is:

```text
New Country Data
       ↓
Preprocessing Pipeline
       ↓
Transformed Features
       ↓
Trained ML Model
       ↓
Predicted GDP per Capita
```

The saved preprocessing pipeline and trained model can therefore be reused for future predictions.

---

# 📁 Repository Files

The GitHub repository contains the following files:

| File | Description |
|---|---|
| `GDP_Prediction_ML.ipynb` | Complete Jupyter Notebook containing data cleaning, EDA, preprocessing, model training, evaluation and predictions |
| `GDP_prediction_model.pkl` | Saved trained Machine Learning model |
| `GDP_preprocessing_pipeline.pkl` | Saved preprocessing pipeline |
| `project - country GDP.xlsx` | Country GDP dataset |
| `README.md` | Project documentation |

---

# 🛠️ Technologies Used

The project was developed using:

- **Python**
- **Jupyter Notebook**
- **NumPy**
- **Pandas**
- **Matplotlib**
- **Scikit-learn**
- **Pickle**
- **Microsoft Excel**

---

# 📚 Python / Machine Learning Libraries

The main Python libraries used in the project include:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.model_selection import cross_val_score
from sklearn.linear_model import LinearRegression
from sklearn.tree import DecisionTreeRegressor
from sklearn.ensemble import RandomForestRegressor
from sklearn.metrics import mean_squared_error
from sklearn.metrics import mean_absolute_error
from sklearn.metrics import r2_score
```

---

# 🚀 How to Run the Project

## Step 1 — Install Python

Install Python on your computer.

## Step 2 — Install Required Libraries

Install the required libraries using:

```bash
pip install numpy pandas matplotlib scikit-learn openpyxl jupyter
```

## Step 3 — Open Jupyter Notebook

Start Jupyter Notebook:

```bash
jupyter notebook
```

## Step 4 — Open the Project

Open:

```text
GDP_Prediction_ML.ipynb
```

## Step 5 — Dataset

Make sure the dataset file is available:

```text
project - country GDP.xlsx
```

## Step 6 — Run the Notebook

Run the notebook cells in order.

The notebook performs:

- Data loading
- Data cleaning
- Exploratory analysis
- Feature engineering
- Train/test splitting
- Preprocessing
- Model training
- Model evaluation
- Cross-validation
- Final prediction

---

# 👥 Group Members

## Group 17

- **Mahesh Anugula**
- **Gnaneswar Borra**
- **Tharun Singireddy**
- **Kavya Seelam**

---

# 🎓 Course Information

**Course:** AI Automation  
**University:** University West  
**Project:** Predicting GDP of World Countries  
**Group:** 17

---

# ✅ Conclusion

This project demonstrates the application of supervised Machine Learning techniques to predict GDP per capita using country-level demographic, geographic, social, and economic information.

Three regression algorithms were investigated:

- Linear Regression
- Decision Tree Regression
- Random Forest Regression

The final test evaluation achieved:

**R² = 0.87356**

This indicates that the final model explains approximately **87.36% of the variation in GDP per capita on the unseen test dataset**.

Cross-validation showed that **Random Forest achieved the lowest mean RMSE** among the evaluated models, indicating stronger generalization performance compared with Linear Regression and Decision Tree Regression.

The project also demonstrates the importance of:

- Data cleaning
- Exploratory Data Analysis
- Feature engineering
- Data preprocessing
- Train/test splitting
- Model comparison
- Cross-validation
- Evaluation on unseen data
- Saving reusable Machine Learning models and preprocessing pipelines

---

## 🌍 Project Summary

**Problem:** Predict GDP per capita of countries.

**Approach:** Supervised Machine Learning regression.

**Models:** Linear Regression, Decision Tree, Random Forest.

**Final Test R²:** **0.87356**

**Best Cross-Validation Model:** **Random Forest**

**Group:** **17**

**University:** **University West**
