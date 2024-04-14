# Linear Regression

Linear regression is a widely used statistical technique for modeling the relationship between a dependent variable (also known as the response variable) and one or more independent variables (also known as explanatory or predictor variables). It assumes a linear relationship between the independent variables and the dependent variable.

## Mathematical Formulation

The linear regression model can be expressed mathematically as:

$$y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \ldots + \beta_n x_n + \varepsilon$$

where:
- $y$ is the dependent variable (response variable).
- $x_1, x_2, \ldots, x_n$ are the independent variables (explanatory variables).
- $\beta_0, \beta_1, \ldots, \beta_n$ are the coefficients, representing the effect of each independent variable on the dependent variable.
- $\varepsilon$ is the error term, representing the difference between the observed and predicted values of the dependent variable.

The goal of linear regression is to estimate the coefficients $\beta_0, \beta_1, \ldots, \beta_n$ that minimize the sum of squared differences between the observed and predicted values of the dependent variable.

## Simple Linear Regression

In simple linear regression, there is only one independent variable, $x$, and one dependent variable, $y$. The relationship between $x$ and $y$ is assumed to be linear, and the model can be written as:

$$y = \beta_0 + \beta_1 x + \varepsilon$$

where:
- $\beta_0$ is the intercept (the value of $y$ when $x = 0$).
- $\beta_1$ is the slope (the change in $y$ for a one-unit change in $x$).

The coefficients $\beta_0$ and $\beta_1$ are estimated from the data using methods such as ordinary least squares.

The Least Squares Line, also known as the regression line or the best-fitting line, is a fundamental concept in linear regression analysis. It represents the line that best summarizes the relationship between the independent variable(s) and the dependent variable in the data.

## Multiple Linear Regression

In multiple linear regression, there are two or more independent variables, and the model can be written as:

$$y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \ldots + \beta_n x_n + \varepsilon$$

where:
- $x_1, x_2, \ldots, x_n$ are the independent variables.
- $\beta_0, \beta_1, \ldots, \beta_n$ are the coefficients.
- $\varepsilon$ is the error term.

Multiple linear regression allows for the analysis of the relationship between the dependent variable and multiple independent variables simultaneously. Each coefficient $\beta_i$ represents the change in the dependent variable for a one-unit change in the corresponding independent variable, holding all other variables constant.

## Regularization in Linear Regression

Regularization is a technique used to prevent overfitting in linear regression models by adding a penalty term to the loss function. The two most common types of regularization used in linear regression are Lasso (L1 regularization) and Ridge (L2 regularization).

### Lasso Regression (L1 Regularization)

In Lasso regression, the penalty term added to the loss function is the absolute value of the coefficients multiplied by a regularization parameter $\lambda$:

$$\text{Loss function} = \text{MSE} + \lambda \sum_{i=1}^{n} |\beta_i|$$

where:
- $\text{MSE}$ is the mean squared error.
- $\beta_i$ are the regression coefficients.
- $\lambda$ is the regularization parameter.

Lasso regression encourages sparsity in the coefficient values, effectively performing feature selection by driving some coefficients to zero.

### Ridge Regression (L2 Regularization)

In Ridge regression, the penalty term added to the loss function is the sum of squares of the coefficients multiplied by a regularization parameter $\lambda$:

$$\text{Loss function} = \text{MSE} + \lambda \sum_{i=1}^{n} \beta_i^2$$

Ridge regression penalizes large coefficient values, leading to more stable and robust models by reducing the impact of multicollinearity.

### Tuning the Regularization Parameter

The regularization parameter $\lambda$ controls the strength of regularization. Larger values of $\lambda$ result in more regularization, leading to simpler models with smaller coefficients. The optimal value of $\lambda$ can be determined using techniques such as cross-validation.

## OLS Calculation
To calculate the coefficients of a linear regression model, typically uses a method called ordinary least squares (OLS) regression. Here's a step-by-step guide:

1. **Setup the Data**: Organize your data into a dataset where you have your independent variables (predictors) and dependent variable (response) for each observation.

2. **Compute Means**: Calculate the mean $\bar{x}_i$ for each independent variable and the mean $\bar{y}$ for the dependent variable.

3. **Compute Covariances**: Compute the covariance between each independent variable $x_i$ and the dependent variable $y$, denoted as  $\text{cov}(x_i, y)$.

4. **Compute Variances**: Calculate the variance of each independent variable $\text{var}(x_i)$.

5. **Compute (Regularized) Coefficients**: 
	- Use the formulas for calculating the coefficients $\beta_i$: $$\beta_i = \frac{\text{cov}(x_i, y)}{\text{var}(x_i)}$$ for each $i$, where $i$ represents each independent variable.

    - For Ridge regression, the coefficients are calculated as: $$\beta_i^{Ridge} = \frac{\text{cov}(x_i, y)}{\text{var}(x_i) + \lambda}$$
    
    - For Lasso regression, the coefficients are calculated as: $$\beta_i^{Lasso} = \frac{\text{sign}(\text{cov}(x_i, y)) \cdot (\text{cov}(x_i, y) - \lambda/2)}{\text{var}(x_i)} \cdot \text{max}(0, |\text{cov}(x_i, y)| - \lambda/2)$$ where $\lambda$ is the regularization parameter.

