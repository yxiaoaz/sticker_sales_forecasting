# Time Series Forecasting with Polynomial Regression, Fourier Series, and ARIMA Model


### Background

This is my submission to this [Kaggle Competition](https://www.kaggle.com/competitions/playground-series-s5e1).
The objective of this challenge is to predict the daily sales of stickers at various countries and stores from 2016-2019, given data from 2010-2015.

### Dataset

This repository uses a synthetic dataset consisting of multiple numerical and categorical features, with a significant portion of missing values.

You can download the dataset [here](https://drive.google.com/drive/folders/111FK-71CZ8ftDOW9Uj3acLFAvz4HX5mD?usp=sharing).

The dataset should be downloaded to a separate `data` folder to result in the following repo structure:

```
repository
│───README.md
│───run.ipynb   
│
|─── data
│      │───train.csv
│      │───test.csv
```


### Model Design
My model contains a mixture of polynomial regression, Fourier Series, and ARIMA process. The model is defined as follows:

$$Y_t = a + \sum_{i = 1}^I a_i x^i + \sum_{k=1}^K \alpha_k sin(\frac{2\pi k t}{T}) + \beta_k cos(\frac{2\pi k t}{T}) + \varepsilon_t$$ 

Specifically, $a + \sum_{i = 1}^I a_i x^i $ capture the trend, $\sum_{k=1}^K \alpha_k sin(\frac{2\pi k t}{T}) + \beta_k cos(\frac{2\pi k t}{T})$ models the seasonality and teh arima process $\varepsilon_t$ models the residual errors.