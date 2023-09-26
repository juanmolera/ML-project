# ML-project

This is my third project of the Ironhack data analytics bootcamp and it consists of a Kaggle competition about predicting the price of diamonds from a [dataset](https://www.kaggle.com/competitions/diamonds-datamad1022).

![diamond breakfast](/images/diamond-breakfast-1.png)

The columns of the dataset present the following information on each of the diamonds:

| id | carat | cut       | color | clarity | depth | table | x    | y    | z    | price |
|--- |-------|-----------|-------|---------|-------|-------|------|------|------|-------|
| 0  | 0.30  | Premium   | D     | SI2     | 62.4  | 58.0  | 4.31 | 4.28 | 2.68 | 6.353 |
| 1  | 1.01  | Ideal     | E     | VVS2    | 62.7  | 56.0  | 6.42 | 6.46 | 4.04 | 9.183 |
| 2  | 0.72  | Ideal     | F     | VS2     | 61.8  | 59.0  | 5.71 | 5.74 | 3.54 | 7.983 |
| 3  | 1.08  | Very Good | G     | SI2     | 63.2  | 57.0  | 6.54 | 6.50 | 4.12 | 8.371 |
| 4  | 0.36  | Premium   | G     | VS1     | 62.3  | 59.0  | 4.50 | 4.55 | 2.82 | 6.588 |

## Exploratory data analysis (EDA)

First, to perform this EDA, the characteristics of the input data set are analyzed. There are no null values, so it is not necessary to treat them, but there are duplicate values, which are discarded. Secondly, it was decided to standardize the columns containing numerical predictor variables (carat, depth, table, x, y and z), in order to reduce the influence of the difference in magnitude that exists between the values of the columns, since each of them has different units of measurement. Thirdly, the categorical predictor variables (cut, color, clarity) are encoded, for which an ordinal encoder is used because the variables have an order. It was decided to order the variables from the highest to the lowest weight in the price of diamonds according to the literature of experts in the field.

## Predictions

Before making the predictions with the test sample of the dataset, a set of tests are performed to detect which of the machine learning models studied gives the best result. The linear regression model is immediately discarded as the target variable does not have a normal distribution (saphiro = 0.00). The decision tree model is tested numerous times by modifying its parameters to try to obtain the best possible result. The combination of parameters that gives the best result is the following: max_depth = 17, max_features = 3 (sqrt(9)), min_samples_leaf = 7, min_samples_split = 13. The suitability of the random forest model to solve the problem has not been tested because I did not feel like being without a computer to work for so many hours.