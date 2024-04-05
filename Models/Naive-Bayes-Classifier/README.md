# Naive Bayes Classifier
The Naive Bayes Classifier is a simple yet powerful probabilistic model commonly used in machine learning for classification tasks. It is based on Bayes' Theorem, which provides a framework for making predictions based on prior knowledge and observed evidence.

## Bayes' Theorem
Bayes' Theorem, a fundamental concept in probability theory, forms the theoretical foundation of the Naive Bayes Classifier. It states:
$$P(Y|X)=P(X|Y)P(Y)\Big/P(X)$$
where:
- $P(X)$ is an **evidence** or marginal likelihood,
- $P(Y)$ is a **prior** probability,
- $P(X|Y)$ is a **likelihood**,
- $P(Y|X)$ is a **posterior** probability.

In the context of the Naive Bayes Classifier, this theorem is employed to calculate the probability of a particular class $Y$ given some features $X$, which aids in classification tasks.

## Naive Assumption

The "naive" aspect of the Naive Bayes Classifier comes from the assumption of feature independence given the class label. In other words, it assumes that the presence of a particular feature in a class is unrelated to the presence of any other feature. 

Although this assumption is often violated in real-world data, the Naive Bayes Classifier tends to perform well in practice, especially for text classification tasks. This is because all word orders are considered equally likely, making the classifier particularly effective for tasks like text classification where word order may not be as important as the presence or absence of specific words.

## Alghorithm
The Naive Bayes Classifier operates in two main phases: *training* and *prediction*.

In the training phase, the algorithm begins with a labeled dataset where each instance is associated with a class label. Features are extracted from the instances, and preprocessing steps like tokenization and vectorization are performed, especially for text data. Then, the algorithm estimates probabilities. It calculates the prior probability of each class $P(Y)$ by counting the frequency of each class label in the training set and dividing by the total number of instances. Next, it computes the likelihoods for each feature $P(X|Y)$. For each feature, it calculates the likelihood of that feature occurring given each class label. This involves counting the frequency of each feature in instances belonging to each class.

In the prediction phase, when presented with a new instance with features $X$, the algorithm calculates posterior probabilities $P(Y|X)$ for each class $Y$. It does this by applying Bayes' Theorem, considering the prior probabilities and likelihoods estimated during training:
$$P(Y|X)=P(Y)\prod_{i=1}^nP(x_i|Y),$$ 
where $x_i$ represents each feature in $X$ and $n$ is the total number of features. Specifically, it computes the posterior probability of each class given the features of the new instance. Finally, it selects the class with the highest posterior probability as the predicted class for the new instance:
$$\hat{Y}=\arg\max_YP(Y_X).$$


The Naive Bayes Classifier operates in two main phases: *training* and *prediction*.

### Training Phase

In the training phase, the algorithm begins with a labeled dataset where each instance is associated with a class label. Features are extracted from the instances, and preprocessing steps like tokenization and vectorization are performed, especially for text data. Then, the algorithm estimates probabilities:

- **Prior Probability $P(Y)$:** The algorithm calculates the prior probability of each class $Y$ by counting the frequency of each class label in the training set and dividing by the total number of instances.
  
- **Likelihoods $P(X|Y)$:** For each feature, the algorithm calculates the likelihood of that feature occurring given each class label $Y$. This involves counting the frequency of each feature in instances belonging to each class.

### Prediction Phase

In the prediction phase, when presented with a new instance with features $X$, the algorithm calculates posterior probabilities $P(Y|X)$ for each class $Y$. It does this by applying Bayes' Theorem, considering the prior probabilities and likelihoods estimated during training:

$$P(Y|X) = P(Y) \prod_{i=1}^n P(x_i|Y),$$

where $x_i$ represents each feature in $X$ and $n$ is the total number of features. Specifically, it computes the posterior probability of each class given the features of the new instance.

Since $P(X)$ is the same for all classes, it cancels out when comparing the posterior probabilities, and thus it does not need to be explicitly calculated during prediction. Therefore, the algorithm can focus solely on computing the product of prior probabilities and likelihoods for each class, making the computation more efficient.

Finally, it selects the class with the highest posterior probability as the predicted class for the new instance:

$$\hat{Y} = \arg\max_Y P(Y|X).$$

## Multinomial Naive Bayes (Discrete Features)
In the Naive Bayes Classifier, discrete features are those whose values are categorical or countable, often represented as integers or symbols. These features are typically encountered in text classification tasks, where words or tokens are used as features.

The probability estimation for discrete features in Naive Bayes classifiers involves considering the frequency of each feature occurring within each class.

The formula for estimating the likelihood of a discrete feature $x_i$ given a class $Y$ is:

$$P(x_i|Y) = \frac{m + \alpha}{l + n \cdot \alpha}$$

