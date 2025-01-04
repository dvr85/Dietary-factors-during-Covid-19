# Nutrition & COVID-19 (Does Diet Matter in fighting Pandemic?)

This is a case study explores the statistical analysis of dietary habits of an individual during the COVID-19 pandemic.

# Introduction:

This study explores the relationship between energy intake (units = kcal) from various nutritional indicators (e.g., animal products, Vegetable products, cereals, and obesity rates) and the percentage of confirmed COVID-19 cases across regions. 

By employing a multiple linear regression model, it investigates how energy intake from these dietary sources correlate with infection rates, providing insights to inform public health strategies and enhance resilience against infectious diseases.

Representation of MLR model : Confirmed(%) = β0 + β1(Alcoholic_Beverages) + β2(Animal _fats) + β3(Cereals) + β4(Eggs) + β5(Seafood) + β6(Milk) + β7(Offals) + β8(Stimulants) + β9(Treenuts) + β10(Vegetal_Products) + β11(Obesity)  


# About Data:

Response variable : The percentage of confirmed cases of COVID-19.

Predictors in Dataset : Alcoholic Beverages, Cereals, Seafood, Offals, Stimulants, Meat, Milk, Sugar & Sweeteners, Eggs, Animal fats, Vegetal Products and Obesity.

Categorical variable: Region (Asia, North America, South America, Africa, Europe).

Dataset : https://www.kaggle.com/datasets/mariaren/covid19-healthy-diet-dataset


# Let's Dive into statistical analysis:

Insights from the scatterplot:

<img width="532" alt="image" src="https://github.com/user-attachments/assets/ecc917b1-c97c-45b4-9f27-75adf5e7a6c7" />

The raw data hints at a possible dichotomy in dietary factors:
1. Potentially Protective: Cereals, Seafood, Vegetal products
2. Potentially Risky: Animal fats, Alcohol, Processed Meat, Obesity
3. Unclear Association: Treenuts
Deeper analysis will help us understand the complex interplay between these factors and COVID-19.


