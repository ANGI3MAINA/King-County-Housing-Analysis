
### README

Predicting House Prices in King County: A Comprehensive Analysis Using Multiple Linear Regression Models

## Overview

This repository contains a Jupyter Notebook titled `index.ipynb`, which focuses on predicting house prices in King County, Washington, using multiple linear regression models. The analysis leverages various property features to provide insights for different stakeholders in the real estate industry, such as investors, agents, developers, and market analysts.

## Table of Contents

1. [Introduction](#introduction)
2. [Problem Statement](#problem-statement)
3. [Objectives](#objectives)
4. [Data Sources and Description](#data-sources-and-description)
5. [Data Understanding](#data-understanding)
6. [Data Cleaning](#data-cleaning)
7. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
8. [Model Building](#model-building)
9. [Model Evaluation](#model-evaluation)
10. [Conclusion](#conclusion)
11. [Recommendations](#recommendations)
12. [Running the Notebook](#running-the-notebook)
13. [Contributing](#contributing)
14. [License](#license)

## Introduction

Accurately predicting house prices is essential for buyers, sellers, and investors in the real estate market. This project focuses on predicting house prices in King County, Washington, using multiple linear regression models. We analyze various features such as living space, quality grade, and the number of bathrooms to determine their impact on house prices. By incrementally adding features to our models, we aim to identify the most significant predictors and develop a robust model for price forecasting.

## Problem Statement

The Real Estate Development Company is looking to enter the King County housing market. They face significant challenges in identifying the most important features that influence housing prices. The objective is to develop a comprehensive analysis that helps the company make data-driven decisions on property investments by focusing on key factors such as square footage, property grade, the number of bathrooms, and location. By understanding these factors, the company aims to create a profitable sales strategy targeting houses with the highest prices in the market.

## Objectives

1. **Assist Real Estate Investors and Home Buyers:**
   - **Objective:** Determine the influence of key property features on house prices to guide investment and purchasing decisions.
   - **Action:** Identify how changes in square footage, property grade, and other significant features affect the overall price of properties.

2. **Guide Real Estate Agents:**
   - **Objective:** Understand the impact of various property features on house prices to enhance marketing strategies.
   - **Action:** Emphasize the role of significant features such as property grade and square footage in influencing pricing when representing homes to potential buyers.

3. **Advise Property Developers:**
   - **Objective:** Evaluate the effect of adding and enhancing property features on house prices to inform development strategies.
   - **Action:** Assess how the inclusion of additional bathrooms and improvements in property grade impact property valuation and buyer preferences.

4. **Support Real Estate Market Analysts:**
   - **Objective:** Analyze the variation in house prices across different zip codes to refine market assessments.
   - **Action:** Examine how zip codes and other location-based features affect property prices and identify which areas are associated with higher or lower values.


## Data Sources and Description

The dataset used for this project is the King County House Sales dataset, which includes comprehensive information on property features and sale prices. This dataset is suitable for evaluating the effects of different aspects of houses on prices due to its completeness and relevance.

### Data Columns

- `id`: Unique identifier for a house.
- `date`: Date when the house was sold.
- `price`: Sale price (prediction target).
- `bedrooms`: Number of bedrooms.
- `bathrooms`: Number of bathrooms.
- `sqft_living`: Square footage of the home.
- `sqft_lot`: Square footage of the lot.
- `floors`: Total floors (levels) in the house.
- `waterfront`: Whether the house has a view of a waterfront.
- `view`: Number of times the house has been viewed.
- `condition`: Overall condition of the house.
- `grade`: Overall grade given to the housing unit.
- `sqft_above`: Square footage of the house apart from the basement.
- `sqft_basement`: Square footage of the basement.
- `yr_built`: Year when the house was built.
- `yr_renovated`: Year when the house was renovated.
- `zipcode`: Zip code of the property.
- `lat`: Latitude coordinate.
- `long`: Longitude coordinate.
- `sqft_living15`: Living space of the nearest 15 neighbors.
- `sqft_lot15`: Land lots of the nearest 15 neighbors.

## Data Understanding

The dataset contains relevant features that are crucial for meeting our objectives. However, some limitations include non-normal distribution of data, missing values, and potential outliers.

## Data Cleaning

### Handling Missing Values

Waterfront Column:
The proportion of missing values in the waterfront column was calculated.
Missing values in the waterfront column were imputed with the mode of the column.
The waterfront column was then converted to a categorical type.

## Exploratory Data Analysis (EDA)

### Visualizing Data

- Use histograms and box plots to understand the spread and identify outliers.
- Create a correlation heatmap to identify relationships between features.

```python
# Correlation Heatmap
plt.subplots(figsize=(20, 15))
sns.heatmap(data.corr(), cmap="coolwarm", annot=True)
plt.show()
```

## Model Building
In this project, we incrementally built three multiple linear regression models to predict house prices. Each model added more features to evaluate their impact on the prediction accuracy. We assessed each model based on performance metrics such as Mean Squared Error (MSE) and R-squared (R²).

Model 1: Baseline Model
Features Used: Square footage of living space (sqft_living).
Training: The model was trained using sqft_living as the sole predictor.
Evaluation: Performance metrics were calculated to serve as a baseline for comparison with subsequent models.

Model 2: Extended Model
Features Used: sqft_living, Number of bathrooms (bathrooms), and Property grade (grade).
Training: The model included additional features to improve prediction accuracy.
Evaluation: Performance metrics were recalculated to assess the impact of the new features.

Model 3: Comprehensive Model
Features Used: sqft_living, bathrooms, grade, Square footage of the lot (sqft_lot), and Year built (yr_built).
Training: Additional features were included for a more comprehensive model.
Evaluation: Final performance metrics were calculated to determine the effectiveness of the comprehensive model.

```python
# Train Test Split
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.2, random_state=42)

# Train the model
model = LinearRegression()
model.fit(x_train_scaled, y_train)
y_pred = model.predict(x_test_scaled)
```

## Model Evaluation

- Comparisons for  model predictions with actual values with calculate performance metrics was conducted to evaluate a model performance, and comparing across models

```python
# Model Evaluation
mse = mean_squared_error(y_test, y_pred)
mae = mean_absolute_error(y_test, y_pred)
r2 = r2_score(y_test, y_pred)

print("MSE:", mse)
print("MAE:", mae)
print("R2:", r2)
```

## Conclusion

The OLS regression analysis of house prices in King County reveals the following key insights:

Square Footage (sqft_living): This feature shows a strong positive relationship with house prices. Each additional square foot increases the house price by approximately $0.45. This indicates that larger homes generally command higher prices.

Property Grade (grade): Higher grades are associated with higher house prices. Each one-point increase in the property's grade increases its price by about $0.19. This suggests that better-quality homes are valued more highly in the market.

Number of Bathrooms (bathrooms): Unexpectedly, each additional bathroom decreases the house price by approximately $32.00. This negative impact suggests that adding more bathrooms may not always lead to higher property values, contrary to common assumptions.

Zipcode (zipcode): The effect of zipcodes on house prices varies significantly. Some zipcodes (e.g., 98004 and 98005) are associated with higher prices, while others have a less favorable effect. Location remains a crucial factor in determining property values.

Overall, these findings highlight the importance of square footage, property grade, and location in influencing house prices. However, the negative relationship between the number of bathrooms and house prices warrants further investigation.

## Recommendations

### Business Strategy Implications

1. **Target Larger Houses**: Focus on acquiring or developing larger houses to maximize potential sales prices.
2. **Focus on High-Grade Houses**: Develop or invest in properties with higher quality finishes and features.
3. **Investigate Bathroom Anomaly**: Re-examine properties with many bathrooms to understand the negative price relationship.
4. **Consider Additional Predictors**: Incorporate additional variables such as location and lot size for a more comprehensive model.
5. **Use Predictive Analytics for Marketing**: Create targeted marketing strategies to attract high-end buyers.

## Running the Notebook

To run the notebook, follow these steps:

1. Clone the repository to your local machine.
2. Open a terminal and navigate to the cloned repository.
3. Open the `index.ipynb` notebook from the Jupyter interface.
4. Run the cells in sequential order to execute the analysis.

## Contributing

Contributions are welcome! To contribute, follow these steps:

1. Fork this repository.
2. Create a new branch:

3. Make your changes and commit them:

4. Push to the branch:

5. Create a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more information.

---

This README provides a comprehensive guide to navigating and utilizing the `index.ipynb` notebook. It ensures that users understand the structure, data, and steps needed to run the analysis effectively.
