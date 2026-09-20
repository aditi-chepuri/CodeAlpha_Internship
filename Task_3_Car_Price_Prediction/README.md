# Car Price Prediction with Machine Learning

## CodeAlpha Internship - Task 3

### Project Overview

This project develops a machine learning model to predict car selling
prices using car-related features. The workflow includes data
preprocessing, categorical feature encoding, train-test splitting,
regression model training, model evaluation, visualization, and model
saving.

## Objective

The main objective is to build a regression-based machine learning
system that can predict the selling price of a used car from available
car attributes.

## Dataset

The dataset used for this project contains 299 records after duplicate
removal and 9 original columns:

-   Car_Name
-   Year
-   Selling_Price
-   Present_Price
-   Driven_kms
-   Fuel_Type
-   Selling_type
-   Transmission
-   Owner

`Selling_Price` is the target variable.

## Technologies Used

-   Python
-   Pandas
-   NumPy
-   Scikit-learn
-   Matplotlib
-   Jupyter Notebook

## Project Workflow

1.  Load the dataset using Pandas.
2.  Inspect the dataset structure and columns.
3.  Check for missing values.
4.  Remove duplicate records.
5.  Separate features and target variable.
6.  Remove `Car_Name` from the initial model features.
7.  Encode categorical variables using one-hot encoding.
8.  Split the data into training and testing sets.
9.  Train a Linear Regression model.
10. Generate predictions.
11. Evaluate the model using MAE, MSE, RMSE, and R².
12. Train a Random Forest Regression model for comparison.
13. Compare the model evaluation results.
14. Visualize actual and predicted prices.
15. Save the trained Linear Regression model.

## Data Preprocessing

Two duplicate rows were found and removed.

No missing values were found in any column.

The categorical columns were:

-   `Fuel_Type`
-   `Selling_type`
-   `Transmission`

These were converted into numerical indicator columns using
`pd.get_dummies()`.

`Car_Name` was removed from the initial model features.

## Train-Test Split

The processed dataset was divided into:

-   Training set: 239 records
-   Testing set: 60 records
-   Number of input features: 8

The split used `test_size=0.2` and `random_state=42`.

## Machine Learning Models

### 1. Linear Regression

Linear Regression was trained as the primary regression model.

Test-set results:

  Metric       Result
  ---------- --------
  MAE           1.473
  MSE           6.373
  RMSE          2.525
  R² Score      0.753

The R² score of 0.753 means that, on this test split, the model explains
approximately 75.3% of the variation in the target values.

### 2. Random Forest Regression

A Random Forest Regression model with 100 estimators was also trained
for comparison.

Test-set results:

  Metric       Result
  ---------- --------
  MAE           1.489
  MSE          12.845
  RMSE          3.584
  R² Score      0.502

For this particular train/test split, the Linear Regression model
produced lower error metrics and a higher R² score than the Random
Forest model.

## Evaluation Metrics

### MAE - Mean Absolute Error

Measures the average absolute difference between actual and predicted
prices.

### MSE - Mean Squared Error

Measures the average squared difference between actual and predicted
prices.

### RMSE - Root Mean Squared Error

The square root of MSE. It expresses prediction error on the same scale
as the target.

### R² Score

Measures how much of the variation in the target variable is explained
by the model.

## Visualizations

The project includes:

1.  Actual vs Predicted Car Prices scatter plot
2.  Actual vs Predicted Car Prices line plot
3.  Model performance comparison using R² score

## Saved Files

The project generates:

-   `car_price_model.pkl` - saved Linear Regression model
-   `car_price_predictions.csv` - actual and predicted prices for the
    test set
-   `car_price_prediction.ipynb` - complete Jupyter Notebook

## Conclusion

The project demonstrates an end-to-end machine learning workflow for car
price prediction. After preprocessing and encoding the data, Linear
Regression and Random Forest Regression were trained and evaluated. On
the current test split, Linear Regression achieved an R² score of 0.753,
while Random Forest achieved an R² score of 0.502.

The trained Linear Regression model was saved as `car_price_model.pkl`,
and the test predictions were saved as `car_price_predictions.csv`.

## How to Run

1.  Open Jupyter Notebook.
2.  Open `car_price_prediction.ipynb`.
3.  Make sure `car data.csv` is available in the project folder.
4.  Run the notebook cells in order.
5.  The trained model and prediction CSV will be generated after
    execution.

## Internship Task

This project was completed as part of:

**CodeAlpha Data Science Internship - Task 3: Car Price Prediction with
Machine Learning**
