# NBA-project

This project is based on a dataset related to NBA players available on Kaggle [kaggle](https://www.kaggle.com/datasets/justinas/nba-players-data). The dataset contains information on each player who has been part of an NBA team's roster for over two decades. It includes demographic variables such as age, height, weight, and place of birth, as well as biographical details like the team played for, draft year, and round. Additionally, it provides basic box score statistics such as games played, average points, rebounds, assists, etc.

The goal of this project is to rely on a linear regression model to explore associations between the response (dependent variable) and certain predictors (independent variables). I have chosen the variable "pts" as my response variable, representing the average number of points scored. In other words, the analysis aims to identify which player statistics significantly impact the average number of points scored and the magnitude of their impact.

## First model

Initially, I create the model with all covariates; most of them are statistically significant (low p-value), making them suitable for the best model. However, a best subset selection is performed to identify the set of predictors most relevant for predicting the response for each possible number of parameters (in this case, from 1 to 13).

## Best model

The next step is to determine the optimal number of regressors to fit the model. This decision can be made using different criteria: BIC, AIC, Cp Mallow’s, and adjusted R2.

Adhering to Occam's razor principle, the best model is the one with 7 predictors.

## Potential issues

While studying the VIF, there are no collinearity problems as all VIF values are below the threshold.

The variance of the residuals, which should be constant, is heterogeneous: the plot of fitted values against residuals isn't a null plot, indicating non-randomly located residuals. A remedy for non-constant variance is to transform the response variable.

To check whether the residuals are normally distributed, one can rely on the QQ-plot and the Shapiro-Wilk test. Both tools indicate that this property is not satisfied, as the graph shows long-tailed residuals and the p-value from the test is close to 0. This issue can be addressed by implementing a non-parametric test.

I also conduct a study on outliers, high leverage points, and influential points. The only modification to the model is the removal of some outliers.

## Coefficients

The study of coefficients reveals that, for each regressor, the p-value relative to the t-test computed to determine whether the estimated coefficient is equal to 0 (H0) or different from 0 (H1) is below the threshold of 0.05. Hence, there is evidence against the null hypothesis for all predictors, concluding that all estimated coefficients are different from 0.

## Goodness of fit

The 98.87% of the variability of log(pts) is explained by the best model. The standard deviation of the model is 0.078, therefore every prediction on the response should be considered in the range ±0.078.

## Predictions and simulation of data points

I make a prediction on a new player which was not included in the dataset NBA used to fit the model and the result are pretty good.

I also simulate 167 new fitted values of log(pts), predicted using the best model. To check how far are the predictions made by the model from the actual data points contained in the dataset. I use the MSE that offers a measure of the average squared difference between the actual and simulated data points: in this case the model provides a relatively good fit to the data, because, on average, the difference between actual and simulated points is relatively small.

