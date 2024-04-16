# Metrics

Metrics are quantitative measures used to evaluate the performance of machine learning models. They provide valuable insights into how well a model is performing and help in comparing different models, tuning hyperparameters, and diagnosing issues in the model's performance. Metrics vary depending on the type of machine learning task being addressed, such as classification, regression, or clustering.

## Common Types of Metrics

Metrics in machine learning can be broadly categorized based on the type of task or problem being addressed. Here are some common types of metrics:

### Binary Classification Metrics:

1. **Accuracy**: Measures the ratio of correctly predicted instances to the total number of instances in the dataset. $$Accuracy = \frac{TP + TN}{TP + TN + FP + FN}$$
   - Interpretation: Indicates the overall correctness of the model's predictions.

2. **Precision**: Measures the proportion of true positive predictions among all positive predictions made by the model. $$Precision = \frac{TP}{TP + FP}$$
   - Interpretation: Evaluates the model's ability to make positive predictions correctly.

3. **Recall (Sensitivity)**: Measures the proportion of true positive predictions that were correctly identified by the model. $$Recall = \frac{TP}{TP + FN}$$
   - Interpretation: Evaluates the model's ability to capture all positive instances without missing any.

4. **F1 Score**: The harmonic mean of precision and recall, providing a balance between the two metrics. $$F1 Score = \frac{2 \times Precision \times Recall}{Precision + Recall}$$
   - Interpretation: Balances the trade-off between precision and recall.

5. **ROC Curve and AUC**: Receiver Operating Characteristic curve and Area Under the ROC Curve quantify the model's performance in distinguishing between positive and negative instances.
   - Interpretation: Provides insights into the model's ability to discriminate between different classes at various threshold levels.

6. **Confusion Matrix**: Provides a tabular summary of the model's predictions versus actual class labels.
   - Components: True Positives (TP), True Negatives (TN), False Positives (FP), False Negatives (FN).
   - Interpretation: Offers detailed insights into the model's performance across different classes.

### Multiclass Classification Metrics:

1. **Accuracy**: Accuracy measures the ratio of correctly predicted instances to the total number of instances in the dataset. In multilevel classification, accuracy calculates the proportion of correctly classified instances across all classes.

   $$Accuracy = \frac{\text{Number of Correct Predictions}}{\text{Total Number of Predictions}}$$

2. **Precision**: Precision measures the proportion of true positive predictions for each class among all instances that were predicted as belonging to that class.

   $$Precision_i = \frac{TP_i}{TP_i + FP_i}$$

   where $TP_i$ is the number of true positives for class $i$, and $FP_i$ is the number of false positives for class $i$.

3. **Recall (Sensitivity)**: Recall measures the proportion of true positive predictions for each class among all instances that truly belong to that class.

   $$Recall_i = \frac{TP_i}{TP_i + FN_i}$$

   where $FN_i$ is the number of false negatives for class $i$.

4. **F1 Score**: The F1 score is the harmonic mean of precision and recall for each class.

   $$F1\_Score_i = \frac{2 \times Precision_i \times Recall_i}{Precision_i + Recall_i}$$

5. **Macro-Averaged Precision, Recall, and F1 Score**: Macro-averaging calculates the metric independently for each class and then takes the unweighted average across all classes. It gives equal weight to each class, regardless of class imbalance.

   $$Macro\_Precision = \frac{\sum_{i=1}^{N} Precision_i}{N}$$
   $$Macro\_Recall = \frac{\sum_{i=1}^{N} Recall_i}{N}$$
   $$Macro\_F1\_Score = \frac{\sum_{i=1}^{N} F1\_Score_i}{N}$$

   where $N$ is the number of classes.

6. **Micro-Averaged Precision, Recall, and F1 Score**: Micro-averaging aggregates the contributions of all classes to compute the average metric. It gives more weight to classes with more instances.

   $$Micro\_Precision = \frac{\sum_{i=1}^{N} TP_i}{\sum_{i=1}^{N} (TP_i + FP_i)}$$
   $$Micro\_Recall = \frac{\sum_{i=1}^{N} TP_i}{\sum_{i=1}^{N} (TP_i + FN_i)}$$
   $$Micro\_F1\_Score = \frac{2 \times Micro\_Precision \times Micro\_Recall}{Micro\_Precision + Micro\_Recall}$$

7. **Weighted Average Precision, Recall, and F1 Score**: Weighted averaging calculates the metric for each class and then takes the average, weighted by the number of true instances in each class. It gives more weight to classes with more instances.

   $$Weighted\_Precision = \frac{\sum_{i=1}^{N} (Precision_i \times \text{Number of True Instances}_i)}{\sum_{i=1}^{N} \text{Number of True Instances}_i}$$

   Similarly for weighted recall and weighted F1 score.

These metrics provide a comprehensive evaluation of the model's performance across all classes in a multilevel classification problem. They help identify which classes the model performs well on and which ones may need further improvement. Additionally, they assist in comparing different models and selecting the one that best meets the requirements of the task.

### Regression Metrics:

1. **Mean Absolute Error (MAE)**: Measures the average absolute difference between predicted and actual values. $$MAE = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y_i}|$$
   - Interpretation: Indicates the average magnitude of errors in predictions.

2. **Mean Squared Error (MSE)**: Measures the average of the squares of the errors between predicted and actual values. $$MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y_i})^2$$
   - Interpretation: Provides a measure of the variance of errors in predictions.

3. **Root Mean Squared Error (RMSE)**: The square root of the MSE, providing a measure of the standard deviation of errors. $$RMSE = \sqrt{MSE}$$
   - Interpretation: Indicates the typical deviation of predicted values from actual values.

4. **R-squared ($R^2$)**: Measures the proportion of the variance in the dependent variable that is predictable from the independent variables. $$R^2 = 1 - \frac{SS_{res}}{SS_{tot}}$$
   - Interpretation: Indicates the goodness of fit of the regression model to the data.

### Clustering Metrics:

1. **Silhouette Score**: Measures how similar an object is to its own cluster compared to other clusters.
   - Interpretation: Evaluates the compactness and separation of clusters.

2. **Davies–Bouldin Index**: Measures the average similarity between each cluster and its most similar cluster.
   - Interpretation: Indicates the clustering quality based on cluster separation and compactness.

3. **Calinski-Harabasz Index**: Measures the ratio of between-cluster dispersion to within-cluster dispersion.
   - Interpretation: Evaluates the separation between clusters and the compactness of clusters.

4. **Homogeneity, Completeness, and V-measure**: Measures the purity and completeness of clusters.
   - Interpretation: Provides insights into the quality of clusters based on ground truth labels.

These metrics play a crucial role in assessing the performance of machine learning models and guiding decisions in model development and optimization. Depending on the specific task and requirements, different metrics may be prioritized, and a combination of metrics is often used for comprehensive evaluation.