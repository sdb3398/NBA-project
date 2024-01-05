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

First of all I create the model with all the covariates; most of them are statistically significant (a low p-value) and so
they can be used for the best model. But, we must perform a best subset selection to identify the set of
predictors that are most relevant for predicting the response for each possible number of parameters (in this
case from 1 to 13).