Where:
- $m$ is the count of occurrences of feature $x_i$ within instances belonging to class $Y$.
- $l$ is the total number of observations (instances) in the training data.
- $n$ is the total number of features.
- $\alpha$ is a smoothing parameter, often set to 1 (Laplace smoothing), as discussed in the [Zero Probability Issue](#### Zero Probability Issue).

### Zero Probability Issue
If the probability of a feature is 0 because it was not present in the training data, the classifier will always classify an object with that feature the same way, regardless of other features.

To address this problem, we can apply Laplace smoothing by adding $\alpha$ to each count of a feature in the data. For example, $\alpha = 1$. With this adjustment, even if a feature was not observed in the training data, it will have a nonzero probability assigned to it during calculation, ensuring that no probability is exactly 0.

## Gaussian Naive Bayes (Continuous Features)
When dealing with continuous features in the Naive Bayes Classifier, using a Gaussian distribution is a common choice. The probability density function (PDF) of a Gaussian distribution, also known as the normal distribution, is given by:
$$f(x) = \frac{1}{\sqrt{2\pi\sigma^2}}\exp\left(-\frac{(x-\mu)^2}{2\sigma^2}\right)$$
Where:
- $x$ is the value of the continuous feature.
- $\mu$ is the mean of the feature, which is calculated from the training data.
- $\sigma^2$ is the variance of the feature, also calculated from the training data.

This formula represents the likelihood of observing a particular value $x$ given the mean $\mu$ and variance $\sigma^2$ of the feature.

### Underflow
When dealing with probabilities, especially in the context of Naive Bayes classifiers, it's common to encounter extremely small values. These small probabilities can result from multiplying many likelihoods together, particularly in cases where there are numerous features or when dealing with continuous variables.

In computing environments with limited precision, such as floating-point arithmetic in programming languages, multiplying together a large number of small probabilities can lead to numerical underflow. Underflow occurs when the result of a computation is smaller in magnitude than the smallest representable number, causing it to be approximated as zero.

To address the issue of underflow, a common strategy is to work with logarithms of probabilities instead of the probabilities themselves. Since the logarithm is a monotonic function, taking the logarithm of probabilities preserves the order of probabilities, making it a suitable transformation for computing posterior probabilities.

By taking the logarithm of posterior probabilities, we transform multiplication into addition, which is numerically more stable. This prevents the likelihoods from becoming excessively small and helps mitigate the risk of underflow.

## Bernoulli Naive Bayes (Binary Features)

In Bernoulli Naive Bayes, features are binary variables indicating whether a particular feature is present or absent in a given instance. This variant is often used in text classification tasks where the presence or absence of words in documents is considered.

The probability estimation for Bernoulli Naive Bayes involves calculating the probability of a feature being present or absent within each class.

The formula for estimating the likelihood of a binary feature $x_i$ given a class $Y$ is:

$$P(x_i|Y) = 
\begin{cases} 
p_i & \text{if } x_i \text{ is present in } Y \\
1 - p_i & \text{if } x_i \text{ is absent in } Y 
\end{cases}$$

Where:
- $p_i$ is the probability of feature $x_i$ being present in instances belonging to class $Y$.

## Complement Naive Bayes
Complement Naive Bayes is a variant of the Naive Bayes Classifier that is **particularly useful for imbalanced datasets**, where one class significantly outnumbers the other. It essentially calculates probabilities with respect to the complement of each class and then selects the class with the smallest complementary probability. This approach tends to perform well in text classification tasks, especially sentiment analysis.

## Hybrid Naive Bayes
Hybrid Naive Bayes combines multiple Naive Bayes models, each specialized for different types of features, into a single classifier. For example, it can incorporate both Gaussian Naive Bayes for continuous features and Bernoulli Naive Bayes for binary features. This approach allows the classifier to handle datasets with mixed feature types more effectively and can potentially improve classification accuracy.

## Advantages of Naive Bayes Classifier

The Naive Bayes Classifier offers several advantages:
- **Simplicity and Ease of Implementation:** Naive Bayes Classifier is straightforward and simple to understand.
- **Less Training Data Required:** It performs well even with limited training data, which is beneficial in situations where obtaining large amounts of labeled data is challenging.
- **Handling of Both Continuous and Discrete Data:** It can handle both continuous and discrete data types, providing flexibility in various types of datasets.
- **Scalability:** The classifier is highly scalable with the number of predictors and data points. It can efficiently handle large datasets and high-dimensional feature spaces, making it suitable for text classification and other tasks with extensive feature sets.
- **Real-Time Predictions:** Naive Bayes Classifier can be used for real-time predictions due to its computational efficiency and simplicity. It is well-suited for applications requiring quick responses.
- **Robustness:** It is robust to irrelevant features, meaning it can maintain good performance even when some features are not informative for the classification task.

## Limitations of Naive Bayes Classifier
- **Naive Assumption:** The assumption of feature independence might not hold true for all datasets, which can lead to inaccurate predictions.
- **Sensitivity to Data Quality:** It is sensitive to the quality of the training data, especially when dealing with features that are rare or unseen during training.

## References
1. Serrano, L. (Instructor). (2024). _Probability & Statistics for Machine Learning & Data Science_. Coursera. https://www.coursera.org/learn/machine-learning-probability-and-statistics
2. StatQuest with Josh Starmer. (2020, June 3). _Naive Bayes, Clearly Explained!!!_ [Video]. YouTube. https://youtu.be/O2L2Uv9pdDA?si=os1LMf1gpqNPXYZO
3. Serrano.Academy. (2019, February 11). _Naive Bayes classifier: A friendly approach_ [Video]. YouTube. https://youtu.be/Q8l0Vip5YUw?si=794d0zkGBAYB-GVx
4. StatQuest with Josh Starmer. (2020, June 3). _Gaussian Naive Bayes, Clearly Explained!!!_ [Video]. YouTube. https://youtu.be/H3EjCKtlVog?si=dfLhr3lqEHDKk2UP
5. Mahesh Huddar. (2022, January 2). _6. Gaussian Naive Bayes Classifier Algorithm to classify the person as Male or Female Solved Example_ [Video]. YouTube. https://youtu.be/kufuBE6TJew?si=B6m00RzAazLr08gJ
