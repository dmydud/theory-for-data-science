# Probability Distributions
Probability distributions are fundamental concepts in statistics and probability theory, providing a framework for understanding the likelihood of different outcomes in random phenomena. These distributions describe the behavior of random variables, which can represent various types of data, ranging from discrete counts to continuous measurements.

## Table of Contents
- [Probability Distribution Functions](#probability-distribution-functions)
    - [Probability Mass Function (PMF)](#probability-mass-function-pmf)
    - [Probability Density Function (PDF)](#probability-density-function-pdf)
    - [Cumulative Distribution Function (CDF)](#cumulative-distribution-function-cdf)
- [Binomial Distribution](#binomial-distribution)
- [Bernoulli Distribution](#bernoulli-distribution)
- [Uniform Distribution](#uniform-distribution)
- [Normal Distribution](#normal-distribution)
- [Chi-Squared Distribution](#chi-squared-distribution)
- [References](#references)

## Probability Distribution Functions
### Probability Mass Function (PMF)
The Probability Mass Function (PMF), denoted as $P(X = x)$, is a function that gives the probability of a discrete random variable $X$ taking on a specific value $x$. Unlike the Probability Density Function (PDF) for continuous variables, which describes the relative likelihood of continuous outcomes, the PMF provides the exact probabilities for each possible outcome of a discrete random variable.

#### Definition
The PMF $P(X = x)$ is defined for all possible values of the discrete random variable $X$, typically denoted by $x$. It assigns a probability to each possible outcome of $X$, representing the likelihood of that outcome occurring.

#### Characteristics
- **Discrete Variables:** The PMF is defined only for discrete random variables, which take on a countable number of distinct values.
- **Non-Negativity:** The PMF is always non-negative, meaning that $P(X = x) \geq 0$ for all possible values of $x$.
- **Normalization:** The total sum of probabilities assigned by the PMF over all possible outcomes is equal to 1. In other words, the sum of the probabilities of all possible values of $X$ equals 1.

#### Properties
- **Exact Probabilities:** Unlike the PDF, which provides probability densities, the PMF gives the exact probabilities of each possible outcome. For a given value $x$, $P(X = x)$ represents the probability of $X$ taking on that specific value.
- **Probability Calculation:** To find the probability of $X$ lying within a specific range or interval, you can sum the probabilities of all individual outcomes within that range:
$$P(a \leq X \leq b) = \sum_{x=a}^{b} P(X = x)$$

### Probability Density Function (PDF)
The Probability Density Function (PDF), denoted as $f_X(x)$, is a function that describes the relative likelihood of a continuous random variable $X$ taking on a particular value $x$. Unlike the Probability Mass Function (PMF) for discrete variables, which gives the probability of exact outcomes, the PDF provides the probability density around each point in the sample space.

#### Characteristics
- **Definition:** The PDF $f_X(x)$ is defined for all real numbers $x$.
- **Non-Negativity:** The PDF is always non-negative, meaning that $f_X(x) \geq 0$ for all $x$.
- **Normalization:** The total area under the PDF curve is equal to 1. In other words, the integral of $f_X(x)$ over the entire range of possible values of $x$ is equal to 1. This ensures that the total probability of all possible outcomes is 1.

#### Properties
- **Relative Likelihood:** The height of the PDF curve at a specific point $x$ represents the relative likelihood of observing that value. Higher values of $f_X(x)$ indicate that $x$ is more likely to occur.
- **Probability Density:** Unlike the PMF, which directly gives probabilities, the PDF provides probability densities. To obtain the probability of $X$ lying within a specific interval $[a, b]$, you need to integrate the PDF over that interval:
$$P(a \leq X \leq b) = \int_{a}^{b} f_X(x) \, dx$$

### Cumulative Distribution Function (CDF)

The Cumulative Distribution Function (CDF), denoted as $F_X(x)$, is a function that gives the probability that a random variable $X$ takes on a value less than or equal to $x$. In other words, the CDF provides the cumulative probability distribution of $X$ up to a certain point $x$.

#### Definition
The CDF $F_X(x)$ is defined as:
$$F_X(x) = P(X \leq x)$$

Where:
- $x$ is any real number.
- $P(X \leq x)$ represents the probability that the random variable $X$ takes on a value less than or equal to $x$.

#### Characteristics
- **Monotonicity:** The CDF is a non-decreasing function, meaning that as $x$ increases, $F_X(x)$ either increases or remains constant.
- **Range:** The range of the CDF is $[0, 1]$, inclusive. This is because probabilities are always between 0 and 1.
- **Right-Continuity:** The CDF is right-continuous, meaning that the CDF approaches its limit from the right as $x$ approaches a specific value.

#### Properties
- **Probability Calculation:** The CDF allows us to calculate probabilities of random variables lying within certain intervals. For example, the probability that $X$ lies in the interval $[a, b]$ is given by:
$$P(a \leq X \leq b) = F_X(b) - F_X(a)$$

- **Relationship with PDF:** For continuous random variables, the CDF is the integral of the Probability Density Function (PDF). Mathematically, the CDF can be expressed as:
$$F_X(x) = \int_{-\infty}^{x} f_X(t) \, dt$$
  
  Where $f_X(t)$ is the PDF of the random variable $X$.
  
- **Inverse CDF:** The inverse of the CDF, denoted as $F_X^{-1}(p)$, gives the value of $x$ for which $F_X(x) = p$. It is also known as the quantile function and is useful in generating random samples from a given distribution.

## Binomial Distribution
In probability theory and statistics, the binomial distribution is a discrete probability distribution that describes the number of successes in a fixed number of independent Bernoulli trials, denoted by $n$, where each trial has the same probability of success, denoted by $p$.

### Definition
A random variable $X$ follows a binomial distribution with parameters $n$ and $p$, denoted as $X \sim \text{Binomial}(n, p)$, if its probability mass function (PMF) is given by:
$$P(X = k) = \binom{n}{k} \cdot p^k \cdot (1 - p)^{n - k}$$
Where:
- $\binom{n}{k}$ is the binomial coefficient.
- $p^k$ is the probability of $k$ successes.
- $(1 - p)^{n - k}$ is the probability of $n - k$ failures.

### Binomial Coefficient

The binomial coefficient, denoted by $\binom{n}{k}$, represents the number of ways to choose $k$ successes out of $n$ trials. It is also known as "n choose k" and can be calculated using the formula:
$$\binom{n}{k} = \binom{n}{n-k} = \frac{n!}{k!(n-k)!}$$

### Characteristics
$$\mu = n \cdot p$$
$$\sigma^2 = n \cdot p \cdot (1 - p)$$

## Bernoulli Distribution
In probability theory and statistics, the Bernoulli distribution represents a single trial with two possible outcomes: success (usually denoted as 1) with probability $p$ and failure (usually denoted as 0) with probability $1 - p$.

### Definition
A random variable $X$ follows a Bernoulli distribution with parameter $p$, denoted as $X \sim \text{Bernoulli}(p)$, if its probability mass function (PMF) is given by:
$$P(X = x) = \begin{cases} p & \text{if } x = 1 \\ 1 - p & \text{if } x = 0 \end{cases}$$
Where:
- $x$ represents the outcome of the trial (either 1 or 0).
- $p$ is the probability of success (the probability of $X = 1$.

### Characteristics
$$\mu = p$$
$$\sigma^2 = p \cdot (1 - p)$$

### Relationship with Binomial Distribution
The Bernoulli distribution is a special case of the binomial distribution where $n = 1$, representing a single trial. In other words, the binomial distribution with $n = 1$ reduces to the Bernoulli distribution.

## Uniform Distribution
The Uniform Distribution is a continuous probability distribution that describes an equally likely chance of observing any value within a specified range. In other words, in a uniform distribution, all outcomes within the range are equally probable.

### Definition
A continuous random variable $X$ follows a uniform distribution over the interval $[a, b]$, denoted as $X \sim \text{Uniform}(a, b)$, if its probability density function (PDF) is given by:
$$f_X(x) = \begin{cases} \frac{1}{b - a} & \text{if } a \leq x \leq b \\ 0 & \text{otherwise} \end{cases}$$
Where:
- $a$ and $b$ are the lower and upper bounds of the interval, respectively.
- The PDF $f_X(x)$ is constant within the interval $[a, b]$ and zero outside this interval.

### Characteristics
- **Constant Probability Density:** In the uniform distribution, the probability density remains constant within the specified interval, indicating an equal likelihood of observing any value within that interval.
- **Range:** The uniform distribution is defined over a specified range \([a, b]\), where \( a \) and \( b \) represent the lower and upper bounds of the interval, respectively.
- **Equal Likelihood:** All values within the interval \([a, b]\) have the same probability of occurrence, resulting in a flat or rectangular-shaped probability density function.

### Properties
$$\mu = \frac{a + b}{2}$$
$$\sigma^2 = \frac{(b - a)^2}{12}$$

- **Probability Calculation:** The probability of observing a value $x$ within the interval $[a, b]$ in a uniform distribution is proportional to the width of the interval. Mathematically, it can be expressed as: $$P(a_x \leq X \leq b_x) = \frac{b_x - a_x}{b - a}$$



## Normal Distribution
The Normal Distribution, also known as the Gaussian distribution, is a continuous probability distribution that is widely used in statistics and probability theory. It is characterized by a symmetric bell-shaped curve centered around its mean.

### Definition
A continuous random variable $X$ follows a normal distribution with parameters $\mu$ (mean) and $\sigma$ (standard deviation), denoted as $X \sim \text{Normal}(\mu, \sigma)$, if its probability density function (PDF) is given by:
$$f_X(x) = \frac{1}{\sigma \sqrt{2\pi}} \exp\left(-\frac{(x - \mu)^2}{2\sigma^2}\right)$$
Where:
- $\mu$ represents the mean of the distribution, determining its center.
- $\sigma$ is the standard deviation, controlling the spread or dispersion of the distribution.
- The term $\exp\left(-\frac{(x - \mu)^2}{2\sigma^2}\right)$ is the exponent of the normal curve, determining the shape of the distribution.

### Characteristics
- **Symmetry:** The normal distribution is symmetric around its mean $\mu$, with the highest point of the curve located at $\mu$.
- **Bell-Shaped Curve:** The PDF of the normal distribution forms a smooth, bell-shaped curve, indicating that values closer to the mean are more likely to occur than those farther away.
- **Mean and Median:** In a normal distribution, the mean, median, and mode are all equal and located at the center of the distribution.

### Properties
- **Standard Normal Distribution:** A special case of the normal distribution where $\mu = 0$ and $\sigma = 1 $ is known as the standard normal distribution, denoted as $Z \sim \text{Normal}(0, 1)$. The PDF of the standard normal distribution is denoted as $\phi(z)$.
- **Probability Calculation:** The probability of observing a value within a certain range in a normal distribution can be calculated using the cumulative distribution function (CDF), denoted as $\Phi(x)$, which gives the probability that a random variable $X$ is less than or equal to a specified value $x$.
- **Mean and Variance:** The mean $\mu$ and variance $\sigma^2$ of a normal distribution represent its central tendency and dispersion, respectively. The standard deviation $\sigma$ controls the width of the distribution curve, with larger values indicating greater dispersion.
- **68-95-99.7 Rule:** In a normal distribution, approximately 68%, 95%, and 99.7% of the data fall within one, two, and three standard deviations from the mean, respectively.

## References
1. Serrano, L. (Instructor). (2024). _Probability & Statistics for Machine Learning & Data Science_. Coursera. https://www.coursera.org/learn/machine-learning-probability-and-statistics