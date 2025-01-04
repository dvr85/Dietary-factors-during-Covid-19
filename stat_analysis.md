# Let's Dive into statistical analysis...

Insights from the scatterplot:

<img width="532" alt="image" src="https://github.com/user-attachments/assets/ecc917b1-c97c-45b4-9f27-75adf5e7a6c7" />

The raw data hints at a possible dichotomy in dietary factors:
1. Potentially Protective: Cereals, Seafood, Vegetal products
2. Potentially Risky: Animal fats, Alcohol, Processed Meat, Obesity
3. Unclear Association: Treenuts
Deeper analysis will help us understand the complex interplay between these factors and COVID-19.


Correlation Matrix & VIF:

<img width="865" alt="image" src="https://github.com/user-attachments/assets/f6b4d289-0308-4253-933f-058fa4bd6d25" />
<img width="507" alt="image" src="https://github.com/user-attachments/assets/d8081f98-1eb3-4bb1-8e63-08a935dfbb44" />


# Summary of the Null Model:

<img width="506" alt="image" src="https://github.com/user-attachments/assets/0f3242f7-d747-4de9-9193-91f26c4a18d9" />

This model is created with response variable without any predictors. The average value of the 'Confirmed' is the estimated intercept which is approximately 1.6145


# Summary of the Full Model:

<img width="405" alt="image" src="https://github.com/user-attachments/assets/cf0e575a-dc50-4a51-a0b5-33e18d37fa0c" />

From this summary,
1. Stimulants and Obesity are possibly significant and positively correlate with the confirmed cases.
2. Animal fats is nearly significant. 
3. About 61.1% variability in the Confirmed cases is being explained by the model.

Further model diagnosis is required...

<img width="489" alt="image" src="https://github.com/user-attachments/assets/8bb5bb0b-1fd4-4644-a1be-b8a35863992a" />

The model does not obey normality.


<img width="362" alt="image" src="https://github.com/user-attachments/assets/c5496015-b5fd-4368-85be-30d295645593" />

Region, Animal fats, Milk and Vegetal Products shows multicollinearity.


Box-Plot of the model:

<img width="510" alt="image" src="https://github.com/user-attachments/assets/4393b004-e2c4-45b7-943e-7878d15037ce" />

From this plot, we can observe that:
* Most of the confirmed cases are from Europe.
* Africa and North America has less confirmed cases.



# Now, let's perform transformations on the predictors...

<img width="754" alt="image" src="https://github.com/user-attachments/assets/9bce02a1-4be3-4228-a25c-bf80bb4cb624" />

But, why these transformations? 

Because,
1. Performing log transformations on Alcoholic Beverages, Animal fats, Offals, Stimulants and Obesity to reduce the skewness, variance spread, and this transformation would reduce non-linearity and improve linear relationship with the response variable.
2. Performing square root transformation on Cereals, Eggs, Seafood and Milk smoothens non-linearity without over transforming.
3. Square root transformation on Milk may reduce multicollinearity.


# Summary of the Transfomed Model:

<img width="322" alt="image" src="https://github.com/user-attachments/assets/9a5f7c13-61bb-4d23-bef4-e82d800ac551" />


<img width="286" alt="image" src="https://github.com/user-attachments/assets/fceb6770-b1e0-4c06-a374-a648e92e720a" />


From this summary, we can observe that ONLY Animal fats and Stimulants are borderline significant in this model and about 60.17% variability in the Confirmed cases is being explained by the model.


<img width="463" alt="image" src="https://github.com/user-attachments/assets/762c2249-439b-48d7-8204-e9a13f022fbc" />


The proposed transformations although, made some improvements to the scatterplots, they need more adjustments, as to make the data points align and act linearly.
Though we have transformed the model, it still shows non-normality and non-constant variance.


<img width="439" alt="image" src="https://github.com/user-attachments/assets/8d879c68-d78d-4239-8da2-d1bd87392df2" />



# Let's perform transformation on the response variable to check if it can do any better...

<img width="346" alt="image" src="https://github.com/user-attachments/assets/ffa5f4a5-07cf-41f7-9429-c23cf4094558" />

<img width="298" alt="image" src="https://github.com/user-attachments/assets/3ee4a7d0-0c82-4739-92d7-7beb2c1f83c2" />

