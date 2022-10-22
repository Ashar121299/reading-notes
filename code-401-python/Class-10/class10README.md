## How to run Linear regression in Python scikit-Learn

### Exploring Boston Housing Data Set

1.The first step is to import the required Python libraries into Ipython Notebook.

2.This data set is available in sklearn Python module, so we'll access it using scikitlearn.
we're going to import Boston data set into Ipython notebook and store it in a variable called boston.

3.The object boston is a dictionary, so you can explore the keys of this dictionary.

### Scikit Learn

 we'll going to fit a linear regression model and predict the Boston housing prices. we'll use the least squares method as the way to estimate the coefficients.

Y = boston housing price(also called “target” data in Python)

and

X = all the other features (or independent variables)

#### Hint :Important functions to keep in mind while fitting a linear regression model are:

.lm.fit() -> fits a linear model

.lm.predict() -> Predict Y using the linear model with estimated coefficients

.lm.score() -> Returns the coefficient of determination (R^2). A measure of how well observed outcomes are replicated by the model, 
as the proportion of total variation of outcomes explained by the model.

![image](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Skitlearn-linear-model1.png)

![image](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Lm.png)



### Fitting a Linear Model

*we'll going to use all 13 parameters to fit a linear regression model. Two other parameters that you can pass to linear regression object are
fit_intercept and normalize.*

In [20]: lm.fit(X, bos.PRICE)

Out[20]: LinearRegression(copy_X=True, fit_intercept=True, normalize=False)

and then construct a data frame that contains features and estimated coefficients

finally  plot a scatter plot between True housing prices and True RM.

![image](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Relationship-between-RM-and-Price.png)


### Predicting Prices

*we'll going to calculate the predicted prices (Y^i) using lm.predict. Then  display the first 5 housing prices.*

![image](https://bigdata-madesimple.com/wp-content/uploads/2016/04/lm-predict.png)


### Training and validation data sets

In practice we wont implement linear regression on the entire data set, we will have to split the data sets into training and test data sets. So that
we train our model on training data and see how well it performed on test data.

How not to do train-test split:

![image](https://bigdata-madesimple.com/wp-content/uploads/2016/04/train-test-split.png)



### How to do train-test split:

![image](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Xtrain-and-Xtest.png)


### Residual Plots

Residual plots are a good way to visualize the errors in our data. If we have done a good job then our data should be randomly scattered around line zero.
If we see structure in our data, that means our model is not capturing some thing. Maye be there is a interaction between 2 variables that we are not considering,
or may be we are measuring time dependent data. If we get some structure in our data, we should go back to our model and check whether we are doing a good job
with our parameters.

![image](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Residual-plot.png)