7. **Intercept**: Calculate the intercept $\beta_0$ using the formula: $$\beta_0 = \bar{y} - \sum_{i=1}^{n} \beta_i \bar{x}_i$$ where $n$ is the number of independent variables.

8. **Model Evaluation**: Once you have the coefficients, you can evaluate the model's performance, typically using metrics like $R^2$ (coefficient of determination) and residual analysis.

9. **Predictions**: Finally, you can use the coefficients to make predictions on new data by plugging in the values of the independent variables into the regression equation: $$\hat{y} = \beta_0 + \sum_{i=1}^{n} \beta_i x_i$$ where $\hat{y}$ is the predicted value of the dependent variable.

By following these steps, you can calculate the coefficients for a linear regression model using ordinary least squares regression.

## MLE Calculation

To calculate linear regression coefficients for multiple independent variables (n variables) using mean squared error (MSE), you'll extend the process of simple linear regression to include multiple predictors. Here's how you can do it:

1. **Define the Model**: For multiple linear regression with $n$ independent variables $x_1, x_2, \ldots, x_n$ and one dependent variable $y$, the model is:

$$y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \ldots + \beta_n x_n + \varepsilon$$

   Where:
   - $y$ is the dependent variable.
   - $x_1, x_2, \ldots, x_n$ are the independent variables.
   - $\beta_0$ is the intercept.
   - $\beta_1, \beta_2, \ldots, \beta_n$ are the coefficients for the independent variables.
   - $\varepsilon$ is the error term.

2. **Calculate Predicted Values**: Use the model to calculate predicted values of the dependent variable $\hat{y}$ for each observation in the dataset. The predicted values are calculated as: $$\hat{y_i} = \beta_0 + \beta_1 x_{i1} + \beta_2 x_{i2} + \ldots + \beta_n x_{in}$$

   Where $x_{ij}$ represents the value of the $j$-th independent variable for the $i$-th observation.

3. **Calculate Residuals**: Compute the residuals $e_i$ for each observation by subtracting the predicted value from the actual value of the dependent variable: $$e_i = y_i - \hat{y_i}$$

4. **Calculate Mean Squared Error (MSE)**: Compute the mean squared error, which is the average of the squared residuals: $$\text{MSE} = \frac{1}{n} \sum_{i=1}^{n} e_i^2$$

   Where $n$ is the number of observations.

5. **Minimize MSE**: Minimize the MSE by adjusting the coefficients $\beta_0, \beta_1, \ldots, \beta_n$. This involves finding the values of the coefficients that minimize the sum of squared residuals.

   You can use optimization techniques such as gradient descent or closed-form solutions like the normal equation to minimize the MSE.

6. **Obtain Coefficients**: Once you have minimized the MSE, you obtain the estimated coefficients $\hat{\beta_0}, \hat{\beta_1}, \ldots, \hat{\beta_n}$ that define the best-fit hyperplane:

   $$\hat{\beta_j} = \frac{\sum_{i=1}^{n} (x_{ij} - \bar{x_j})(y_i - \bar{y})}{\sum_{i=1}^{n} (x_{ij} - \bar{x_j})^2}$$

   Where $\bar{x_j}$ and $\bar{y}$ are the sample means of the $j$-th independent variable $x_j$ and dependent variable $y$ respectively.

These steps outline the process of calculating linear regression coefficients for multiple variables using mean squared error. By minimizing the MSE, you can find the coefficients that best fit the data and minimize the prediction error.

## Coefficient of Determination (R-squared)

The coefficient of determination, denoted as $R^2$, measures the proportion of the variance in the dependent variable that is predictable from the independent variables. It is a measure of how well the regression model fits the observed data.

$$R^2 = 1 - \frac{\sum_{i=1}^{n} (y_i - \hat{y}_i)^2}{\sum_{i=1}^{n} (y_i - \bar{y})^2}$$

where:
- $y_i$ are the observed values of the dependent variable.
- $\hat{y}_i$ are the predicted values of the dependent variable.
- $\bar{y}$ is the mean of the observed values of the dependent variable.

The $R^2$ value ranges from 0 to 1, where 1 indicates a perfect fit and 0 indicates that the model does not explain any of the variability in the dependent variable.

## Categorical Explanatory Variables

In linear regression, categorical explanatory variables can be included by encoding them as dummy variables. Each level of the categorical variable is represented by a separate binary variable (0 or 1), which is then included as an independent variable in the regression model. This allows the model to account for the categorical variable's effect on the dependent variable.

## Hypothesis Testing

Hypothesis testing in linear regression involves assessing the significance of the regression coefficients and the overall significance of the model. This is typically done using statistical tests such as the t-test for individual coefficients and the F-test for the overall model. These tests help determine whether the relationship between the independent variables and the dependent variable is statistically significant.