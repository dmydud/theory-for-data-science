# Expected Value and Variance of Population

## Table of Contents
- [Expected Values](#expected-values)
	- [Rules about Expected Values](#rules-about-expected-values)
- [Variances](#variances)
	- [Interpreting Variances](#interpreting-variances)


## Expected Values

The expected value or mean of a random variable serves as the central measure of its distribution. Symbolized as $E[X]$, it embodies the center of mass within a set of values, each associated with its corresponding weight.

- For a discrete random variable $X$ with probability mass function (PMF) $p(x)$, the expected value is defined as:

$$E[X] = \sum_x xp(x)$$

- For a continuous random variable $X$ with probability density function (PDF) $f$, the expected value is defined as:

$$E[X] = \int_{-\infty}^\infty tf(t) \, dt$$

### Rules about Expected Values

The expected value is a linear operator, which simplifies calculations for complicated expressions.

If $a$ and $b$ are constants and $X$ and $Y$ are random variables, then:

- $E[aX+b] = aE[X] + b$
- $E[X+Y] = E[X] + E[Y]$

> Let $X_i$ for $i=1,\dots,n$ be a collection of random variables, each from a distribution with mean $\mu$. Expected value of the sample average of the $X_i$:
> $$E\left[\frac{1}{n}\sum^n_{i=1}X_i\right]=\frac{1}{n}\sum^n_{i=1}E[X_i]=\\=\frac{1}{n}\sum^n_{i=1}\mu=\mu$$

The expected value of the **sample mean** equals the **population mean** it attempts to estimate. An **unbiased** estimator has an expected value equal to what it aims to estimate.

## Variances

The **variance** of a random variable quantifies its dispersion.

Given a random variable $X$ with mean $\mu$, its variance is calculated as the expected squared distance from the mean:

$$\text{Var}(X) = E[(X - \mu)^2]$$

Higher variances indicate greater spread within the distribution.

A computationally convenient form for variance is:

$$\text{Var}(X) = E[X^2] - E[X]^2$$

> Proof:
> $$\text{Var}(X) = E[(X - \mu)^2]=E[(X - E[X])^2]=\\=E[X^2-2XE[X]+E[X]^2]=\\=E[X^2]-2E[X]E[X]+E[X]^2=\\=E[X^2]-E[X]^2$$

If $a$ is constant, then the variance of $aX$ is $a^2$ times the variance of $X$.

The square root of variance is the **standard deviation**, which shares the same units as the random variable.

### Interpreting Variances

Variances and standard deviations can be challenging to interpret intuitively. Chebyshev's inequality provides a useful tool for interpreting variances. It states that:

$$P(|X-\mu| \geq k \sigma) \leq \frac{1}{k^2}$$

> Proof:
> $$P(|X-\mu| \geq k \sigma) = \int_{\{x:|x-\mu|>k\sigma\}}f(x)dx\le\\\le\int_{\{x:|x-\mu|>k\sigma\}}\frac{(x-\mu)^2}{k^2\sigma^2}f(x)dx\le\\\le\int^\infty_{-\infty}\frac{(x-\mu)^2}{k^2\sigma^2}f(x)dx=\\=\frac{1}{k^2\sigma^2}E[(X-\mu)^2]=\frac{1}{k^2\sigma^2}Var(X)=\frac{1}{k^2}$$

For example, the probability of a random variable lying beyond $k$ standard deviations from its mean is less than $1/k^2$:

- $2\sigma \rightarrow 25\%$
- $3\sigma \rightarrow 11\%$
- $4\sigma \rightarrow 6\%$

## References:
1. Brian Caffo, (Instructor). (2024). _Mathematical Biostatistics Boot Camp 1_. Coursera. https://www.coursera.org/learn/biostatistics?specialization=advanced-statistics-data-science