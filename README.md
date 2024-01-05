# NBA-project

This project is based on a dataset related to NBA players available on Kaggle [kaggle](https://www.kaggle.com/datasets/justinas/nba-players-data). The dataset contains information on each player who has been part of an NBA team's roster for over two decades. It includes demographic variables such as age, height, weight, and place of birth, as well as biographical details like the team played for, draft year, and round. Additionally, it provides basic box score statistics such as games played, average points, rebounds, assists, etc.

The goal of this project is to utilize a linear regression model to explore associations between the response (dependent variable) and certain predictors (independent variables). I have chosen the variable "pts" as my response variable, representing the average number of points scored. In other words, the analysis aims to identify which player statistics significantly impact the average number of points scored and the magnitude of their impact.

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

# Coefficients

The study of coefficients reveals that, for each regressor, the p-value relative to the t-test computed to determine whether the estimated coefficient is equal to 0 (H0) or different from 0 (H1) is below the threshold of 0.05. Hence, there is evidence against the null hypothesis for all predictors, concluding that all estimated coefficients are different from 0.










# NBA-project
The study is based on the dataset that refers to NBA players from kaggle [kaggle] (https://www.kaggle.com/
datasets/justinas/nba-players-data). This data set contains over two decades of data on each player who
has been part of an NBA teams’ roster. It captures demographic variables such as age, height, weight and
place of birth, biographical details like the team played for, draft year and round. In addition, it has basic
box score statistics such as games played, average number of points, rebounds, assists, etc..
The goal of this project is to rely on a linear regression model to explore associations between the
response (the dependent variable) and some predictors (independent). I choose the variable “pts” as my
response variable and it represents the average number of points scored. In other words the aim of this
analysis is to identify which statistics of the players have a significant impact on the average number of
points scored and the magnitude of their impact.

## First model

First of all I create the model with all the covariates; most of them are statistically significant (a low p-value) and so
they can be used for the best model. But, we must perform a best subset selection to identify the set of
predictors that are most relevant for predicting the response for each possible number of parameters (in this
case from 1 to 13).

## Best model

the following step is to determine which is
the optimal number of regressors that must be used to fit the model. This decision can be taken by using
different criteria: the BIC, the AIC, the Cp Mallow’s and the adjusted R2.

For the Occam’s razor principle, the best model is the one with 7 predictors.

## Potential issues

Making a study related to the VIF, I see that there are not collinearity problems because all the VIF values are below the treshold.

The variance of the residuals, which should be constant, is heterogeneous: the plot of the fitted values against the residuals isn’t a null plot, the residuals are not randomly located. A remedy for non constant variance is to transform the response variable.

To check whether the residuals are normally distributed, one can rely on the QQ-plot and on the Shapiro-Wilk test: both this tools shows that this property is not satisfied, since form the graph it’s clear that the residuals distribution has long tails and the p-value obtained from the test is close to 0;
this problem can be addressed by implementing a non parametric test.

I make also a study for the outliers, high leverage points and influential points. The only modification at the model is that I remove some outliers.

# Coefficients

The study of the coefficients tells us that, for each regressor, the p-value relative to the t-test computed
to determine whether the estimated coefficient is equal to 0 (H0) or different from 0 (H1): since all of them
are below the threshold of 0.05, for all the predictors there is evidence against the null hypothesis, so the
conclusion is that all the estimated coefficient are different from 0.
