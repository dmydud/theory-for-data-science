# Point Estimation
Point estimation is a statistical method used to estimate a single value, known as a point estimate, for an unknown parameter based on observed data. The goal of point estimation is to provide a single "best guess" or representative value for the parameter of interest.

## Table of Contents

- [Point estimation](#point-estimation)
   - [Properties](#properties)
- [Maximum Likelihood Estimation (MLE)](#maximum-likelihood-estimation-mle)
   - [MLE: Bernoulli Distribution](#mle-bernoulli-distribution)
   - [MLE: Gaussian Distribution](#mle-gaussian-distribution)
- [Maximum A Posteriori (MAP) Estimation](#maximum-a-posteriori-map-estimation)
- [References](#references)


## Properties

1. **Unbiasedness**: An estimator is unbiased if, on average, it produces estimates that are equal to the true parameter value. In other words, the expected value of the estimator is equal to the true parameter value. Unbiased estimators are desirable because they do not systematically overestimate or underestimate the parameter.

	An estimator $\hat{\theta}$ for a parameter $\theta$ is unbiased if: $$\text{E}(\hat{\theta}) = \theta$$ where $\text{E}(\cdot)$ denotes the expected value operator.

2. **Consistency**: An estimator is consistent if it converges to the true parameter value as the sample size increases indefinitely. In practical terms, this means that as we collect more data, the estimator becomes increasingly accurate and approaches the true parameter value. Consistency is a crucial property as it ensures that our estimates become more reliable with larger sample sizes.

	An estimator $\hat{\theta}_n$ for a parameter $\theta$ is consistent if: $$\lim_{n \to \infty} \text{P}(|\hat{\theta}_n - \theta| > \epsilon) = 0$$ for all $\epsilon > 0$, where $n$ represents the sample size and $\text{P}(\cdot)$ denotes probability.


3. **Efficiency**: An efficient estimator achieves the smallest possible variance among all unbiased estimators. In other words, it provides estimates that are most concentrated around the true parameter value, given the sample size and distribution of the data. Efficient estimators are desirable because they offer more precise and reliable estimates, making the most efficient use of the available information.

   An estimator $\hat{\theta}$ is efficient if it achieves the Cramér-Rao lower bound (CRLB) for the variance of an unbiased estimator: $$\text{Var}(\hat{\theta}) \geq \frac{1}{I(\theta)}$$ where $\text{Var}(\cdot)$ denotes the variance, and $I(\theta)$ represents the Fisher information.

4. **Robustness**: A robust estimator is insensitive to departures from the underlying assumptions or distributional properties of the data. Robust estimators perform well even when the data contain outliers or are not perfectly normally distributed. Robustness is particularly important in real-world applications where data may not always adhere to theoretical assumptions.

   Robust estimators are less sensitive to deviations from model assumptions. One common example is the median, which is robust to outliers compared to the mean.

5. **Asymptotic Normality**: Asymptotic normality refers to the property that the distribution of the estimator converges to a normal distribution as the sample size approaches infinity. This property is important for conducting statistical inference, such as hypothesis testing and constructing confidence intervals, as it allows us to apply standard normal-based methods.

   
   An estimator $\hat{\theta}_n$ is asymptotically normal if: $$\sqrt{n}(\hat{\theta}_n - \theta) \xrightarrow{d} N(0, \sigma^2)$$ as $n \rightarrow \infty$, where $\xrightarrow{d}$ denotes convergence in distribution and $N(0, \sigma^2)$ represents a normal distribution with mean 0 and variance $\sigma^2$.

6. **Bias-Variance Tradeoff**: The bias-variance tradeoff reflects the tradeoff between bias and variance in an estimator. Bias measures the systematic error of an estimator, while variance measures its variability. In general, decreasing bias tends to increase variance and vice versa. Finding a balance between bias and variance is essential for developing estimators that provide accurate and reliable estimates.

   The Mean Squared Error (MSE) of an estimator combines both bias and variance: $$\text{MSE}(\hat{\theta}) = \text{Bias}(\hat{\theta})^2 + \text{Var}(\hat{\theta})$$ Minimizing the MSE involves balancing bias and variance to achieve the best overall performance.

7. **Sufficiency**: Sufficiency is another important property in statistical inference, particularly in the context of parameter estimation. A statistic is considered sufficient if it contains all the information in the sample relevant to estimating the parameter of interest. In simpler terms, a sufficient statistic summarizes the data in such a way that no additional information about the parameter is gained by using the entire dataset.

   Formally, let $X = (X_1, X_2, \ldots, X_n)$ be a random sample from a probability distribution characterized by a parameter $\theta$. A statistic $T = t(X)$ is said to be sufficient for $\theta$ if the conditional distribution of the sample $X$ given the statistic $T$ does not depend on $\theta$, i.e., $$f(X \,|\, T = t, \theta) = f(X \,|\, T = t)$$ for all possible values of $t$ and $\theta$, where $f(\cdot)$ represents the probability density function (or probability mass function) of $X$.

   In simpler terms, a statistic $T$ is sufficient if knowing $T$ is sufficient to capture all the information about $\theta$ contained in the data $X$.

   The concept of sufficiency is closely related to the idea of data reduction. By identifying and using a sufficient statistic, we can reduce the dimensionality of the data while retaining all the information needed for estimating the parameter of interest. This can lead to more efficient estimation procedures and facilitate simpler and more interpretable analyses.

## Maximum Likelihood Estimation (MLE)
Maximum Likelihood Estimation (MLE) is a fundamental statistical method used to estimate the parameters of a probability distribution. It is based on the principle of finding the set of parameter values that maximizes the likelihood function, which measures the probability of observing the given data under the assumed statistical model.

The concept of likelihood plays a central role in MLE. Given a statistical model with parameters θ and observed data x, the likelihood function $L(θ | x)$ represents the probability of observing the data x given the parameter values $\theta$. Mathematically, it is expressed as the joint probability density function or probability mass function of the observed data:

$$L(\theta | x) = f(x | \theta)$$

Where $f(x | \theta)$ denotes the probability density function (pdf) or probability mass function (pmf) of the data $x$ given the parameter values $\theta$.

The goal of MLE is to find the value of $\theta$ that maximizes the likelihood function, i.e., the parameter values that make the observed data most probable. This is often done by taking the derivative of the likelihood function with respect to the parameters, setting it equal to zero, and solving for the parameters. In some cases, it might be more convenient to maximize the log-likelihood function, as it simplifies the calculations and does not change the location of the maximum since the logarithm function is monotonically increasing.

$$\ell(\theta | x) = \log L(\theta | x)$$

Once the maximum likelihood estimates are obtained, they can be used to make inferences about the underlying population or to make predictions for new data. MLE provides point estimates of the parameters, along with measures of uncertainty such as standard errors or confidence intervals.

### MLE: Bernoulli Distribution
Given a sequence of $n$ independent Bernoulli trials with outcomes $x_1, x_2, ..., x_n$, where each $x_i$ is either 0 or 1, the likelihood function for estimating the parameter $p$ is:

$$L(p | x_1, x_2, ..., x_n) = p^{\sum_{i=1}^{n} x_i} (1-p)^{n - \sum_{i=1}^{n} x_i}$$

This likelihood function represents the probability of observing the given sequence of outcomes, assuming each trial is independent and follows a Bernoulli distribution with parameter $p$.


$$\ell(p | x_1, x_2, ..., x_n) = \log L(p | x_1, x_2, ..., x_n) = \sum_{i=1}^{n} x_i \log(p) + (n - \sum_{i=1}^{n} x_i) \log(1-p)$$


We differentiate this function with respect to $p$ and set the derivative equal to zero to find the maximum likelihood estimate.

Taking the derivative with respect to $p$ gives:

$$\frac{d\ell}{dp} = \frac{\sum_{i=1}^{n} x_i}{p} - \frac{n - \sum_{i=1}^{n} x_i}{1-p}$$

Setting this derivative equal to zero:

$$\frac{\sum_{i=1}^{n} x_i}{\hat{p}} - \frac{n - \sum_{i=1}^{n} x_i}{1-\hat{p}} = 0$$

Solving this equation for $\hat{p}$:

$$\frac{\sum_{i=1}^{n} x_i}{\hat{p}} = \frac{n - \sum_{i=1}^{n} x_i}{1-\hat{p}}$$

$$\hat{p} \times (n - \sum_{i=1}^{n} x_i) = (1-\hat{p}) \times \sum_{i=1}^{n} x_i$$

$$\hat{p} \times n - \hat{p} \times \sum_{i=1}^{n} x_i = \sum_{i=1}^{n} x_i - \hat{p} \times \sum_{i=1}^{n} x_i$$

$$\hat{p} \times n = \sum_{i=1}^{n} x_i$$

$$\hat{p} = \frac{\sum_{i=1}^{n} x_i}{n} = \bar{x}$$

So, the maximum likelihood estimate $\hat{p}$ for the parameter $p$ in a Bernoulli distribution is simply the proportion of successes in the observed data.

Hence, the Maximum Likelihood Estimation for $p$ is the sample mean $\bar{x}$.


### MLE: Gaussian Distribution
The Gaussian distribution, often referred to as the Normal distribution, is a continuous probability distribution that is characterized by its mean $\mu$ and standard deviation $\sigma$. The probability density function (pdf) of the Gaussian distribution is given by:

$$f(x | \mu, \sigma) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left(-\frac{(x - \mu)^2}{2\sigma^2}\right)$$

where $x$ is the random variable, $\mu$ is the mean, and $\sigma$ is the standard deviation.

Given a sample of $n$ independent and identically distributed (i.i.d.) observations $x_1, x_2, ..., x_n$ from a Gaussian distribution, the likelihood function for estimating the parameters $\mu$ and $\sigma$ is:

$$L(\mu, \sigma | x_1, x_2, ..., x_n) = \prod_{i=1}^{n} \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left(-\frac{(x_i - \mu)^2}{2\sigma^2}\right)$$

Taking the logarithm of the likelihood function (log-likelihood) to simplify the calculations:

$$\ell(\mu, \sigma | x_1, x_2, ..., x_n) = -\frac{n}{2} \log(2\pi) - n \log(\sigma) - \frac{1}{2\sigma^2} \sum_{i=1}^{n} (x_i - \mu)^2$$

#### MLE for $\mu$

The partial derivative of the log-likelihood function with respect to $\mu$ is:

$$\frac{\partial}{\partial \mu} \ell(\mu,\sigma) = \frac{1}{\sigma^2} \left( \sum_{i=1}^{n} x_i - n\mu \right)$$

Setting this derivative equal to \(0\), we have:

$$\frac{1}{\sigma^2} \left( \sum_{i=1}^{n} x_i - n\mu \right) = 0$$

Since $\sigma > 0$, we can simplify the expression to:

$$\sum_{i=1}^{n} x_i - n\mu = 0$$

Solving for $\mu$, we get:

$$\hat{\mu} = \frac{\sum_{i=1}^{n} x_i}{n} = \bar{x}$$

So, the MLE for $\mu$ is the sample mean $\bar{x}$.

#### MLE for $\sigma$

Next, we find the value of $\sigma$ that maximizes the log-likelihood function. The partial derivative of the log-likelihood function with respect to $\sigma$ is:

$$\frac{\partial}{\partial \sigma} \ell(\mu,\sigma) = -\frac{n}{\sigma} + \frac{1}{\sigma^3} \sum_{i=1}^{n} (x_i - \mu)^2$$

Setting this derivative equal to \(0\), we have:

$$-\frac{n}{\sigma} + \frac{1}{\sigma^3} \sum_{i=1}^{n} (x_i - \mu)^2 = 0$$

Since $\sigma > 0$, we can simplify the expression to:

$$-n + \frac{1}{\sigma^2} \sum_{i=1}^{n} (x_i - \mu)^2 = 0$$

Substituting $\mu = \bar{x}$, we have:

$$-n + \frac{1}{\sigma^2} \sum_{i=1}^{n} (x_i - \bar{x})^2 = 0$$

Solving for $\sigma^2$, we get:

$$\sigma^2 = \frac{\sum_{i=1}^{n} (x_i - \bar{x})^2}{n}$$

And finally, the MLE for $\sigma$ is:

$$\hat{\sigma} = \sqrt{\frac{\sum_{i=1}^{n} (x_i - \bar{x})^2}{n}}$$

This expression tells us that the MLE for the standard deviation of a Gaussian population is the square root of the average squared difference between each sample and the sample mean, similar to the formula for the sample standard deviation, with the only difference being the normalizing constant.

## Maximum A Posteriori (MAP) Estimation
Maximum A Posteriori (MAP) estimation is a Bayesian approach used to estimate the parameters of a model by incorporating prior knowledge or beliefs about those parameters. In the context of linear regression, MAP estimation extends the concept of Maximum Likelihood Estimation (MLE) by considering not only the likelihood of the observed data but also the prior distribution of the parameters.

Formally, MAP estimation seeks to find the parameter values that maximize the posterior probability, which is proportional to the product of the likelihood function and the prior distribution of the parameters. Mathematically, the MAP estimate $\hat{\boldsymbol{\theta}}$ of the parameters $\boldsymbol{\theta}$ is given by:

$$\hat{\boldsymbol{\theta}}_{\text{MAP}} = \arg \max_{\boldsymbol{\theta}} \left[ P(\boldsymbol{\theta} | \text{data}) \right]=\\=\arg \max_{\boldsymbol{\theta}} \left[\frac{ P(\text{data} | \boldsymbol{\theta}) \times P(\boldsymbol{\theta})}{P(\text{data})} \right]=\arg \max_{\boldsymbol{\theta}} \left[ P(\text{data} | \boldsymbol{\theta}) \times P(\boldsymbol{\theta}) \right]$$

Where:
- $P(\boldsymbol{\theta} | \text{data})$ is the posterior distribution of the parameters given the observed data.
- $P(\text{data} | \boldsymbol{\theta})$ is the likelihood function, representing the probability of observing the data given the parameters.
- $P(\boldsymbol{\theta})$ is the prior distribution of the parameters, representing prior beliefs or knowledge about the parameters.

In the context of linear regression, MAP estimation involves specifying prior distributions for the regression coefficients $\beta_0, \beta_1, \dots, \beta_n$. These prior distributions encapsulate any prior beliefs or assumptions about the values of the coefficients. Common choices for prior distributions include Gaussian (normal) distributions, Laplace distributions, or other informative or non-informative distributions depending on the available information and the specific context of the problem.

By combining the likelihood function with the prior distributions, MAP estimation provides a principled way to incorporate additional information into the parameter estimation process. It allows for a more robust estimation, especially in situations where the amount of observed data is limited or when additional domain knowledge is available.

## References:
1. Serrano, L. (Instructor). (2024). _Probability & Statistics for Machine Learning & Data Science_. Coursera. https://www.coursera.org/learn/machine-learning-probability-and-statistics
