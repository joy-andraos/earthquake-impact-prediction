# earthquake-impact-prediction
# Dataset Description
This dataset provides insights into earthquakes worldwide from May 5, 1995, to June 8, 2023: https://www.kaggle.com/datasets/patricklford/earthquakes-historical-data-and-live-data
Earthquakes occur when built-up stress from tectonic plate movement is released, generating seismic waves. The relationship between plate tectonics and earthquakes is explored, focusing on how different factors influence seismic intensity. The context of this project is risk analysis: assessing the significance of future earthquakes or tsunamis. The quantitative response to predict is the numerical significance of a potential earthquake based on several factors such as its location.
Features include:
 • quantitative attributes: magnitude, date_time, cdi, mmi, sig, nst, dmin, gap, depth, lati
tude/longitude
 • qualitative attributes: title, alert, tsunami, magType, location, continent, country.
 More details on each feature can be accessed through the dataset link.

#  Data mining tasks: data preprocessing, visualization, and exploration techniques
Building on our school knowledge of tectonic plates, we expect a correlation between earthquake depth, tectonic activity type (e.g., subduction), and geographic location. For example, Japan is known for its significant seismic activity due to its tectonic setting. However, there may be additional factors influencing the likelihood and intensity of earthquakes that we aren’t yet aware of. To better understand our dataset, we start by inspecting the first few rows of the dataframe, checking for any missing values, and summarizing its shape. This initial examination allows us to assess data quality and structure. Next, we generate a correlation matrix to explore potential relationships among the features, aiming to uncover patterns and gain deeper insights.

# Hypothesis
From the correlation matrix, we can see that the most significant features that affect the sig are magnitude, mmi and cdi.  Therefore, our hypothesis is:
There is a significant relationship between seismic significance (sig) and the variables magnitude, MMI, and CDI, with recurring earthquakes exhibiting patterns of similar magnitude at the same locations.

# Simple and multiple linear regression, polynomial regression and interaction terms
- Linear Regression, Significance vs. Magnitude: Our results indicate an R-squared value of 26.25%, which is consistent with our expectations. This means that 26.25% of the the variability of an earthquake can be explained by its magnitude, suggesting that other factors also influence significance.
- Polynomial Regression, Depth vs. Magnitude (degree 5): The results from the polynomial regression indicate that the model is insignificant, as expected. The R-squared value is only 0.1%, and the negative adjusted R-squared suggests that this small percentage could be due to chance rather than a meaningful relationship. This weak fit is further supported by the high p-value of 0.9516, indicating that none of the polynomial terms significantly contribute to predicting depth based on magnitude.
- Multiple Linear Regression:  As expected, the results from the multiple linear regression indicate a significant improvement in the model’s explanatory power, with an R-squared value of 90.75%. This means that approximately 90.75% of the variability in earthquake significance (sig) can be explained by the combined effects of magnitude, CDI, MMI, and location.  The residuals range from-858.99 to 1057.47, with a median of zero, indicating no systematic bias in predictions. The residual standard error of 130.5 suggests variability in the model’s predictions, which could reflect the complexities of earthquake behavior not fully captured by the model.
- Interaction terms: the R-squared value increases to 96.14%, indicating a significant improvement in the model’s explanatory power: a large portion of the variability in earthquake significance can now be attributed to both magnitude and its interaction with different locations. The residuals range from-524.13 to 801.57, with a median close to zero, suggesting that the model’s predictions are unbiased overall. However, the residual standard error of 100.9 indicates that while the model is capturing a large portion of variability, there is still some degree of prediction error.

# Results and Final Comments:
In conclusion, our analysis demonstrates that the significance and impact of an earthquake can be effectively predicted based on several key factors: magnitude, location, CDIs, and MMIs. The final model resulted in an impressive R-squared value of 96.14%, indicating that our predictors explain a significant portion of the variability in earthquake significance. 
The regression results revealed the following insights: 
- Magnitude has a positive coefficient, suggesting that as the magnitude of an earthquake increases, so does its significance. However, the magnitude’s impact alone may not fully capture the complexity of earthquake significance when considering location as an interactive factor.
- Location plays a crucial role, with specific locations such as Japan showing higher significance scores. This highlights the necessity of incorporating geographic context into seismic risk assessments.
- Both CDI and MMI contribute positively to the model, with significant p-values, reinforcing their roles as essential predictors of earthquake impact.

Therefore, with a p-value < 2.2e-16, we can confidently reject the null hypothesis, affirming that the variables included in our model significantly contribute to explaining earthquake significance. This analysis not only enhances our understanding of earthquake dynamics but also emphasizes the importance of incorporating multiple predictive factors in seismic impact assessments. 

Future work could expand on these findings by exploring other techniques (residual plots, VIF...) to further improve prediction accuracy and deepen our insights into earthquake behavior.
