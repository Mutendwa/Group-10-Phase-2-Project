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

### Data Understanding
The dataset comprises 21,597 entries across 21 columns, reflecting various aspects of housing data. Most columns show a non-null count, indicating a relatively complete dataset. However, there are some key points to note regarding potential missing values.

### Column Names and Descriptions for King County Data Set
#### Property Attributes

id - Unique identifier for a house

date - Date house was sold

price - Sale price (target variable)

bedrooms - Number of bedrooms

bathrooms - Number of bathrooms

sqft_living - Square footage of living space in the home

sqft_lot - Square footage of the lot

floors - Number of floors (levels) in house

waterfront - Whether the house is on a waterfront eg a lake

view - Quality of view from house

condition - How good the overall condition of the house is. Related to maintenance of house. explanation of each condition code

grade - Overall grade of the house. Related to the construction and design of the house. explanation of each building grade code

sqft_above - Square footage of house apart from basement

sqft_basement - Square footage of the basement

yr_built - Year when house was built

yr_renovated - Year when house was renovated

zipcode - ZIP Code used by the United States Postal Service

lat - Latitude coordinate

long - Longitude coordinate

sqft_living15 - The square footage of interior housing living space for the nearest 15 neighbors

sqft_lot15 - The square footage of the land lots of the nearest 15 neighbors

### Data Source and it’s suitability for the project

The data source utilized for our analysis was obtained from GitHub, specifically from the House Price Dataset uploaded by Learn-Co-Curriculum in 2021. This dataset includes variables such as date, view, square footage of above-ground living space, square footage of basements, year of renovation, zipcode, latitude, longitude, square footage of living areas, and square footage of lots. These variables are crucial for addressing our research questions.

Reference Learn-Co-Curriculum. (2021). House Price Dataset. GitHub. https://github.com/learn-co-curriculum/dsc-phase-2-project-v2-3

### LImitation
Nonetheless, it is important to acknowledge that this dataset, being from 2021, may not fully reflect the current market conditions. Market dynamics could have shifted in the intervening period, potentially impacting the relevance of our analysis. Additionally, as this is secondary data, there may be limitations regarding its accuracy and applicability to our current study.
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

![Capture4](https://github.com/Mutendwa/Group-10-Phase-2-Project/assets/151445934/c1b322ae-64b0-4b2a-9061-8ac205160eef)

## Multiple Linear Regression
More predictors including: `waterfront`, `view`, `grade`,`floors`, `yr_built`, `bedrooms`, `bathrooms`, `sqft_living15` were used for this model. The model explained a variance of ~ 62.9% on the price. All model coefficients are statistically significant, with t-statistic p-values well below 0.05.

![Image](https://github.com/Mutendwa/Group-10-Phase-2-Project/blob/main/Images/Multiple%20Regression%20model.png)

## Polynomial Regression and Model Metrics
The independent variable(s) and the dependent variable is modeled as an nth-degree polynomial. It extends linear regression by allowing the relationship between variables to be modeled as a curve rather than a straight line. In this case we use it to determine whether its a better fit compared to the multiple linear regression. The Polynomial regression is a better model in this case, since It explains ~ 64.8% of variance in house `prices` which is slighlty higher than the variance explained using the multiple linear regression . The Root Squared Mean Error for polynomial regression is also lower than that of the linear model.This implies that the polynomial regression performed better.

![Capture3](https://github.com/Mutendwa/Group-10-Phase-2-Project/assets/151445934/fb16e8aa-4b83-4c0d-8e4f-7aaee704ac56)

The plot above shows the difference between the predictedvalues and the actual values.
The spread of the residuals of the polynomial regression seems to be fairly constant across the range of fitted values. This suggests that the assumption of homoscedasticity may be met.


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
### Conclusion
The study into the dynamics of housing price determinants underscores the complexity and multifaceted nature of real estate markets. The study reveals that a deep and nuanced understanding of regional trends, economic indicators, and a plethora of other variables is essential for crafting accurate and reliable predictive models. The insights gained from this research highlight the importance of adopting comprehensive and sophisticated analytical frameworks that can accommodate the intricate interplay of factors affecting housing prices.

Moreover, the findings underscore the value of continuous refinement and expansion of data collection methodologies, emphasizing the need for high-quality, diverse datasets. Such datasets are crucial for developing models that are not only robust and predictive but also reflective of the real-world variability and diversity of housing markets across different regions.

This research, therefore, not only contributes to the academic discourse on housing price prediction but also provides practical insights for policymakers, urban planners, and investors. By fostering a deeper understanding of market dynamics and improving predictive methodologies, we can better navigate the complexities of the housing market, ultimately contributing to more sustainable and equitable urban development.

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
