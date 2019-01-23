# ARCH Model
An ARCH (autoregressive conditionally heteroscedastic) model is a model for the variance of a time series. ARCH models are used to describe a changing, possibly volatile variance. (https://www.investopedia.com/terms/a/autoregressive-conditional-heteroskedasticity.asp)

# ARCH Model in Python
In this section, we will look at how we can develop ARCH and GARCH models in Python using the arch library.

# Test Dataset
We can create a dataset with a controlled model of variance. The simplest case would be a series of random noise where the mean is zero and the variance starts at 0.0 and steadily increases. We can achieve this in Python using the gauss() function that generates a Gaussian random number with the specified mean and standard deviation.

# Autocorrelation
We know there is an autocorrelation in the variance of the contrived dataset. Nevertheless, we can look at an autocorrelation plot to confirm this expectation.

# ARCH Model
Developing an ARCH model involves three steps:
1. Define the model
2. Fit the model
3. Make a forecast.
Before fitting and forecasting, we can split the dataset into a train and test set so that we can fit the model on the train and evaluate its performance on the test set.

# Train-test split
A model can be defined by calling the arch_model() function. We can specify a model for the mean of the series: in this case mean=’Zero’ is an appropriate model. We can then specify the model for the variance: in this case vol=’ARCH’. We can also specify the lag parameter for the ARCH model: in this case p=15. Note, in the arch library, the names of p and q parameters for ARCH/GARCH have been reversed.

# Fit
The model can be fit on the data by calling the fit() function. There are many options on this function, although the defaults are good enough for getting started. This will return a fit model.

# Forecast
Finally, we can make a prediction by calling the forecast() function on the fit model. We can specify the horizon for the forecast.
In this case, we will predict the variance for the last 10 time steps of the dataset, and withhold them from the training of the model.