We can notice that some of the predictors are significant with overall explainability of 70.93% R-squared.


The scatterplot of the transformed model shows that the cereals and animal fats have strong negative trend whereas offals has moderate positive trend.

<img width="449" alt="image" src="https://github.com/user-attachments/assets/c33ac9b8-bee6-4eab-99b3-a6840739ca4b" />

From the model diagnostics of the transformed model,

<img width="439" alt="image" src="https://github.com/user-attachments/assets/643ae202-7a89-4e87-921e-933e47f0748a" />

<img width="440" alt="image" src="https://github.com/user-attachments/assets/47df5b86-ae22-4876-a58c-261c7f770d02" />

* There is a significant improvement in the normality of the transformed model.
* There is slight curvature in the residuals which indicates some deviations but satisfies linearity overall.
* Although better, the slight curvatures indicate non-linearity in the model.


# Now, let's perform power transformation on the response variable and compare the models...

<img width="477" alt="image" src="https://github.com/user-attachments/assets/ec6f02d0-e11f-453e-9aac-4afa96dce842" />

<img width="307" alt="image" src="https://github.com/user-attachments/assets/b7097489-e779-48f0-963d-4ca11532a074" />

<img width="328" alt="image" src="https://github.com/user-attachments/assets/f961a26b-d8f0-404a-bddf-c69f02af1a62" />


With the power transformed response variable, the model has significantly increased the overall fit while maintaining the significance of the predictors.
Here's the scatterplot and the diagnostics of the power transformed model,


<img width="460" alt="image" src="https://github.com/user-attachments/assets/85bef4b9-fd98-4fe9-8ee2-2c3101b844a4" />

<img width="439" alt="image" src="https://github.com/user-attachments/assets/39c3e5fe-95f8-4b86-9fc4-9f116b0462b9" />

<img width="414" alt="image" src="https://github.com/user-attachments/assets/ddb32967-5723-4aab-8f10-83f54da21f27" />


# Model Assessing Method: AIC/BIC on the Transformed Models:

Based on the AIC/BIC criteria, the power transformed model (model_pow_trans) is the preferred model.

<img width="492" alt="image" src="https://github.com/user-attachments/assets/88a270c9-94c0-4e19-81ea-a4fd7f6975f8" />


But...

Though the power transformed model shows better fit, log transformed model has more interpretability and robustness.
This is because, in the data, the values of the response variable and the predictors are in percentages. Log transformation aligns well with percentage data, as coefficients can be interpreted as proportional changes.
Therefore, we go with log transformed model (model_trans).


# Forward Selection on the Transformed Model:

This is one of the model selection methods.

<img width="859" alt="image" src="https://github.com/user-attachments/assets/4e683cac-bb26-44e1-9f92-9bea88ea4582" />

<img width="602" alt="image" src="https://github.com/user-attachments/assets/7831c422-e4d2-44f9-9df6-fccff6116b8e" />

So, the model suggested by forward selection is given as: 

Confirmed ~ Region + Obesity_trans + Animal_fats_trans + Stimulants_trans + Offals_trans + Seafood_trans

<img width="364" alt="image" src="https://github.com/user-attachments/assets/cce647ee-0750-44aa-a6cf-4f1b1d94f126" />
<img width="356" alt="image" src="https://github.com/user-attachments/assets/fe0defff-2cf9-4ccf-9285-a9a552cc8478" />



# Backward Elimination on the Transformed Model:

<img width="642" alt="image" src="https://github.com/user-attachments/assets/ec63a066-8772-4663-b0f1-0219a4529d45" />
<img width="494" alt="image" src="https://github.com/user-attachments/assets/34d26702-f3f0-4edf-80f6-3ae2cfb38e6e" />

So, the model suggested by backward elimination is given as: 

Confirmed ~ Region + Obesity_trans + Animal_fats_trans  + Offals_trans

<img width="399" alt="image" src="https://github.com/user-attachments/assets/568788a8-f216-42dd-9dc4-7060d4e262cd" />

Fron this summary,
* Obesity, Animal fats and Offals are the most significant predictors, after backward elimination.
* This model explains the significant variance of 64.62%.
* Region has the highest GVIF, but it is acceptable. 


# Diagnostics of the Final Model:

<img width="468" alt="image" src="https://github.com/user-attachments/assets/9d16151d-c547-409f-bb9c-4ab968bb793d" />

