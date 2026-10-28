# 🌍 GDP Prediction of World Countries Using Machine Learning

## 📌 Project Overview

This project focuses on predicting the **GDP per capita of countries** using **Supervised Machine Learning** techniques.

The project uses country-level demographic, geographical, and socioeconomic information to train Machine Learning regression models and predict GDP per capita.

Different Machine Learning models are trained, evaluated, compared, and validated to identify the most suitable model for the prediction task.

---

## 🎯 Problem Statement

The main objective of this project is to develop a Machine Learning system that can predict the **GDP per capita of countries** based on different demographic, geographical, and socioeconomic features.

The project investigates whether information such as population, literacy, migration, birth rate, death rate, agriculture, industry, and service-sector contribution can be used to predict the GDP per capita of a country.

---

## 🧠 Machine Learning Type

**Learning Type:** Supervised Learning

**Problem Type:** Regression

**Target Variable:** GDP ($ per capita)

Since the target variable is a continuous numerical value, this is a **regression problem**.

---

# 📊 Dataset

The dataset contains information about different countries and their demographic, geographical, and socioeconomic characteristics.

### Input Features

The following features are used as input variables:

1. Population
2. Area (sq. mi.)
3. Pop. Density (per sq. mi.)
4. Coastline (coast/area ratio)
5. Net migration
6. Infant mortality (per 1000 births)
7. Literacy (%)
8. Phones (per 1000)
9. Arable (%)
10. Crops (%)
11. Other (%)
12. Climate
13. Birthrate
14. Deathrate
15. Agriculture
16. Industry
17. Service

### Target Variable

**GDP ($ per capita)**

The GDP per capita column is used as the target variable and is separated from the input features before Machine Learning model training.

---

# 🧹 Data Preprocessing

Several preprocessing steps were performed before training the Machine Learning models.

### Preprocessing Steps

1. Load the dataset.
2. Inspect the dataset structure.
3. Convert numerical values into appropriate numerical formats.
4. Check for duplicate records.
5. Check for missing values.
6. Handle missing values.
7. Separate the target variable from the input features.
8. Split the data into training and testing datasets.
9. Apply numerical preprocessing.
10. Apply categorical preprocessing where required.
11. Apply feature scaling.
12. Create a reusable preprocessing pipeline.

### Preprocessing Techniques

The project uses:

- Median imputation for missing numerical values
- One-hot encoding for categorical variables
- Standard scaling for numerical features
- Reusable Scikit-learn preprocessing pipelines

---

# 🔧 Feature Engineering

Additional features were created to provide the Machine Learning models with more meaningful information.

The engineered features include:

### Natural Growth

Natural growth is derived from the relationship between birth rate and death rate.

### Industry + Service

The Industry and Service contributions are combined to represent the overall contribution of these sectors.

### Service-Agriculture Gap

The difference between the Service and Agriculture contributions is used as an additional socioeconomic feature.

Feature engineering helps the models identify relationships that may not be directly visible from the original variables.

---

# 🔬 Exploratory Data Analysis

Exploratory Data Analysis was performed to understand the dataset and relationships between variables.

The analysis included:

- Dataset inspection
- Descriptive statistics
- Missing-value analysis
- Duplicate checking
- Histograms
- Scatter plots
- Correlation analysis
- Feature relationships

Visualization was performed using **Matplotlib**.

---

# 🤖 Machine Learning Models

Three supervised regression models were implemented and compared.

## 1. Linear Regression

Linear Regression is a supervised Machine Learning algorithm used to model the relationship between the input features and the target variable.

It assumes a linear relationship between the independent variables and GDP per capita.

---

## 2. Decision Tree Regression

Decision Tree Regression uses a tree-like structure to make predictions.

The model repeatedly divides the data using decision rules based on the input features.

Decision Trees can capture nonlinear relationships between features and the target variable.

---

## 3. Random Forest Regression

Random Forest Regression is an ensemble Machine Learning algorithm.

It combines multiple Decision Trees and uses their predictions to produce a final prediction.

Random Forest can capture complex nonlinear relationships and is generally more robust than a single Decision Tree.

---

# 📏 Model Evaluation

The Machine Learning models were evaluated using three important regression metrics:

## RMSE — Root Mean Squared Error

RMSE measures the magnitude of prediction errors.

A **lower RMSE indicates better performance**.

---

## MAE — Mean Absolute Error

MAE measures the average absolute difference between the actual and predicted values.

A **lower MAE indicates better performance**.

---

## R² — R-squared

R² measures how much of the variation in the target variable is explained by the Machine Learning model.

An R² value closer to **1.0** indicates better performance.

---

# 📊 Model Comparison

The three Machine Learning models were compared using RMSE, MAE, and R².

| Model | RMSE | MAE | R² |
|---|---:|---:|---:|
| Linear Regression | 4269.97 | 2884.59 | 0.83159 |
| Decision Tree | 0.00 | 0.00 | 1.00000 |
| Random Forest | 1710.73 | 991.55 | 0.97297 |

The model comparison shows the performance of the different regression algorithms on the evaluation data.

The perfect Decision Tree score should be interpreted carefully because a perfect score on one evaluation split can indicate **overfitting**.

Therefore, cross-validation was also performed to obtain a more reliable comparison.

---

# 🔄 Cross-Validation

Cross-validation was used to obtain a more reliable estimate of model performance.

The cross-validation results were:

| Model | Mean RMSE | Standard Deviation |
|---|---:|---:|
| Random Forest | 4441.73 | 1252.61 |
| Linear Regression | 5777.27 | 1257.34 |
| Decision Tree | 7297.17 | 1351.66 |

### Cross-Validation Result

**Random Forest achieved the lowest Mean RMSE and was therefore selected as the best-performing model based on cross-validation.**

---

