# Interval Estimation
**Interval estimation** is a statistical technique used to estimate an unknown parameter of a population based on a sample from that population. Unlike point estimation, which provides a single value as an estimate of the parameter, interval estimation offers a range of values within which the true parameter value is likely to lie.

## Table of Contents

- [Interval Estimation](#interval-estimation)
- [Confidence Intervals](#confidence-intervals)
    - [Construction of Confidence Intervals](#construction-of-confidence-intervals)
        - [Confidence Interval for Population Mean](#confidence-interval-for-population-mean)
        - [Confidence Interval for Proportions](#confidence-interval-for-proportions)
    - [Interpretation of Confidence Intervals](#interpretation-of-confidence-intervals)
    - [Factors Affecting Interval Estimation](#factors-affecting-interval-estimation)
- [References](#references)

## Importance of Interval Estimation

Interval estimation provides a more informative representation of uncertainty compared to point estimation. By providing a range of plausible values for the parameter, interval estimation accounts for sampling variability and provides a measure of the precision of the estimate. This information is valuable for decision-making, hypothesis testing, and drawing conclusions about the population based on sample data.

## Confidence Intervals

The most common approach to interval estimation is the construction of **confidence intervals**. A confidence interval is a range of values derived from sample data that is likely to contain the true value of the parameter with a specified level of confidence. The level of confidence represents the probability that the interval contains the true parameter value, and it is typically expressed as a percentage (e.g., 95%, 99%).

### Construction of Confidence Intervals

The construction of a confidence interval involves two main components: the point estimate and the margin of error.

1. **Point Estimate**: The point estimate is the sample statistic (e.g., sample mean, sample proportion) used to estimate the population parameter. It serves as the center of the confidence interval.

2. **Margin of Error**: The margin of error accounts for the variability in the point estimate and is determined based on the sampling distribution of the statistic. It represents the maximum likely difference between the point estimate and the true parameter value.

The confidence interval is constructed by adding and subtracting the margin of error from the point estimate.

### Known Population Standard Deviation
To construct a 95% confidence interval for the population mean, we use the formula:

$$\text{Confidence Interval} = \bar{x} \pm Z_{1-\alpha/2} \times \frac{\sigma}{\sqrt{n}}$$

where:
- $\bar{x}$ is the sample mean,
- $Z$ is the critical value from the standard normal distribution corresponding to the desired level of confidence (for a 95% confidence interval, $Z_{0.975} \approx 1.96$),
- $\sigma$ is the population standard deviation, and
- $n$ is the sample size.

Your description is accurate. Here's a slightly revised version:

### Construction of Confidence Intervals

Constructing a confidence interval involves two primary components: the point estimate and the margin of error.

1. **Point Estimate**: The point estimate is the sample statistic (such as the sample mean or sample proportion) used to estimate the population parameter. It serves as the center of the confidence interval.

2. **Margin of Error**: The margin of error accounts for the variability in the point estimate and is determined based on the sampling distribution of the statistic. It represents the maximum likely difference between the point estimate and the true parameter value.

The confidence interval is constructed by adding and subtracting the margin of error from the point estimate.

### Confidence Interval for Population Mean

To construct a 95% confidence interval for the population mean when the population standard deviation is known, we use the formula:

$$\text{Confidence Interval} = \bar{x} \pm z_{1-\alpha/2} \times \frac{\sigma}{\sqrt{n}}$$

where:
- $\bar{x}$ is the sample mean,
- $z_{1-\alpha/2}$ is the critical value from the standard normal distribution corresponding to the desired level of confidence (for a 95% confidence interval, $z_{0.975} \approx 1.96$),
- $\sigma$ is the population standard deviation, and
- $n$ is the sample size.

#### Unknown Population Standard Deviation

To construct a 95% confidence interval for the population mean when the population standard deviation is unknown (and replaced by the sample standard deviation $s$), we use the $t$-distribution with $n-1$ degrees of freedom:

$$\text{Confidence Interval} = \bar{x} \pm t_{1-\alpha/2} \times \frac{s}{\sqrt{n}}$$

where:
- $\bar{x}$ is the sample mean,
- $s$ is the sample standard deviation,
- $n$ is the sample size, and
- $t_{1-\alpha/2}$ is the critical value from the $t$-distribution corresponding to the desired level of confidence.

#### Interpretation of Confidence Intervals

A confidence interval does not provide a definitive statement about the true parameter value; rather, it indicates the range of values that are plausible given the sample data and the specified level of confidence. 

- If we construct a 95% confidence interval for the population mean height and find that it ranges from 160 cm to 170 cm, we interpret this as follows: "We are 95% confident that the true average height of adults in the population lies between 160 cm and 170 cm."

- It's important to note that the true parameter value is either within the interval or not; the probability refers to the long-term frequency of such intervals capturing the true value in repeated sampling.

### Confidence Interval for Proportions

When dealing with proportions, where $\hat{p}$ represents the sample proportion, $x$ is the number of successes in the sample, and $n$ is the sample size, the confidence interval can be calculated using the formula:

$$\hat{p}=\frac{x}{n}$$

The confidence interval for proportions is given by:

$$\text{Confidence Interval} = \hat{p} \pm z_{1-\alpha/2} \times \sqrt{\frac{\hat{p}(1-\hat{p})}{n}}$$

Here, $z_{1-\alpha/2}$ is the critical value from the standard normal distribution corresponding to the desired level of confidence, typically 1.96 for a 95% confidence interval.


### Factors Affecting Interval Estimation

Several factors influence the width and precision of a confidence interval:

- **Sample Size**: Larger sample sizes tend to result in narrower confidence intervals, as they provide more precise estimates of the population parameter.

- **Level of Confidence**: Higher confidence levels result in wider confidence intervals, as the range needs to be broader to accommodate the increased certainty.

- **Variability in the Data**: Greater variability in the sample data typically leads to wider confidence intervals, as there is more uncertainty in the estimate of the population parameter.

## References
1. Serrano, L. (Instructor). (2024). _Probability & Statistics for Machine Learning & Data Science_. Coursera. https://www.coursera.org/learn/machine-learning-probability-and-statistics