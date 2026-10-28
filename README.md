# GDP Prediction of World Countries

## Group 17 — Machine Learning Project

### Project Overview

This project aims to predict the **GDP per capita of countries** using supervised machine learning techniques.

The dataset contains information about different countries, including population, area, population density, literacy, migration, birth rate, death rate, agriculture, industry, service sector and other socio-economic features.

The project demonstrates the complete machine learning workflow from data preprocessing to model training, testing and prediction.

## Project Objective

The main objective of this project is to build a machine learning model that can predict **GDP per capita** based on various demographic, geographic and economic features of countries.

## Dataset

The project uses the dataset:

`project - country GDP.xlsx`

The dataset contains country-level information such as:

- Population
- Area
- Population Density
- Coastline Ratio
- Net Migration
- Infant Mortality
- Literacy
- Phones
- Arable Land
- Crops
- Other Land
- Climate
- Birth Rate
- Death Rate
- Agriculture
- Industry
- Service

### Target Variable

**GDP ($ per capita)**

The GDP per capita column is used as the target variable for supervised learning.

## Machine Learning Workflow

The project follows these major steps:

1. Load the dataset
2. Data cleaning
3. Handle missing values
4. Check duplicate records
5. Convert data into appropriate formats
6. Exploratory Data Analysis
7. Feature engineering
8. Separate features (X) and target (y)
9. Split data into training and testing sets
10. Preprocess numerical and categorical features
11. Train machine learning models
12. Make predictions
13. Evaluate model performance
14. Save the trained model
15. Save the preprocessing pipeline

## Preprocessing

The preprocessing pipeline includes techniques such as:

- Missing-value handling
- Median imputation
- One-hot encoding for categorical variables
- Feature scaling / standardization

The preprocessing pipeline is saved as:

`GDP_preprocessing_pipeline.pkl`

## Machine Learning Model

The trained prediction model is saved as:

`GDP_prediction_model.pkl`

The main Jupyter Notebook containing the complete implementation is:

`GDP_Prediction_ML.ipynb`

## Project Files

| File | Description |
|---|---|
| `GDP_Prediction_ML.ipynb` | Complete machine learning implementation |
| `GDP_prediction_model.pkl` | Trained machine learning model |
| `GDP_preprocessing_pipeline.pkl` | Saved preprocessing pipeline |
| `project - country GDP.xlsx` | Project dataset |

## Technologies Used

- Python
- Jupyter Notebook
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Excel

## Team Members

**Group 17**

- Mahesh Anugula
- Gnaneswar Borra
- Tharun Singireddy
- Kavya Seelam

## Conclusion

This project demonstrates how supervised machine learning can be used to predict GDP per capita from country-level demographic, geographic and economic information.

The saved model and preprocessing pipeline can be reused to process new input data and generate GDP predictions.
