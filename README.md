# Understanding Trends in Property Market Value in Washington

This project aims at analysing various factors including: structural features, location, and temporal factors, to understand what influences global housing prices. 

![Image](https://github.com/Mutendwa/Group-10-Phase-2-Project/blob/main/Images/Visuals.png)

## Business Understanding

The real estate agency aims to provide comprehensive services to homeowners looking to buy or sell their properties. One significant aspect of their services involves advising homeowners on potential renovations that could increase the estimated value of their homes. This guidance is crucial in assisting homeowners in making informed decisions about investing in renovations that will yield a favourable return on investment (ROI) when they decide to sell their property.

Stakeholder:

Real Estate Agency

### Problem Statement:

The real estate agency lacks an efficient method and face challenges in understanding the factors influencing the potential increase in the estimated value of a property. Without this capability, homeowners may not receive optimal advice regarding which renovations to pursue and what factors to consider when buying a property, leading to potential dissatisfaction or loss of value. Therefore, there is a pressing need to develop a data-driven solution that can accurately predict the impact of various renovations/House Features on the estimated value of houses, enabling the agency to provide tailored and informed recommendations to homeowners in King City County.

Objectives:
Analyze the relationship between property attributes such as lot area, no of bedrooms, the grade, condition , etc. and their impact on house prices. Which factors are the most influential and the least on house prices.

Offer Reccomendations: Reccomend insights to the Real Estate Agency that will help them understand how the property attributes impact the value of a property

Research Questions
What is the combined influence of structural features, location, and temporal factors on the market price of houses, and how can we optimally model these relationships to predict housing prices with high accuracy?
Is there a statistically significant difference in lot size (sqft_lot) among houses with varying grades?
Do houses with a waterfront view have a significantly higher average price compared to houses without a view?
To what extent does the combined influence of bedrooms and bathrooms affect the price of a house?


## Technologies
Python\
Jupyter\
Numpy\
Pandas\
Scikit learn\
StatsModel

## Project description
In this project we look at:

* What is the combined influence of structural features, location, and temporal factors on the market price of houses, and how can we optimally model these relationships to predict housing prices with high accuracy?
* Is there a statistically significant difference in lot size (sqft_lot) among houses with varying grades?
* Do houses with a waterfront view have a significantly higher average price compared to houses without a view?
* To what extent does the combined influence of bedrooms and bathrooms affect the price of a house?

## Correlation Analysis
`sqft_living` exhibits the highest correlation with `price`, indicating that the size of the living area strongly influences the price of a house.\
Features like `grade` and '`sqft_above`' also demonstrate significant positive correlations with `price`, suggesting that overall quality and living space contribute substantially to house pricing.

![Image](https://github.com/Mutendwa/Group-10-Phase-2-Project/blob/main/Images/Correlation%20Plots.png)

## Simple Linear Regression
The `price` was chosen as the target variable and `grade`  as the predictor variable for the baseline model. This choice was motivated by the strong correlation between these two variables, measured at 0.668. The model accounted for ~49.3% of variance observed in the `price`. Additionally, `grade` demonstrated lower collinearity with other predictors, thereby reducing concerns of multicollinearity. We transformed the target variable so that it approaches a normal distribution.

![Image](https://github.com/Mutendwa/Group-10-Phase-2-Project/blob/main/Images/Simple%20Linear%20regression.png
)

## Multiple Linear Regression
More predictors including: `waterfront`, `view`, `grade`,`floors`, `yr_built`, `bedrooms`, `bathrooms`, `sqft_living15` were used for this model. The model explained a variance of ~ 62.9% on the price. All model coefficients are statistically significant, with t-statistic p-values well below 0.05.

![Image](https://github.com/Mutendwa/Group-10-Phase-2-Project/blob/main/Images/Multiple%20Regression%20model.png)

## Polynomial Regression and Model Metrics
The independent variable(s) and the dependent variable is modeled as an nth-degree polynomial. It extends linear regression by allowing the relationship between variables to be modeled as a curve rather than a straight line. In thic case we use it to determine whether its a better fit compared to the multiple linear regression. The Polynomial regression is a better model in this case, since It explains ~ 64.8% of variance in house `prices` which is slighlty higher than the variance explained using the multiple linear regression . The Root Squared Mean Error for polynomial regression is also lower than that of the linear model.This implies that the polynomial regression performed better.

![Image](https://github.com/Mutendwa/Group-10-Phase-2-Project/blob/main/Images/Residual%20plots%20polynomial%20regression.png)


## Recommendations
* The shareholder should encourage homeowners to do renovations so as to improve the overall condition and raise the property's grade as this has a great impact on the value of a house. 

* There is also high impact of square footage of living space on house prices and use this information to justify higher listing prices for properties with more extensive square footage.
   
* The number of bathrooms and bedrooms also have a positive correlation with the value of a house. Therefore, during renovation adding a bedroom would increase the value of the house! 

* For price prediction of the houses, we recommend use of Polynomial regression model as it gives a high R- squared value which means that we can get a better and more accurate price value.
  
• Quality and Lot Size Connection: A property's condition directly correlates with its lot size, highlighting the importance of upkeep and modernization in enhancing market value.

• Premium on Waterfront Views: Properties boasting waterfront views command higher market prices, representing a lucrative investment for buyers and a unique selling proposition for owners.

• Optimal Bedrooms and Bathrooms Mix: The combination of bedrooms and bathrooms significantly impacts house pricing, guiding strategic property selection for buyers and effective marketing for sellers.

## Project Limitations
* Geographical Focus: The dataset only covers the Northeastern region, limiting its usefulness for predicting housing prices nationwide. This means our findings might not apply to other areas of the country.

* Multicollinearity: We found that some variables in our dataset are strongly related to each other. This can make our predictions biased or inaccurate.


## Project Deliverables
* [Notebook](https://github.com/Mutendwa/Group-10-Phase-2-Project/blob/main/Final_Project.ipynb)
* [Presentation](https://github.com/Mutendwa/Group-10-Phase-2-Project/blob/main/Understanding%20Trends%20In%20Property%20Market%20Value.pptx)
* Pdf files

## Group Members
Team Lead: [Diana Olulo](https://github.com/Dee-Olulo)

Other members:\
[Shuru Ebale](https://github.com/shuruebale)\
[Edwin Mutendwa](https://github.com/Mutendwa)\
[Pheminah Wambui](https://github.com/Pheminah)\
[Caleb Asati](https://github.com/CarlAK96)