<img width="463" alt="image" src="https://github.com/user-attachments/assets/f4074a90-de84-433b-9713-17356508b1b1" />

<img width="415" alt="image" src="https://github.com/user-attachments/assets/778cdbee-82e8-47e1-86cd-82ad897b9575" />

We can observe strong positive correlations between the response variable, obesity and animal fats. Also, the model is normally distributed and has constant variance.
Residuals align well with the diagonal line, suggesting that the normality assumption is mostly satisfied. A few outliers (e.g., 81, 97, and 24) deviate from the line in the tails.


Based on the AIC/BIC criteria, the backward elimination model (model_trans_main) is the preferred model over the forward selection model.

<img width="522" alt="image" src="https://github.com/user-attachments/assets/3f337721-db3a-403e-a1ac-eded32f1e832" />



# ANOVA Test:

It is one of the model selection methods.

<img width="416" alt="image" src="https://github.com/user-attachments/assets/53a6f1e4-aac3-42af-b0b9-6345c01ede5d" />

* The RSS of the models is nearly identical.
* The backward elimination model (model_trans_main) is preferred because it removes the insignificant predictors and maintains interpretability.


# The Final Model:

Log(Confirmed) =  (-5.9975) + (1.8198).(Obesity_trans )+ (0.8992).(Animal_Fats_trans ) + (−0.619).(Offals_trans)

<img width="406" alt="image" src="https://github.com/user-attachments/assets/66514037-08f2-49f0-8061-bc91cc169694" />

1. The model explains 64.6% of the variation in the final model.
2. Obesity_trans and Offals_trans are the most influential predictors, with strong statistical significance.
3. Regional differences are less conclusive, with North America showing a borderline effect.
4. North America shows a potential decrease in confirmed cases and Asia, Europe, and South America have weak or unclear effects. It means that regional differences are not strongly contributing to the confirmed cases when compared to other factors like diet and obesity.

<img width="429" alt="image" src="https://github.com/user-attachments/assets/9ce5f1eb-81c0-4cb2-bea4-7b6578c77382" />

<img width="429" alt="image" src="https://github.com/user-attachments/assets/0e1e0377-aa1d-4c68-8952-c73d40acfc96" />

<img width="390" alt="image" src="https://github.com/user-attachments/assets/16ece4db-0f02-466f-bb6e-b881bc675cfb" />

<img width="455" alt="image" src="https://github.com/user-attachments/assets/27fb967b-de0b-40c9-9b80-8d53bd4e0897" />

<img width="401" alt="image" src="https://github.com/user-attachments/assets/dd0d80ff-2d15-484f-b680-f158296be093" />


<img width="350" alt="image" src="https://github.com/user-attachments/assets/44f60e91-dfa2-42fa-9982-693d2de2f5c6" />

<img width="468" alt="image" src="https://github.com/user-attachments/assets/6c51ad39-7441-459f-bdfe-d68f46ae3688" />



# Outliers & Influential points...Do they matter?

<img width="356" alt="image" src="https://github.com/user-attachments/assets/6bcfdf28-12f7-4cb6-b528-8eec86592287" />

<img width="274" alt="image" src="https://github.com/user-attachments/assets/f65867a6-7a67-4ff9-a563-8a87cf0db93a" />

<img width="375" alt="image" src="https://github.com/user-attachments/assets/55701e3b-68d8-4883-be86-b2060ea6481c" />

<img width="449" alt="image" src="https://github.com/user-attachments/assets/93368481-94f0-4442-a404-420031df9d78" />

<img width="483" alt="image" src="https://github.com/user-attachments/assets/16edea52-26e7-4e35-9aec-7ba050542152" />

<img width="381" alt="image" src="https://github.com/user-attachments/assets/860710a8-c1e0-4943-b80f-523d81231cd7" />

Some improvement...


Let's try removing more outliers/influential data points.

<img width="392" alt="image" src="https://github.com/user-attachments/assets/3dd96913-f403-415c-a835-3fafa8777c8c" />

<img width="346" alt="image" src="https://github.com/user-attachments/assets/4b5771fb-c7d3-45b8-922b-22902b0e1f9a" />

The tails persists.
More possible influential points/outliers arise.
Existence of possible limitations.


# Prediction Intervals:

