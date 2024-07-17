## Predicting House Prices in King County: A Comprehensive Analysis Using Multiple Linear Regression Models
## Introduction
Accurately predicting house prices is essential for buyers, sellers, and investors in the real estate market. This project focuses on predicting house prices in King County, Washington, using multiple linear regression models. We analyze various features such as living space, quality grade, and the number of bathrooms to determine their impact on house prices. By incrementally adding features to our models, we aim to identify the most significant predictors and develop a robust model for price forecasting.

## Key Objectives 

1. Develop Accurate Predictive Models for House Prices: Create and evaluate multiple linear regression models to predict house prices in King County.
2. Identify Key Factors Influencing House Prices: Analyze various features to determine their impact on house prices.
3. Provide Actionable Recommendations for Property Value Enhancement based on model results and feature analysis.
4. Guide homeowners and real estate professionals in optimizing property quality and features to increase market value.

## Outline
1. Data Analysis and Cleaning: Loaded and cleaned the King County House Sales dataset, handling missing values and outliers.
2. Exploratory Data Analysis (EDA):  Visualized the distribution of house prices and explored relationships between features and prices.
3. Identified key features with the highest correlations to house prices.
4. Model Development: Built and evaluated 4 linear regression models with increasing complexity:
5. Model Evaluation: Assessed model performance using Mean Absolute Error (MAE) and R-squared (R²).
6. Recommendations: Provided actionable insights for homeowners and real estate professionals to enhance property values by focusing on quality improvements and optimizing living space.

## DATA UNDERSTANDING

King  County Housing data contains sales price of properties  sold between y1 and y2 as well as various fetures for specific properties. The colums are well described below:
olumn Names and descriptions for Kings County Data Set
* **id** - unique identifier  for a house
* **dateDate** - This is the date whwn the house was sold
* **pricePrice** -  is prediction target
* **bedroomsNumber** - This is the number  of Bedrooms in the House
* **bathroomsNumber** -  of bathrooms/bedrooms
* **sqft_livingsquare** -  footage of the home
* **sqft_lotsquare** -  footage of the lot
* **floorsTotal** -  floors (levels) in house
* **waterfront** - House which has a view to a waterfront
* **view** - Has been viewed
* **condition** - How good the condition is ( Overall )
* **grade** - overall grade given to the housing unit, based on King County grading system
* **sqft_above** - square footage of house apart from basement
* **sqft_basement** - square footage of the basement
* **yr_built** - Built Year
* **yr_renovated** - Year when house was renovated
* **zipcode** - zip
* **lat** - Latitude coordinate
* **long** - Longitude coordinate
* **sqft_living15** - The square footage of interior housing living space for the nearest 15 neighbors
* **sqft_lot15** - The square footage of the land lots of the nearest 15 neighbors

## STEPS 
1. Loading The Imports
2. Exploratory Data analysis , and cleaning Using Pandas
3. Data Analysis
4. Feature Selectioct
5. Exploring the Linearity Assumptions
6. Fitting Linear regression Models
7. Discussion of the Results
8. Conclusions and Recomendations

# Loading the Imports
* **In this step we import the necessary modules and packages  necessary for the the**

# Exploratory Data analysis , and cleaning Using Pandas
* **In this step we use Pandas library to understand the the structure of King County datasets using fuctions such as df.head(), df.info(), df.isna() etc**
* **this is followed by data cleaning i.e dealing with the missing values in the Waterfront column**
* **we do a little bit of visualizations to figure out the correlation between the prices and the res of the columns. The results from this step aind in determining what features we need to consider for moddeling**

# Feature Selection
* **In this step, based on the correlation coefficients, we pick features to be included in the modeling process. We consider a correlation coefficient of above 0.5**








