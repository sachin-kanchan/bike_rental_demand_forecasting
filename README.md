# Bike Rental Demand Prediction using Linear Regression

## Overview

This project focuses on building a multiple linear regression model to predict the demand for shared bikes using a dataset provided by BoomBikes, a US bike-sharing provider. The analysis aims to identify significant variables that influence bike rental demand and to create a model that accurately predicts future demand. This model is intended to help BoomBikes optimize their business strategy, especially in the post-COVID-19 recovery period.

## Problem Statement
BoomBikes, a US-based bike-sharing provider, has recently experienced considerable dips in their revenues due to the ongoing COVID-19 pandemic. This has created significant challenges for the company to sustain itself in the current market conditions. Therefore, BoomBikes is developing a strategic business plan to accelerate its revenue recovery as the lockdown ends and the economy gradually restores.

As part of this plan, BoomBikes wants to understand the demand for shared bikes after the quarantine situation ends. The goal is to prepare the company to meet people's needs and stand out from the competition, aiming for improved business performance and profitability.

To achieve this goal, BoomBikes has engaged a consulting company to identify the key factors that influence the demand for shared bikes, specifically in the American market. The company seeks answers to the following questions:

*   Which variables are statistically significant in predicting the demand for shared bikes?
*   How well do these variables describe and explain variations in bike demand?

The service provider has gathered a large dataset on daily bike demands in the American market, which includes meteorological surveys and data reflecting various usage patterns. You are required to model this demand using a multiple linear regression model. This model should help management understand how demands change with different features and use this knowledge to adjust their business strategy to meet those demand levels and exceed customers’ expectations. It would also help to gauge the demand dynamics of a new market.

## Data
The dataset used for this project is `day.csv`, which includes the following features:
-   **instant**: Record index.
-   **dteday**: Date of the rental.
-   **season**: Season (1: spring, 2: summer, 3: fall, 4: winter).
-   **yr**: Year (0: 2018, 1: 2019).
-   **mnth**: Month (1 to 12).
-   **holiday**: Whether the day is a holiday (1) or not (0).
-   **weekday**: Day of the week.
-   **workingday**: Whether the day is a working day (1) or not (0).
-   **weathersit**: Weather situation (1: Clear, 2: Mist, 3: Light Snow/Rain, 4: Heavy Rain).
-   **temp**: Temperature in Celsius.
-   **atemp**: Feeling temperature in Celsius.
-   **hum**: Humidity.
-   **windspeed**: Wind speed.
-   **casual**: Count of casual users.
-   **registered**: Count of registered users.
-   **cnt**: Total count of bike rentals (target variable).

A detailed explanation of these features can be found in `data_dictionary.txt`.

## Project Workflow
1.  **Data Loading and Inspection:**
    -   Loading the dataset from `day.csv`.
    -   Examining the data structure, data types, and statistical summaries.
    -   Checking for missing values.
2.  **Data Preparation:**
    -   Creating a copy of the original dataframe to work on.
    -   Mapping numerical categories in 'season' and 'weathersit' to their corresponding string labels.
    -   Converting 'dteday' to datetime format to extract additional temporal features like day of the week and month.
    -   Dropping unnecessary columns ('instant', 'casual', 'registered') to avoid multicollinearity.
    -   Handling Outliers using IQR capping.
3.  **Exploratory Data Analysis (EDA):**
    -   Analyzing the distribution of the target variable ('cnt').
    -   Examining the distributions of numerical and categorical variables using histograms, boxplots, and countplots.
    -   Time-series analysis of the target variable to understand trends.
    -   Bivariate analysis to observe the relationship between categorical and numerical variables with the target variable.
    -   Pair plots and correlation analysis to understand the relationships between numerical variables, identifying multicollinearity.
4.  **Linear Regression Model Building:**
    -   Creating dummy variables for categorical features.
    -   Splitting the dataset into training and testing sets.
    -   Scaling the numerical features using StandardScaler.
    -   Using Recursive Feature Elimination (RFE) for feature selection, narrowing down to 15 features for the model.
    -   Building the OLS regression model using the selected features.
    -   Iterative feature selection to simplify the model further based on p-values and VIF values.
    -   Residual analysis to validate model assumptions.
    -   Making predictions on the test set.
5.  **Model Evaluation:**
    -   Evaluating the model's performance using R-squared on the test set.
    -   Checking for the model assumptions like Linearity, Independence, Normality and Homoscedasticity.
    -   Discussing the top 3 features contributing significantly to the target variable.
6.  **Final Observations:**
    -   Summarizing key insights and implications of model results for BoomBikes.

## Key Findings

-   The project identified key factors that impact bike rental demand.
-   The regression model's performance was evaluated and interpreted thoroughly.
-   Recommendations are provided to BoomBikes for improving their business strategy.
-   Model assumptions have been verified and the model performs well on test data.

## Repository Contents
-   `bike_rental_regression_analysis.ipynb`: Jupyter Notebook containing the code for data analysis and model building.
-   `day.csv`: Dataset used in the project.
-   `problem_statement.md`: Markdown file with the problem statement.
-   `data_dictionary.txt`: Text file containing the data dictionary.
-   `README.md`: This file, providing an overview of the project.

## Libraries Used
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- statsmodels

## How to Run
1.  Clone the repository
2.  Install the requirements using `pip install -r requirements.txt`.
3.  Open the `boombikes.ipynb` using Jupyter Notebook or Jupyter Lab and run all cells.

## Author
[Sachin Kanchan](https://github.com/sachin-kanchan)

## License
This project is licensed under the [MIT License](LICENSE).