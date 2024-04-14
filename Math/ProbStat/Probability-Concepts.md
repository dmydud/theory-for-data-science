# Probability Concepts

## Table of Contents

- [Probability Measure](#probability-measure)
- [Random Variables](#random-variables)
- [PMFs and PDFs](#pmfs-and-pdfs)
- [CDF and SF](#cdf-and-sf)
- [Quantile](#quantile)
- [References](#references)

## Probability Measure
A **probability measure**, denoted as $P$, is a real-valued function defined on a collection of possible events such that the following hold:

1. For any event $E \subset \Omega$, $0 \leq P(E) \leq 1$.
2. $P(\Omega) = 1$.
3. If $E_1$ and $E_2$ are mutually exclusive events, then $P(E_1 \cup E_2) = P(E_1) + P(E_2)$.

---
Part 3 Implies **finite additivity**:
$$P(\cup^n_{i=1}A_i )=\sum^n_{i=1}P(A_i)$$
where the $\{A_i\}$ are mutually exclusive.

This is usually extended to **countable additivity**:
$$P(\cup^\infty_{i=1}A_i )=\sum^\infty_{i=1}P(A_i)$$

---

$P$ is defined on $\mathcal{F}$ a callection of subsets of $\Omega$.

When $\Omega$ is continuous, defining this becomes more complex. Here, we presume that $\mathcal{F}$ is comprehensive enough to encompass all relevant sets of interest.

---

- $P(\varnothing)=0$
- $P(E)=1-P(E^c)$
> Proof:
> $$1=P(\Omega)=P(E \cup E^c) = P(E) + P(E^c) \Rightarrow\\\Rightarrow1-P(E^c)$$
- $P(A \cup B)=P(A)+P(B)-P(A \cap B)$
- If $A \sub B$ then $P(A) \le P(B)$
- $P(A \cup B)=1 - P(A^c \cap B^c)$
- $P(A \cap B^c)=P(A) - P(A \cap B)$
- $P(\cup^n_{i=1}E_i ) \le \sum^n_{i=1} P(E_i)$
> Proof:
> $$P(E_1 \cup E_2)=P(E_1) + P(E_2) - P(E_1 \cap E_2)\\ \le P(E_1) + P(E_2)$$
> Assume the statement is true for $n-1$ and consider $n$
> $$P(\cup^n_{i=1}E_i ) \le P(E_n) + P(\cup^{n-1}_{i=1}E_i) \\ \le P(E_n) + \sum^{n-1}_{i=1}P(E_i)=\sum^{n}_{i=1}P(E_i)$$
- $P(\cup^n_{i=1}E_i ) \ge \max_i P(E_i)$

## Random Variables

A **random variable** is a numeric outcome of an experiment.

- **Discrete random variables** take on a countable number of possibilities, represented as $P(X=k)$.
- **Continuous random variables** can assume any value on the real line or some subset of it, represented as $P(X \in A)$.

## PMFs and PDFs

- **Probability Mass Function (PMF)**: Associated with discrete random variables, it maps values to their probabilities. A valid PMF function $p(x)$ must satisfy:
   1. $\forall x, \; p(x) \geq 0$.
   2. $\sum_x p(x) = 1$.

- **Probability Density Function (PDF)**: Associated with continuous random variables, it describes the distribution of probabilities. A valid PDF function $f_X(x)$ must satisfy:
   1. $\forall x, \; f_X(x) \geq 0$.
   2. $\displaystyle\int_{-\infty}^\infty f_X(x) \, dx = 1$.

	Areas under pdfs correspond to probabilities for that random variable.

**Note:** In probability and statistics, we use different notation to distinguish between conceptual entities and realized values. When we refer to a random variable conceptually, we use uppercase letters like $X$ to represent it. On the other hand, when we use lowercase letters like $x$ or $y$, we are referring to specific realized values of the random variable. While this notation may initially seem confusing, it helps differentiate between the abstract concept of the random variable and its specific outcomes.

## CDF and SF

- **Cumulative Distribution Function (CDF):** Defined as $F(x) = P(X \leq x)$.
- **Survival Function (SF):** Defined as $S(x) = P(X > x)$. 
$$S(x) = 1 - F(x)$$

For continuous random variables, the PDF is the derivative of the CDF.

## Quantile

- **Quantile:** The $\alpha^{th}$ quantile $x_\alpha$ of a distribution with CDF $F$ satisfies $F(x_\alpha) = \alpha$.
- **Percentile:** A quantile expressed as a percentage.
- **Median:** The $50^{th}$ percentile.

## References:
1. Brian Caffo, (Instructor). (2024). _Mathematical Biostatistics Boot Camp 1_. Coursera. https://www.coursera.org/learn/biostatistics?specialization=advanced-statistics-data-science