<img width="612" alt="image" src="https://github.com/user-attachments/assets/7653bcef-3c80-4af9-9183-c34ca0edbb6f" />

Removing influential points can lead to more reliable and precise predictions, as seen from the narrower prediction intervals in the second case. 

Disregarding the Influential points and outliers, might not be suggested for the model because they are special cases and the model after removing these points is not showing much improvement.
On the contrary, the prediction intervals does show some improvement, suggesting removal of these influential points.   

NOTE: I did not removed any outliers from the dataset, because I considered them as special cases.


# Disregarding Outliers/Influencers tests, Dataset speaks otherwise:

<img width="855" alt="image" src="https://github.com/user-attachments/assets/ed430449-50a3-4dd7-b0f0-2ca118209ad7" />

* 24 (Cambodia) & 30 (China): The rows mentioned have unusual diets on dataset inspection. Their average consumption of few food items in specific are, far above/below than average when compared to other and has more confirmed cases, justifying their unusual behavior. 
 * 81 (Lao people’s): The country Lao People’s Democratic Republic has followed the model behavior well and seen less confirmed cases than usual. 
* 97 (Mongolia): This country’s usual  diet is quite abnormal, meaning, although they consumed less vegetal products, and more Animal fats, they have way less Confirmed cases.


# Testing the model with 30% of the data:

<img width="337" alt="image" src="https://github.com/user-attachments/assets/fa4a1d9b-f83d-4d21-ba42-193b98e2aa71" />

<img width="259" alt="image" src="https://github.com/user-attachments/assets/f4545a97-130e-4b55-8f9e-fcd3758983e1" />

<img width="413" alt="image" src="https://github.com/user-attachments/assets/5cb78937-598a-444e-b781-9d6257ca0b96" />


Possible Reasons for poor test model:
* The testing data shows that some of the predictors are gone insignificant. This may be due to the smaller number of data points.
*  Different variances for both these datasets might cause instability of regression coefficients.
  * Possible existence of outliers can also reduce the significance of the predictors and the overall model. 
* In the Q-Q plot, the close alignment of most points to the diagonal line suggests residuals approximately follow the normal distribution, with slight deviations in the tails.

However, the model shows an R-square of 69.25% and Adj R-squared of 63.87%. The overall model with significant p value.



# Conclusions from the final model:

1. Obesity (in kcal): Regions with higher obesity rates tend to have a higher number of confirmed cases(on a logarithmic scale). A unit increase in log(Obesity in kcal+1) increases log(Confirmed) cases in (%) by 1.8198. 

2. Animal fats (in kcal): Increased consumption of animal fats is associated with a higher number of confirmed cases. A unit increase in log(Animal fats in kcal+1) increases log(Confirmed) cases in (%) by 0.8992, suggesting Animal fats are beneficial. 

3. Offals (in kcal): Higher consumption of offals (organ meats) is associated with a lower number of confirmed cases. A unit increase in log(Offals in kcal+1) decreases log(Confirmed) cases in (%) by -3.6594, suggesting offals are beneficial.


# Limitations:

1. The linear model captures some relationships between dietary factors and COVID-19 confirmed cases (transformed percentage) but leaves significant variance unexplained, as indicated by residual patterns.

2. While Region was included in the model, none of the regional coefficients (Asia, Europe, North America, and South America) were statistically significant.
This suggests that regional differences may not be relevant after accounting for dietary factors and obesity. 

3. Diagnostic plots reveal issues such as non-normality, heteroscedasticity, and high residuals/errors, suggesting model limitations due to missing critical pandemic-related variables.
This highlights the inability of the model to capture all the statistical variability. High residuals suggest that key factors influencing COVID-19 spread, and severity are missing.

4. Scatter Plots reveal not only weak and inconsistent relationships among predictors but also poorly distributed data points, even after applying the best lambda transformation and other predictor-specific transformations. 
This suggests that despite efforts to stabilize variances and linearize relationships, the inherent structure and variability of the data remain challenging, limiting the model's explanatory power.

5. While diet plays a role in health stability, pandemics like COVID-19 are influenced by broader factors—country’s border safety protocols, public health policies, quarantine measures, household hygiene, vaccination rates, drug intake, airborne transmission, and more—which are absent in our dataset and are unaccounted for in our analysis.
 


