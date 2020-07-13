# IowaHouses
Predict House Prices in Ames, Iowa using the Kaggle Dataset

## Overview
Used the Kaggle Dataset for home sales in Ames, Iowa to predict home prices.

I discarded two documented outliers from the dataset.  And then cleaned the data.  I looked for
data that was null chose a strategy to replace the data. Features that were null because a 
home did not have that feature were set to "None."  Most missing features were replaced with the median
for that feature.  Three homes were not on public utilities, I dropped them from the training set to get a 
better model.  I rechecked for nulls to verify all were fixed.

I converted several numerical features that were really categorical to string.  Used label encoding for 
categorical features that were ordinal.  And one hot encoding for the remainder of categorical data.

I also added two new features to the data for total square footage and total number of bathrooms, since 
this info was broken into a categories of First floor bathrooms, second floor bathrooms... and the total 
seemed like it may help the model.

I used grid hyper parameter tuning.

I ran Ridge, Lasso, ElasticNet, SVR, Gradient Boosting, extreme gradient boosting, light gradient boosting,
and Random Forest regressors to build the model and predict prices.

## Results

Several models had an R-squared of over 0.90.  The boosting models did very well.  The gradient boosting regressor
was the best with an R-squared of 0.9251 and the lowest MSE.  

![Image of Visualization](https://github.com/briordan/IowaHouses/blob/master/BestFit.png)

## Next Steps

Stacking several regressors together may further improve the fit.

## Acknowledgements

Sergine https://www.kaggle.com/serigne/stacked-regressions-top-4-on-leaderboard has a great article on 
stacking regressors for this problem.  I used some of his tips on data cleaning.
