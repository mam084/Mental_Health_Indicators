
# Time-Series Modeling of Mental Health Indicators in the United States (2020–2024)

## Overview

This project analyzes and models national mental health trends in the United States during and following the COVID-19 pandemic. Using CDC Household Pulse Survey data, the study examines reported symptoms of anxiety and depressive disorders from 2020 through 2024. The goal is to quantify shifts in mental health over time, identify demographic disparities, and evaluate predictive modeling approaches for forecasting future trends.

The project combines exploratory data analysis, demographic comparison, and multiple predictive modeling techniques to better understand how mental health indicators evolved throughout and after the pandemic period.

---

## Dataset

The data originates from the CDC Household Pulse Survey, conducted in partnership with the U.S. Census Bureau. The survey collected nationwide responses on mental health symptoms across demographic categories including:

- Age  
- Gender identity  
- Race and ethnicity  
- Education level  
- Disability status  
- Geographic region  

The dataset spans April 2020 through early 2024, providing high-frequency observations suitable for time-series analysis.

Minor missing segments were handled through interpolation when appropriate, while larger missing intervals were excluded to preserve model reliability.

---

## Exploratory Data Analysis

Initial analysis focused on identifying structural patterns and demographic variation in reported anxiety and depression symptoms.

Key findings include:

- A substantial spike in reported symptoms in early 2020, rising sharply from pre-pandemic baselines.
- Gradual stabilization and partial decline in mean symptom levels from 2021 onward.
- Significant variation across states, with some regions exhibiting strong correlation patterns.
- Clear demographic trends, particularly:
  - Higher reported symptom levels among younger adults (18–29).
  - Lower reported symptom levels among older adults (60+).
  - Elevated rates among transgender respondents and racially mixed individuals.

Visualizations included heatmaps of state correlations, violin plots of age-based distributions, and interactive regional mapping to examine geographic disparities.

---

## Predictive Modeling

Three modeling approaches were implemented and compared.

### Bayesian Updating Model

A Bayesian model was first developed to iteratively update posterior means as new data became available. This approach provided uncertainty estimates through confidence intervals but achieved a root mean square error (RMSE) of approximately 6.35, indicating moderate predictive performance.

### Prophet Time-Series Model

To better capture seasonality and trend components, a Prophet model was trained on 2020–2022 data and evaluated on 2023 observations. This model reduced RMSE to approximately 3.82 and demonstrated improved ability to track cyclical patterns and long-term trend movement.

### Linear Regression Model

A least squares regression model examined the relationship between age and reported symptom levels. Results showed a negative association between age and symptom frequency, with an R² of approximately 0.84. However, a relatively high RMSE indicated limitations in predictive precision.

---

## Results

The Prophet time-series model provided the strongest forecasting performance among the tested approaches. It successfully captured seasonal variation and broader trend shifts in mental health indicators over time.

The analysis confirms that:

- The pandemic corresponded with a dramatic surge in anxiety and depression symptoms.
- Mental health impacts were not evenly distributed across demographics.
- Time-series modeling techniques are effective tools for forecasting population-level mental health trends.

---

## Tools and Libraries

- Python  
- Pandas  
- Matplotlib  
- Scikit-learn  
- Prophet  

---

## Future Work

Future research could improve predictive accuracy by incorporating additional explanatory variables such as:

- Economic indicators  
- Regional unemployment data  
- Climate and temperature trends  
- Policy intervention timing  

Expanding feature sets and experimenting with hybrid or hierarchical models may further enhance forecasting reliability.
