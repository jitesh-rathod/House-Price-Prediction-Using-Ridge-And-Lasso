## Housing Price Prediction using Ridge and Lasso Regression

# Problem Statement

A US-based housing company named Surprise Housing has decided to enter the Australian market. The company uses data analytics to purchase houses at a price below their actual values and flip them at a higher price. For the same purpose, the company has collected a dataset from the sale of houses in Australia. The data is provided in the CSV file below. The company is looking at prospective properties to buy to enter the market. You are required to build a regression model using regularization to predict the actual value of the prospective properties and decide whether to invest in them or not. 



Which variables are significant in predicting the price of a house, and how well those variables describe the price of a house.
Determine the optimal value of lambda for ridge and lasso regression.

# Approach Taken

# Reading and Understanding the Data: 
- Initial exploration of the dataset to understand its structure and variables.
# Basic Data Cleanup: 
- Addressing missing values and changing data types where necessary.

# Exploratory Data Analysis (EDA):
- Utilized AutoEDA using SweetViz to identify important variables.
- Conducted univariate and bivariate analysis including correlation heatmap.

# Data Preparation for Model Building:
- Performed log transformation of the target variable.
- Split the data into training and testing sets.
- Imputed missing values using business logic.
- Encoded categorical (nominal) features and scaled numerical features using robust scaling.
- Applied variance thresholding to exclude features with almost zero variance.

# Model Building:
- Utilized Ridge Regression model with GridSearchCV to find the optimal value of alpha.
- Identified top 25 features based on beta coefficient values.
- Employed Lasso Regression model with GridSearchCV to find the optimal value of alpha.
- Lasso eliminated 110 features (including dummy variables) and identified the top 25 features based on beta coefficient values.

# Evaluation:
- Evaluated both models on the training and test datasets.

## Observations

# Data Analysis and Feature Engineering:
- The housing data is first read and analyzed, dividing the features into numerical and categorical types.
- SalePrice is the target column.
- Missing data handling, outlier detection, and data cleaning are done.
- Trend of SalePrice is observed for changes in individual features.
- New features are extracted, redundant features are dropped, and categorical features are encoded accordingly.
- The data is split into train and test data and feature scaling is performed.
- Target variable SalePrice is right-skewed. Natural log of the same is normally distributed, hence for model building, the natural log of SalePrice is considered.
- Creating dummy variables increased the number of features greatly, highly imbalanced columns are dropped.

## Model Performance:

# Ridge Regression:
    - Best R² Score: 0.8949
    - Test R² Score: 0.8950
    - Best Alpha: 2.0
    - R² Score on Test Data: 0.8944
    - Mean Squared Error (MSE): 0.0168
    - Root Mean Squared Error (RMSE): 0.1295

# Lasso Regression:
    - Best R² Score: 0.8981
    - Test R² Score: 0.8967
    - Best Alpha: 0.0006
    - R² Score on Test Data: 0.8967
    - Mean Squared Error (MSE): 0.0164
    - Root Mean Squared Error (RMSE): 0.1281

- Both Ridge and Lasso regression models perform well on the test data, with R² scores close to 0.895 and 0.897 respectively.
- Lasso regression achieves a slightly higher R² score and lower RMSE compared to Ridge regression, indicating slightly better performance.
- The best alpha value for Ridge regression is 1.49, indicating moderate regularization, while for Lasso regression, the best alpha is 0.0006, suggesting very weak regularization.
- Lasso regression achieves better performance with a much smaller alpha value, indicating that it relies more on feature selection and less on regularization compared to Ridge regression.

For additional queries, refer to the Additional Questions document.
For detailed implementation, refer to the notebook here.

## Contact
Created by [jitesh-rathod@githubusername] - feel free to contact me!