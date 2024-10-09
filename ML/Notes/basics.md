# Supervised vs Unsupervised Learning in Machine Learning

| **Aspect**                      | **Supervised Learning**                                                                 | **Unsupervised Learning**                                                        |
|----------------------------------|-----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|
| **Definition**                   | The model learns from labeled data (input-output pairs).                                | The model learns patterns from unlabeled data (no specific output labels).       |
| **Training Data**                | Requires labeled data (e.g., each input has a corresponding correct output).             | Uses unlabeled data (e.g., only input data is provided without any labels).      |
| **Goal**                         | Predict output for new, unseen inputs based on training data.                           | Identify patterns, groupings, or structures within the data.                     |
| **Type of Task**                 | Classification or regression tasks (e.g., predicting categories or values).             | Clustering or association tasks (e.g., finding similarities, grouping data).     |
| **Examples**                     | - Predicting house prices based on features like size, location (regression).           | - Grouping customers based on purchasing behavior (clustering).                  |
|                                  | - Classifying emails as spam or not spam (classification).                             | - Identifying items frequently bought together (association).                    |
| **Algorithms**                   | - Decision Trees, Support Vector Machines, Neural Networks.                            | - K-Means, Principal Component Analysis (PCA), Hierarchical Clustering.          |
| **Real-world Example**           | - Predicting whether a loan will default based on applicant data (labeled: Yes/No).     | - Grouping products into categories based on customer reviews (no labels).       |
| **Data Label Requirement**       | Yes, labels are needed for the output (e.g., labeled as spam or not spam).              | No labels required; the algorithm infers structure from the data.                |

## Example:

- **Supervised Learning Example**:  
  - **Task**: Predict house prices based on square footage, number of bedrooms, etc.  
  - **Data**: Input features (size, bedrooms, etc.) and labeled output (house price).
  
- **Unsupervised Learning Example**:  
  - **Task**: Group similar customers based on their purchase history.  
  - **Data**: Customer transaction data (no predefined labels). The model will group customers into clusters.