# 🧪 Final Evaluation on Unseen Test Data

After training and selecting the Machine Learning model, the saved model and preprocessing pipeline were used to make predictions on unseen test data.

The final model was evaluated using RMSE, MAE, and R².

## Final Test Results

| Metric | Final Score |
|---|---:|
| RMSE | **2981.35** |
| MAE | **2281.24** |
| R² | **0.87356** |

### Final R² Score

**0.87356**

The R² score of approximately **0.87** means that the final model explains approximately **87.36% of the variation in GDP per capita** in the unseen test data.

---

# 📈 Final Prediction Results

The final model was used to predict GDP per capita values for countries that were not used during the model's training process.

The predictions were compared with the actual GDP per capita values to evaluate the model's performance.

The final evaluation demonstrates that the trained Machine Learning system can make meaningful predictions on unseen data.

---

# 💾 Saving the Machine Learning Model

The trained Machine Learning components were saved using Pickle/Joblib so that they can be reused without training the model again.

## Saved Files

### `GDP_prediction_model.pkl`

This file contains the trained Machine Learning model.

It can be loaded later to make predictions on new data.

### `GDP_preprocessing_pipeline.pkl`

This file contains the preprocessing pipeline.

It ensures that new input data is transformed in the same way as the data used during model training.

---

# 🔮 Prediction Workflow

The saved Machine Learning system follows this workflow:

```text
New Country Data
       ↓
Preprocessing Pipeline
       ↓
Data Transformation
       ↓
Trained Machine Learning Model
       ↓
GDP per Capita Prediction
```

This makes the trained model reusable for future predictions.

---

# 🔁 Complete Project Workflow

```text
Country Dataset
       ↓
Data Loading
       ↓
Data Inspection
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
Separate Features and Target
       ↓
Train/Test Split
       ↓
Preprocessing Pipeline
       ↓
Feature Transformation
       ↓
Machine Learning Models
       ↓
 ┌───────────────────────┐
 │ Linear Regression     │
 │ Decision Tree         │
 │ Random Forest         │
 └───────────────────────┘
       ↓
Model Comparison
       ↓
Cross-Validation
       ↓
Best Model Selection
       ↓
Final Evaluation
       ↓
Unseen Test Data
       ↓
Save Model and Pipeline
       ↓
Future Predictions
```

---

# 🛠️ Technologies and Libraries Used

## Programming Language

- Python

## Development Environment

- Jupyter Notebook

## Python Libraries

- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Joblib

## Version Control and Repository

- GitHub

---

# 📚 Key Learning Outcomes

Through this project, we learned how to:

- Load and inspect datasets
- Clean real-world data
- Handle missing values
- Detect duplicate records
- Perform Exploratory Data Analysis
- Create data visualizations
- Engineer new features
- Separate input features and target variables
- Split data into training and testing sets
- Build Machine Learning preprocessing pipelines
- Perform numerical and categorical preprocessing
- Train supervised Machine Learning models
- Perform regression
- Compare multiple Machine Learning algorithms
- Perform cross-validation
- Evaluate models using RMSE
- Evaluate models using MAE
- Evaluate models using R²
- Identify the best-performing model
- Save trained Machine Learning models
- Save preprocessing pipelines
- Load saved Machine Learning models
- Generate predictions on unseen data
- Organize a Machine Learning project using GitHub

---

# 🏆 Project Conclusion

This project demonstrates the application of **Supervised Machine Learning regression techniques** for predicting the GDP per capita of countries.

Three different regression algorithms were implemented:

1. Linear Regression
2. Decision Tree Regression
3. Random Forest Regression

The models were compared using RMSE, MAE, and R².

Cross-validation showed that **Random Forest achieved the lowest Mean RMSE** among the tested models and was therefore selected as the best model based on cross-validation.

The final evaluation on unseen test data produced:

- **RMSE:** 2981.35
- **MAE:** 2281.24
- **R²:** 0.87356

The final R² score of **0.87356** indicates that the final model explains approximately **87.36% of the variation in GDP per capita** on the unseen test data.

The project also demonstrates how a trained Machine Learning model and preprocessing pipeline can be saved and reused for future predictions.

---

# 👥 Group Information

## Group 17

**University:** University West

### Group Members

- Mahesh Anugula
- Gnaneswar Borra
- Tharun Singireddy
- Kavya Seelam

---

# 📁 Repository Structure

The GitHub repository contains the following files:

```text
GDP-Prediction-Group-17/
│
├── GDP_Prediction_ML.ipynb
│
├── GDP_prediction_model.pkl
│
├── GDP_preprocessing_pipeline.pkl
│
├── project - country GDP.xlsx
│
└── README.md
```

---

# 📄 File Descriptions

| File | Description |
|---|---|
| `GDP_Prediction_ML.ipynb` | Complete Jupyter Notebook containing data preprocessing, analysis, model training, evaluation, comparison, and prediction |
| `GDP_prediction_model.pkl` | Saved trained Machine Learning model |
| `GDP_preprocessing_pipeline.pkl` | Saved preprocessing pipeline |
| `project - country GDP.xlsx` | Original project dataset |
| `README.md` | Project documentation |

---

# 🌟 Final Project Summary

**Problem:** Predict GDP per capita of countries

**Approach:** Supervised Machine Learning Regression

**Models:** Linear Regression, Decision Tree Regression, Random Forest Regression

**Best Cross-Validation Model:** Random Forest

**Final Test RMSE:** 2981.35

**Final Test MAE:** 2281.24

**Final Test R²:** 0.87356

**Group:** 17

**University:** University West

---

# ✅ Project Status

**Project Completed**

The Machine Learning model has been trained, evaluated, compared using multiple regression algorithms, validated using cross-validation, tested on unseen data, and saved for future reuse.
