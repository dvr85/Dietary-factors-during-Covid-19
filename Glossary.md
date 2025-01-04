# What is Multiple Linear Regression?

A Multiple Linear Regression (MLR) is a statistical technique that models the relationship between a dependent variable Y and multiple independent (or explanatory) variables X1,X2,...Xp. 

The formal representation of the MLR model is:

Y = β0 + β1X1 + β2X2 +....+ βpXp + ϵ

where,
* Y = Dependent variable (the outcome we are trying to predict).
* X1,X2,...Xp = Independent variables (predictors).
* β0 = Intercept, representing the expected value of Y when all X variables are 0.
* β1,β2,...βp = Regression coefficients, representing the change in Y associated with a one-unit increase in Xi, holding all other predictors constant.
* ϵ = Random error term, assumed to be normally distributed with a mean of 0 and variance σ2.

Assumptions of the MLR Model:
* Linearity: The relationship between each predictor and the outcome is linear.
* Independence: Observations are independent of each other.
* Homoscedasticity: The variance of residuals (errors) is constant across all levels of the independent variables.
* Normal assumption of Residuals: The residuals (errors) are normally distributed, particularly important for inference.
* No Multicollinearity: Independent variables are not highly correlated with each other.


# Data Exploration Tools for MLR:
* Correlation Matrix: Check for multicollinearity by examining correlations between predictors, as high correlations can indicate multicollinearity issues.
* Scatterplots and Effect plots: Visualize relationships between variables to detect potential linear associations and outliers.
* Boxplots: Use boxplots to identify outliers and understand the spread of each region.

# Model Diagnostic Tools for MLR:
* Residual Plots: Plot residuals against fitted values to check for homoscedasticity and detect non-linearity. A random scatter suggests homoscedasticity.
* Effect Plot: Plot which shows the relationship between response and a predictor while holding other predictors constant.
* Variance Inflation Factor (VIF): Measures multicollinearity by quantifying how much variance in a predictor is explained by other predictors. VIF values above 10 may suggest serious multicollinearity.

# Model Selection Tools for MLR:
* Adjusted R square: Adjusted R square accounts for the number of predictors in the model, allowing comparison of models with different numbers of predictors.
* Forward & Backward Selection: These procedures add or remove predictors based on statistical significance (e.g., p-values) to find an optimal model.
* Akaike Information Criterion (AIC) and Bayesian Information Criterion (BIC): Lower values indicate better models while balancing model complexity and fit. BIC penalizes complexity more than AIC.
