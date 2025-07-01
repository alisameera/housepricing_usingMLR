# House Price Prediction Using Multiple Linear Regression - Project Report

## Introduction
The real estate market is characterized by its dynamic nature, making the accurate prediction of house prices a vital task for buyers, sellers, and investors alike. This project leverages a comprehensive dataset to develop a Multiple Linear Regression (MLR) model aimed at estimating house prices based on a variety of housing features. The initiative seeks to provide actionable insights into the factors driving property values and deliver reliable predictions for unseen data.

## Problem Statement
The primary challenge addressed in this project is the development of a predictive model capable of estimating house prices using a dataset that includes diverse attributes such as area, number of bedrooms, bathrooms, and amenities like air conditioning or parking. The dynamic and complex nature of the real estate market necessitates a robust analytical approach to support informed decision-making.

## Objectives
The key objectives of this project are threefold:
- To identify the most significant features that influence house prices.
- To generate accurate predictions for house prices on a test dataset.
- To evaluate the model's performance using appropriate metrics, including R-squared and Mean Squared Error.

## Dataset Overview
The project utilizes the `Housing.csv` dataset, which comprises 545 rows and 13 columns. The dataset provides a detailed representation of housing features, categorized into numerical and categorical variables. Below is a table summarizing each column and its description:

| **Column Name**    | **Description**                                      |
|---------------------|------------------------------------------------------|
| price              | The selling price of the house (in currency units, likely millions). |
| area               | The total area of the house (in square feet).        |
| bedrooms           | The number of bedrooms in the house.                 |
| bathrooms          | The number of bathrooms in the house.                |
| stories            | The number of stories (floors) in the house.         |
| mainroad           | Indicates whether the house is located on a main road (yes/no). |
| guestroom          | Indicates the presence of a guest room (yes/no).     |
| basement           | Indicates the presence of a basement (yes/no).       |
| hotwaterheating    | Indicates the presence of hot water heating (yes/no).|
| airconditioning    | Indicates the presence of air conditioning (yes/no). |
| parking            | The number of parking spaces available.              |
| prefarea           | Indicates whether the house is in a preferred area (yes/no). |
| furnishingstatus   | The furnishing status of the house (furnished, semi-furnished, unfurnished). |

The dataset is noted for its completeness, with no missing values or duplicate entries, ensuring a solid foundation for analysis.

## Data Exploration and Insights
Initial exploration of the dataset revealed a well-structured collection with a mix of numerical and categorical variables. The data quality is high, with no missing values or duplicates, facilitating a seamless analytical process. Numerical features such as price and area exhibit significant variability, with potential skewness that may impact linear regression assumptions. High-priced houses and larger areas suggest a premium market segment, while the majority of properties are more modest, with a median price of approximately 4.34 million and an area of around 4600 square feet. Categorical features, including binary variables like mainroad and multi-category furnishingstatus, require encoding for effective modeling.

Visualizations further highlighted key relationships. The pairplot indicated that area and bathrooms have the strongest positive correlations with price, while bedrooms, stories, and parking show weaker but positive trends. Boxplots for categorical variables demonstrated that air conditioning, preferred area, and furnished status significantly increase house prices, with mainroad and guestroom also contributing positively, albeit to a lesser extent.

## Model Development and Evaluation
The MLR model was developed following preprocessing steps that included encoding categorical variables and scaling numerical features. The model's performance was assessed using a 70-30 train-test split, yielding an R-squared value of 0.67 on the test set, indicating that it explains 67% of the variance in house prices. The Root Mean Squared Error (RMSE) of approximately 1.32 million reflects the average prediction error in price units, suggesting a reasonable but improvable fit.

## Feature Importance Insights
Analysis of feature importance revealed that area and bathrooms are the most significant positive predictors of house prices, with coefficients around 2.5 million and 2.2 million, respectively. Moderate contributors include stories, hotwaterheating, and airconditioning, each with coefficients ranging from 1.2 to 1.5 million. Notably, the unfurnished status negatively impacts price (coefficient ~ -0.5 million) compared to the furnished baseline, while features like guestroom, basement, and semi-furnished have weaker influences (0.5–0.8 million).

## Final Summary

### Conclusion
The Multiple Linear Regression model successfully predicts house prices, achieving an R-squared of 0.67 on the test set. Key features influencing price include area, bathrooms, and air conditioning, underscoring their importance in the real estate market. This model provides a solid baseline for understanding price determinants and offers reliable predictions for unseen data.

### Implementation
The project was implemented using Python, leveraging libraries such as pandas for data manipulation, seaborn and matplotlib for visualization, and statsmodels and scikit-learn for modeling and evaluation. The dataset was preprocessed to handle categorical variables and scaled to ensure equitable feature contribution, followed by model training and validation on a split dataset.

### Suggestions
To enhance the model's performance, future work should consider addressing potential multicollinearity using the Variance Inflation Factor (VIF). Additionally, experimenting with feature selection or regularization techniques such as Ridge and Lasso, as well as exploring non-linear models like Random Forest, could yield improved accuracy. These enhancements would further refine the predictive capabilities and adaptability of the model to varying market conditions.
