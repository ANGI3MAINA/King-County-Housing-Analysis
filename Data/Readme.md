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

King  County Housing data contains sales price of properties  sold between 2014 and 2015 as well as various fetures for specific properties. The colums are well described below:
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
4. Feature Selection
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

# Exploring Linearity Models
 Some of the linearity assumptions checked in the  fetures selected models include;
 # 1. Normality
 * **Checking Skewness is the linearity of the features distribution** -   The Skewness of the features was outlined as below:
**price          4.023116**

**sqft_living    1.473192**

**grade          0.788431**

**bathrooms      0.519766**

**bedrooms       2.023584**

**floors         0.614843**


this informed the next  step which was dealing with outliers

* **Removing Outliers**- the skeness of the data significantly reduced after removing the outliers as shown below:

price; 0.778495

sqft_living ; 0.518488

grade  ; 0.259773

bathrooms ;-0.040541

bedrooms; 0.234265

floors; 0.768639

* **Log Transformation** - This was key to enhancing normality of the features' distribution.
upon visualization, most of the features assumed near normal distribution.

# 2. Heteroscedasticity
We fitted the fitted fatures against the residuals using a scatter plot. The cone-shaped distribution indicated  that the fetures were heteroscedastic hence acsertaining the efficiency of our confidence intervals.

## Fitting Linear Regression Models

#### MODEL 1: Simple regression with sqft_living and price
This model predicted house prices base on the square footage of interior housing living space
The model's R2 was,0.3052 with and MSE of 0.2912

#### MODEL 2: Sqft_living, grade and price 

In this model we increased the number of predictors to two ;overall grade given to the housing unit and the square footage of interior housing living space
The model's R2 was,0.3725 with and MAE of 0.3725

#### MODEL 3: Regression with Three Features (sqft_living, grade, bathrooms)
In this model we increased the number of predictors to three ;overall grade given to the housing unit, the square footage of interior housing living space and the number of bathrooms
The model's R2 was,0.2739 with and MAE of 0.3742

#### MODEL 4: regression with all the selected features 
In this model we increased the number of predictors to four ;overall grade given to the housing unit, the square footage of interior housing living space the number of bathrooms, total number of floors per house and the total number of bathrooms.
The model's R2 was,0.3769 with and MAE of 0.2731.


## Discussion of the Results
The analysis of house prices using multiple linear regression models demonstrated that adding more features incrementally improves predictive accuracy and explanatory power. Model 1, with only sqft_living, explained 30.53% of the variance in house prices, indicating a moderate relationship between living area size and prices.

Model 2 included grade, increasing the R-squared to 37.26%, showing that house quality is also significant. However, the MAE increased slightly, suggesting potential overfitting. Model 3, which added bathrooms, improved the MAE to 0.2740 and the R-squared to 37.43%, confirming the relevance of the number of bathrooms.

Model 4, incorporating all features, had the best performance with an MAE of 0.2731 and an R-squared of 37.69%. This comprehensive model highlighted that multiple features together provide a better understanding of house price determinants. Key coefficients showed grade (0.1793) had the most substantial positive impacts on prices.

The analysis of house prices using multiple linear regression models demonstrated that adding more features incrementally improves predictive accuracy and explanatory power. Model 1, with only sqft_living, explained 30.53% of the variance in house prices, indicating a moderate relationship between living area size and prices.

Model 2 included grade, increasing the R-squared to 37.26%, showing that house quality is also significant. However, the MAE increased slightly, suggesting potential overfitting. Model 3, which added bathrooms, improved the MAE to 0.2740 and the R-squared to 37.43%, confirming the relevance of the number of bathrooms.

Model 4, incorporating all features, had the best performance with an MAE of 0.2731 and an R-squared of 37.69%. This comprehensive model highlighted that multiple features together provide a better understanding of house price determinants. Key coefficients showed grade (0.1793) had the most substantial positive impacts on prices.

## Conclusions 

Best Predictive Model: Model 4, using all features, is the most accurate and robust for predicting house prices. It balances prediction accuracy and explanatory power effectively.

Key Influencing Features: Grade is the most influential features positively affecting house prices. Enhancing property quality and optimizing living space can significantly increase property values.


## Key Recommendations

1. Enhance Property Quality: Invest in improving the overall quality (grade) of properties. High-quality materials and design standards lead to substantial returns.

2. Optimize Living Space: Increase living space (sqft_living) thoughtfully, ensuring additional space enhances functionality and appeal without unnecessary expansions.

3. Balanced Feature Development: Aim for a balanced approach in adding features like floors, bathrooms, and bedrooms. Focus on usability, aesthetics, and overall appeal to avoid potential negative impacts on house prices.

Implementing these recommendations helps stakeholders understand the factors influencing house prices and make informed decisions to enhance property value effectively.














