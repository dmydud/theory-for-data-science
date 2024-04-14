# Correlation

## Covariance

The **covariance** between two random variables $X$ and $Y$ is defined as:

$$\text{Cov}(X, Y) = E[(X - \mu_x)(Y - \mu_y)] = E[XY] - E[X] \cdot E[Y]$$

The following are useful facts about covariance:

1. $\text{Cov}(X, Y) = \text{Cov}(Y, X)$
2. $\text{Cov}(X, Y)$ can be negative or positive
3. $\left| \text{Cov}(X, Y) \right| \leqslant \sqrt{\text{Var}(X) \cdot \text{Var}(Y)}$

## Correlation

The **correlation** between $X$ and $Y$ is:

$$\text{Cor}(X,Y) = \frac{\text{Cov}(X,Y)}{\sqrt{\text{Var}(X) \cdot \text{Var}(Y)}}$$

The correlation describes the strength of the **linear association** between two variables.

The following are useful facts about correlation:

1. $-1 \leqslant \text{Cor}(X,Y) \leqslant 1$
2. $\text{Cor}(X,Y) = \pm 1$ if and only if $X = a + bY$ for some constants $a$ and $b$
3. $\text{Cor}(X,Y)$ is unitless

The sign of the correlation coefficient indicates the direction of association:
1. $X$ and $Y$ are **uncorrelated** if $\text{Cor}(X,Y) = 0$
2. $X$ and $Y$ are positively correlated, the closer $\text{Cor}(X,Y)$ is to $1$
3. $X$ and $Y$ are negatively correlated, the closer $\text{Cor}(X,Y)$ is to $-1$

The correlation coefficient is **unitless**, and is not affected by changes in the center or scale of either variable.

The correlation of $X$ with $Y$ is the same as of $Y$ with $X$.

The correlation coefficient is sensitive to outliers.

---

Let $\{X_i\}^n_{i=1}$ be a collection of random variables:

$$\text{Var}\left(\sum^n_{i=1}a_iX_i + b\right) = \sum^n_{i=1}a_i^2 \text{Var}(X_i) + 2\sum^{n-1}_{i=1}\sum^{n}_{j=i}a_i a_j \text{Cov}(X_i, X_j)$$

If the $X_i$ are IID with variance $\sigma^2$, then $\text{Var}(\bar{X}) = \sigma^2/n$ and $E[S^2] = \sigma^2$.

**Note:** $\text{Var}(X+Y) = \text{Var}(X) + \text{Var}(Y) + 2\text{Cov}(X,Y)$

If a collection of random variables $\{X_i\}$ are uncorrelated, then the variance of the sum is the sum of the variances:

$$\text{Cor}(X,Y) = 0 \Rightarrow \text{Var}\left(\sum_{i=1}^n X_i\right) = \sum_{i=1}^n \text{Var}(X_i)$$

## References:
1. Brian Caffo, (Instructor). (2024). _Mathematical Biostatistics Boot Camp 1_. Coursera. https://www.coursera.org/learn/biostatistics?specialization=advanced-statistics-data-science
2. Mine Çetinkaya-Rundel (Instructor). (2024). _Linear Regression and Modeling_. Coursera. https://www.coursera.org/learn/linear-regression-model?specialization=statistics